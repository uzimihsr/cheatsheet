# Kubernetes cheatsheet

## autocompletion
```
# zshで補完を効かせる
$ source <(kubectl completion zsh)
$ echo 'source <(kubectl completion zsh)' >> ~/.zprofile
```

## context
```
# 現在のcontextを確認
$ kubectl config current-context

# contextの切り替え(context-abcに切り替える例)
$ kubectl config use-context context-abc
```

## resource
```
# マニフェストを用いたリソースの作成/更新(manifest-abc.yamlを使用する例)
# createよりapplyのほうが使い勝手が良い
$ kubectl apply -f manifest-abc.yaml

# 同じ階層にある全てのマニフェストを用いたリソースの作成/更新
$ kubectl apply -f ./

# マニフェストを用いたリソースの削除(manifest-abc.yamlを使用する例)
$ kubectl delete -f manifest-abc.yaml

# リソースの種類と名前を指定したリソースの削除(pod-abcという名前のpodを削除する例)
$ kubectl delete pod pod-abc

# 全てのリソースを表示
$ kubectl get all
```

## pod
```
# podの一覧表示
$ kubectl get pods

# 作成されたpodの編集(vimでpod-abcを編集する場合)
$ export EDITOR=vim
$ kubectl edit pod pod-abc

# podの情報を見る(pod-abcを見る場合)
$ kubectl describe pod pod-abc

# podに入る(pod-abcでbashを使う)
$ kubectl exec -it pod-abc /bin/bash

# ログを流す(pod-abcのログを見る例)
$ kubectl logs pod-abc

# コンテナにファイルをコピー(ローカルのlocalfileをpod-abcの/tmp/newfileとしてコピーする例)
$ kubectl cp localfile pod-abc:/tmp/newfile

# コンテナへのポート転送(localhost:8888をpod-abcの80へ転送)
# Ctrl + Cで終了
$ kubectl port-forward pod-abc 8888:80
```
