# Docker cheatsheet

## image
```
# 現在のディレクトリにあるDockerfileでイメージをビルド
# reponame:tagをつける
$ docker image build -t reponame:tag .

# Dockerfileを指定してイメージをビルド(Dockerfile-sampleを使用する例)
# reponame:tagをつける
$ docker image build -t reponame:tag -f Dockerfile-sample

# Docker Hub用にイメージにタグを付け直す
# ローカルのrepo_old:1.0にdocker_id/repo_new:2.0タグをつける
$ docker image tag repo_old:1.0 docker_id/repo_new:2.0

# 全イメージを表示
$ docker image ls -a

# イメージ削除
$ docker image rm IMAGE_ID

# イメージ全削除
$ docker image rm $(docker image ls -a -q)

# 一時的にイメージ(IMAGE_NAME)に入る
$ docker container run --rm -it IMAGE_NAME /bin/bash
```

## container
```
# イメージ(reponame:tag)を使用してコンテナを起動
$ docker container run reponame:tag

# コンテナ一覧の確認
$ docker container ls -a

# コンテナの停止(コンテナIDがCONTAINER_IDのものを停止)
$ docker container stop CONTAINER_ID

# コンテナの削除(コンテナIDがCONTAINER_IDのものを削除)
$ docker container rm CONTAINER_ID

# コンテナの全削除
$ docker container rm $(docker container ls -a -q)

# 停止したコンテナの一括削除
$ docker container prune

# コンテナに入る(コンテナのbashを起動)
$ docker exec -it CONTAINER_ID bash
```
