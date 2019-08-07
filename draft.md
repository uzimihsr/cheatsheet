# draft.md
まとめるのは後にしてとにかく書きなぐる

.gitignoreを生成するツール
[gitignore.io](https://www.gitignore.io/)

リモートリポジトリを含めたブランチの確認
```
$ git branch -a
```

リモートのブランチをローカルにpull.  
できればブランチ名を揃えた方があとで楽.
```
$ git checkout -b branchname remotes/origin/branchname
```
