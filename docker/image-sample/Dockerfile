# ベースとなるイメージ(latestタグのalpine Linux)を取得
FROM alpine:latest

# 作成するイメージの作者を設定
MAINTAINER uzimihsr

# 動作するディレクトリを変更(無い場合は作成される)
WORKDIR ~/workspace

# Dockerfileと同じ階層のファイルをイメージに追加
COPY ./parrot.sh ./

# イメージ実行前に必要なコマンドを記述
RUN mv parrot.sh return.sh; \
    chmod +x ./return.sh

# オウム返しを実行
# docker run時に引数が渡された場合は上書きされる
ENTRYPOINT ["./return.sh"]
