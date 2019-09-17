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

## Pod
```
# podの一覧表示
$ kubectl get pods

# podの状態をyaml形式で出力(pod-abcを見る)
$ kubectl get pods pod-abc -o yaml

# 作成されたpodの編集(vimでpod-abcを編集する場合)
$ export EDITOR=vim
$ kubectl edit pod pod-abc

# podの情報を見る(pod-abcを見る場合)
$ kubectl describe pod pod-abc

# podに入る(pod-abcでbashを使う)
$ kubectl exec -it pod-abc /bin/bash

# ログを流す(pod-abcのログを見る例)
$ kubectl logs pod-abc -f

# コンテナにファイルをコピー(ローカルのlocalfileをpod-abcの/tmp/newfileとしてコピーする例)
$ kubectl cp localfile pod-abc:/tmp/newfile

# コンテナへのポート転送(localhost:8888をpod-abcの80へ転送)
# Ctrl + Cで終了
$ kubectl port-forward pod-abc 8888:80
```

## ReplicaSet
```
# ReplicaSetの詳細情報を見る(rs-abcを見る)
$ kubectl describe rs rs-abc

# レプリカ数の変更(rs-abcのレプリカ数を5に変更)
$ kubectl scale rs rs-abc --replicas 5
```

## Deployment
```
# コンテナイメージを更新する(deployment-abcで使用するイメージnginx-containerをnginx:1.13に更新する)
$ kubectl set image deployment deployment-abc nginx-container=nginx:1.13

# アップデートの状況を見る(deployment-abcの状況を見る)
$ kubectl rollout status deployment deployment-abc

# アップデート履歴を見る(deployment-abcの履歴を見る)
$ kubectl rollout history deployment deployment-abc

# 1つ前のrevisionにロールバックする
$ kubectl rollout undo deployment deployment-abc
```
