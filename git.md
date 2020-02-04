# Git cheatsheet

## repository

リポジトリごとにアカウントを使い分ける  
```bash
# httpsでclone
$ git clone https://github.com/path/to/repo.git
$ cd repo

# このリポジトリ限定でユーザ名とメールアドレスを設定
$ git config --local user.name uzimihsr
$ git config --local user.email uzimihsr@gmail.com

# 以降はPushの時にパスワードを求められる
$ git push origin master
Username for 'https://github.com':
Password for 'https://username@github.com':
```

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

###### リモートリポジトリの登録(origin)
```
$ git remote add origin REPO_URL
```
