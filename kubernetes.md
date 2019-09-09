# Kubernetes cheatsheet

## context
```
# 現在のcontextを確認
$ kubectl config current-context

# contextの切り替え(context-abcに切り替える例)
$ kubectl config use-context context-abc
```

## resource
```
# マニフェストを用いたリソースの作成(manifest-abc.yamlを使用する例)
$ kubectl create -f manifest-abc.yaml

# マニフェストを用いたリソースの削除(manifest-abc.yamlを使用する例)
$ kubectl delete -f manifest-abc.yaml

# リソースの種類と名前を指定したリソースの削除(pod-abcという名前のpodを削除する例)
$ kubectl delete pod pod-abc

# マニフェストを用いたリソースの更新(manifest-abc.yamlを使用する例)
$ kubectl apply -f manifest-abc.yaml
```

## pod
```
# podの一覧表示
$ kubectl get pods
```
