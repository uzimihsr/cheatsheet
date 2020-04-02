# linux cheatsheet

## file
```bash
# ディレクトリごと差分を表示する
$ diff -r <DIRECTORY_A> <DIRECTORY_B>
# 差分があったファイル名だけ表示する
$ diff -r <DIRECTORY_A> <DIRECTORY_B>
# ファイルの差分をvimでみる
$ vim -d <FILE_A> <FILE_B>
```

## network
```bash
# 正引き
$ dig <HOST_NAME> +short
# 逆引き
$ dig -x <IP_ADDRESS> +short
```

## yum
```bash
# 利用可能なパッケージを全部並べる
$ yum list
# 指定したパッケージの利用可能なバージョンを全て表示する
$ yum list --showduplicates <PACKAGE_NAME>
```

## awk
```bash
# 特定の列だけ抜き出す
$ echo "a b c d e" | awk '{print $1,$4}'
a d
```

## service
```bash
# 特定のUnitのログを見る
$ journalctl -xe -u <UNIT_NAME>
```
