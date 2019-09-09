# Git cheatsheet

###### リモートも含めた全ブランチの確認
`-a`オプションでリモートブランチも含めて全部表示する.  
```
$ git branch -a
```

###### リモートブランチにローカルでチェックアウトする
```
$ git checkout -b branchname remotes/origin/branchname
```

###### リポジトリごとにGitアカウントを使い分ける
リポジトリURLの前にアカウントとパスワードを記述する.  
```
$ git clone https://user:password@github.com/path/to/repo.git
```

###### いい感じの.gitignoreを生成する
[gitignore.io](https://www.gitignore.io/)
使う言語とかOSを入力するだけで必要な.gitignoreをすぐ生成してくれる.  
