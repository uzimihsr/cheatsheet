# Kubernetes cheatsheet

## autocompletion
```bash
# zshで補完を効かせる
$ source <(kubectl completion zsh)
$ echo 'source <(kubectl completion zsh)' >> ~/.zshrc
```

## context
```bash
# contextの一覧を表示
$ kubectl config get-context

# 現在のcontextを確認
$ kubectl config current-context

# contextの切り替え
$ kubectl config use-context <CONTEXT_NAME>
```

## namespace
```bash
# namespaceを変更
$ kubectl config set-context $(kubectl config current-context) --namespace=<NAMESPACE>
```

## event
```bash
# クラスタのイベントを表示
$ kubectl get events
```

## proxy
```bash
# ローカルマシンからKubernetes APIに接続するためのproxyを起動
$ kubectl proxy
# 使い終わったらCtrl + Cで終了
```

## resource
```bash
# マニフェスト(manifest.yaml)を用いたリソースの作成/更新
$ kubectl apply -f manifest.yaml

# 同じ階層にある全てのマニフェストを用いたリソースの作成/更新
$ kubectl apply -f ./

# マニフェスト(manifest.yaml)を用いたリソースの削除
$ kubectl delete -f manifest.yaml

# リソースの種類と名前を指定したリソースの削除
$ kubectl delete <RESOURCE_TYPE> <RESOURCE_NAME>

# 全てのリソースを表示
$ kubectl get all

# リソースの詳細を表示
$ kubectl describe <RESOURCE_TYPE> <RESOURCE_NAME>

# リソースの種類を指定して一覧を表示
$ kubectl get <RESOURCE_TYPE>
```

## Pod
```bash
# Podの一覧表示
$ kubectl get pods

# Podの一覧表示(情報が増える)
$ kubectl get pods -o wide

# ラベルで指定してPodを取得
$ kubectl get pods -l <LABEL_KEY>=<LABEL_VALUE>

# Podの状態をyaml形式で出力
$ kubectl get pods <POD_NAME> -o yaml

# 作成されたPodの編集(vimを使用)
$ export EDITOR=vim
$ kubectl edit pod <POD_NAME>

# Podにラベルを付与
$ kubectl label pod <POD_NAME> <LABEL_KEY>=<LABEL_VALUE>

# Podの情報を見る
$ kubectl describe pod <POD_NAME>

# Podに入る
$ kubectl exec -it <POD_NAME> /bin/bash

# Podのログを流す
$ kubectl logs <POD_NAME> -f

# Pod内のコンテナを指定してログを見る
$ kubectl logs <POD_NAME> -c <CONTAINER_NAME>

# コンテナにファイルをコピー(ローカルのファイルをPodにコピーする例)
$ kubectl cp <LOCAL_FILE> <POD_NAME>:<PATH_TO_FILE>

# コンテナへのポート転送(localhost:8888をPodの80番ポートへ転送)
# Ctrl + Cで終了
$ kubectl port-forward <POD_NAME> 8888:80
```

## ReplicaSet
```bash
# レプリカ数の変更
$ kubectl scale rs <REPLICA_SET_NAME> --replicas <NUM_REPLICAS>
```

## Deployment
```bash
# マニフェストファイルを使わずにDeploymentを作成
$ kubectl create deployment <DEPLOYMENT_NAME> --image=<REPOSITPRY>:<TAG>

# Deploymentで使用しているイメージを更新する
$ kubectl set image deployment <DEPLOYMENT_NAME> <IMAGE_NAME>=<REPOSITORY>:<TAG>

# Deploymentのレプリカ数を変更する
$ kubectl scale deployments/<DEPLOYMENT_NAME> --replicas=<NUM_REPLICAS>

# アップデートの状況を見る
$ kubectl rollout status deployment <DEPLOYMENT_NAME>

# アップデート履歴を見る
$ kubectl rollout history deployment <DEPLOYMENT_NAME>

# 1つ前のrevisionにロールバックする
$ kubectl rollout undo deployment <DEPLOYMENT_NAME>
```

## Service
```bash
# マニフェストファイルを使わずにNodePort Serviceを作成
$ kubectl expose deployment/<DEPLOYMENT_NAME> --type="NodePort" --port 8080
```

## Job
```bash
# CronJobからJobを生成する
$ kubectl create job <JOB_NAME> --from=cronjob/<CRONJOB_NAME>
```

## CronJob
```bash
# CronJobを一時停止する
$ kubectl patch cronjob <CRONJOB_NAME> -p '{"spec":{"suspend":true}}'
```

## stern
```bash
# Podのログを時刻付きで出力する
$ stern -t <POD_NAME_QUERY>
```
