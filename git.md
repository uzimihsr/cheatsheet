# Git cheatsheet

## repository

```bash
# リポジトリごとにアカウントを使い分ける  
## httpsでcloneする(重要)
$ git clone https://github.com/path/to/repo.git
$ cd repo
## このリポジトリ限定でGithubのユーザ名とメールアドレスを設定
$ git config --local user.name <USERNAME>
$ git config --local user.email <MAIL_ADDRESS>
## 以降はPushの時にパスワードを求められる
$ git push origin master
Username for 'https://github.com':
Password for 'https://username@github.com':

# リモートリポジトリの登録(origin)
$ git remote add origin <REPO_URL>
```

## branch
```bash
# リモートも含めた全ブランチの確認
$ git branch -a

# リモートブランチにローカルでチェックアウトする
$ git checkout -b branchname remotes/origin/branchname

# 2つのブランチの差分を表示する
$ git diff <BRANCH_A> <BRANCH_B>
```

## .gitignore
[gitignore.io](https://www.gitignore.io/)  
使う言語とかOSを入力するだけでいい感じの.gitignoreをすぐ生成してくれる.  
