# Docker cheatsheet

###### イメージのビルド
dockerでビルド時になまえ(リポジトリ名/タグ)をつける.  
```
# 現在のディレクトリにあるDockerfileを使う場合
$ docker build -t name:tag .
# Dockerfileを指定する場合
$ docker build -t name:tag -f Dockerfile-01
```

###### コンテナ一覧の確認
```
$ docker ps -a
```

###### コンテナの停止
```
$ docker stop container_id
```

###### コンテナの削除
```
$ docker rm container_id
```
