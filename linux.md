# linux cheatsheet

## network
```bash
# 正引き
$ dig <HOST_NAME>
# 逆引き
$ dig -x <IP_ADDRESS>
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
