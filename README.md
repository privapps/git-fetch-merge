## What
A github action that fetch a remote tar/xz/gz files, extract it, and add all files of that folder, and commit to current branch.

## Why
Had a hug project, a few GB in size with a few million files, and want to migrate to github. The `git add/commit/push` took ages. I am not sure it is bandwidth related or just git is slow to index so many files. So I create this to let github action to do the heavy lifting.

## Github Action Usage

See [action.yml](https://github.com/privapps/git-fetch-merge/blob/main/action.yml)
```
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: privapps/git-fetch-merge@main
        with:
          target-url: 'https://raw.githubusercontent.com/privapps/git-fetch-merge/data-4-test/data.tar.xz'
          extracted-folder: 'data'
          no-trace: false
```
