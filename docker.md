# Docker cheatsheet

## image
```bash
# 現在のディレクトリにあるDockerfileでイメージをビルド
$ docker image build -t <REPOSITORY>:<TAG> .

# Dockerfileを指定してイメージをビルド
$ docker image build -t <REPOSITORY>:<TAG> -f <PATH_TO_DOCKERFILE>

# Docker Hub用にイメージにタグを付け直す
$ docker image tag <REPOSITORY>:<TAG> <DOCKER_HUB_ID>/<REPOSITORY>:<TAG>

# 全イメージを表示
$ docker image ls -a

# イメージ削除
$ docker image rm <IMAGE_ID>
$ docker image rm <REPOSITORY>:<TAG>

# イメージ全削除
$ docker image rm $(docker image ls -a -q)

# 一時的にイメージ(IMAGE_NAME)に入る
# 厳密には使い切りのコンテナを起動してENTRYPOINTを消してbashを呼び出している
$ docker container run --rm -it --entrypoint='' <IMAGE_ID> /bin/bash
$ docker container run --rm -it --entrypoint='' <REPOSITORY>:<TAG> /bin/bash

# イメージからDockerfileの内容を(ほぼ)復元
$ docker image history <IMAGE_ID>
$ docker image history <REPOSITORY>:<TAG>
```

## container
```bash
# イメージを使用してコンテナを起動
$ docker container run <IMAGE_ID>
$ docker container run <REPOSITORY>:<TAG>

# ポートを指定してコンテナを起動(ローカルマシンの8080番をコンテナの80番に割当)
$ docker container run -p 8080:80 <REPOSITORY>:<TAG>

# コンテナ一覧の確認
$ docker container ls -a

# コンテナの停止(コンテナIDがCONTAINER_IDのものを停止)
$ docker container stop <CONTAINER_ID>

# コンテナの削除(コンテナIDがCONTAINER_IDのものを削除)
$ docker container rm <CONTAINER_ID>

# コンテナの全削除
$ docker container rm $(docker container ls -a -q)

# 停止したコンテナの一括削除
$ docker container prune

# コンテナに入る(コンテナのbashを起動)
$ docker exec -it <CONTAINER_ID> bash
```
