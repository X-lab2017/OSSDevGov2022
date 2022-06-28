# elastic/elasticsearch分析报告

## CI/CD的使用

elastic/elasticsearch使用两个CI/CD。其中一个是**gradle-wrapper-validation.yml**

```yml
name: "Validate Gradle Wrapper"
on: [push]

jobs:
  validation:
    name: "Validation"
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gradle/wrapper-validation-action@v1
```

此操作验证源代码树中Gradle Wrapper JAR文件的校验和，如果发现未知的Gradle Wrapper JAR文件则失败。

另外一个是**sync-main-branch.yml**

```yml
# Synchronize all pushes to 'master' branch with 'main' branch to facilitate migration
name: "Sync main branch"
on:
  push:
    branches:
      - master

jobs:
  sync_latest_from_upstream:
    runs-on: ubuntu-latest
    name: Sync latest commits from master branch

    steps:
      - name: Checkout target repo
        uses: actions/checkout@v2
        with:
          ref: main

      - name: Sync upstream changes
        id: sync
        uses: aormsby/Fork-Sync-With-Upstream-action@v3.0
        with:
          target_sync_branch: main
          target_repo_token: ${{ secrets.GITHUB_TOKEN }}
          upstream_sync_branch: master
          upstream_sync_repo: elastic/elasticsearch
```

当有代码push在master分支上时，执行sync_latest_from_upstream工作。actions/checkout@v2这个action切换到$GITHUB_WORKSPACE下，所以这个仓库的workflow可以访问它。aormsby/Fork-Sync-With-Upstream-action@v3.0这个action将elastic/elasticsearch的master分支同步到main分支中，main分支应该是非工作分支。
