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
# または
$ docker image ls -a

# イメージ削除
$ docker rmi IMAGE_ID
# または
$ docker image rm IMAGE_ID

# イメージ全削除
$ docker image rm $(docker image ls -a -q)

# 一時的にイメージに入る
$ docker run --rm -it IMAGE_NAME /bin/bash
```

## container
```
# コンテナ一覧の確認
$ docker ps -a
# または
$ docker container ls -a

# コンテナの停止(コンテナIDがCONTAINER_IDのものを停止)
$ docker stop CONTAINER_ID
# または
$ docker container stop CONTAINER_ID

# コンテナの削除(コンテナIDがCONTAINER_IDのものを削除)
$ docker rm CONTAINER_ID
# または
$ docker container rm CONTAINER_ID

# コンテナの全削除
$ docker container rm $(docker container ls -a -q)

# 停止したコンテナの一括削除
$ docker container prune

# コンテナに入る(コンテナのbashを起動)
$ docker exec -it CONTAINER_NAME bash
```
