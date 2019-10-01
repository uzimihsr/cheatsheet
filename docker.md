# Docker cheatsheet

## image
```
# 現在のディレクトリにあるDockerfileでイメージをビルド
$ docker build -t name:tag .

# Dockerfileを指定してイメージをビルド(Dockerfile-sampleを使用する例)
$ docker build -t name:tag -f Dockerfile-sample

# イメージを実行
$ docker run name:tag
```

## container
```
# コンテナ一覧の確認
$ docker ps -a

# コンテナの停止(コンテナIDがCONTAINER_IDのものを停止)
$ docker stop CONTAINER_ID

# コンテナの削除(コンテナIDがCONTAINER_IDのものを削除)
$ docker rm CONTAINER_ID
```
