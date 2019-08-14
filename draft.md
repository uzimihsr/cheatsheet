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
