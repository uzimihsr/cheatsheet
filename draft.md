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

MacでGitHubのアカウントを切り替えた際, .gitconfigなどは[新アカウント]に更新されているのに  
git pushの際にPermission denied [旧アカウント]が出るばあいの対処法  
```
[キーチェーンアクセス]を開き, github.comを削除する
```

やべーやつ
https://pypi.org/project/Unidecode/

dockerでビルド時になまえ(リポジトリ名/タグ)をつける, 命名規則わからぬ
```
$ docker build -t name:tag .
```

タグつけない場合(そんなのあるのか?)
```
$ docker build -t name .
```
