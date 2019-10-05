# Docker cheatsheet

## image
```
# 現在のディレクトリにあるDockerfileでイメージをビルド
$ docker build -t name:tag .

# Dockerfileを指定してイメージをビルド(Dockerfile-sampleを使用する例)
$ docker build -t name:tag -f Dockerfile-sample

# イメージを実行
$ docker run name:tag

# イメージ一覧
$ docker images

# イメージ削除
$ docker rmi IMAGE_ID

# 一時的にイメージに入る
$ docker run --rm -it IMAGE_NAME /bin/bash
```

## container
```
# コンテナ一覧の確認
$ docker ps -a
# または
$ docker container ls

# コンテナの停止(コンテナIDがCONTAINER_IDのものを停止)
$ docker stop CONTAINER_ID

# コンテナの削除(コンテナIDがCONTAINER_IDのものを削除)
$ docker rm CONTAINER_ID

# 停止したコンテナの一括削除
$ docker container prune

# コンテナに入る(コンテナのbashを起動)
$ docker exec -it CONTAINER_NAME bash
```
