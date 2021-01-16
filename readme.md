# Kubernetesのお勉強

## 環境
- docker desktop for mac: 3.0.4
  - kubernetes: v1.19.3
  - Docker Engine: v20.10.2

## 勉強内容
- コンテナは揮発性を持つため，コンテナが削除された場合はデータが削除されてしまう
  - そのため，アプリはステートレスになるよう設計し，データは外部で永続化する必要がある
- 最近はDBをコンテナで運用し始める機運が高まっており，コンテナで状態を持つ必要性が出ている
- kubernetesでは状態を保存するための仕組みとして以下を提供している
  - StorageClass: Volumeの生成元となるストレージ定義
  - PersistentVolume: 保存先Volumeの具体的な仕様定義
  - PersistentVolumeClaim: Podが要求するVolumeの仕様

## デモ環境
- nginxのログ情報をVolumeに保存する

```bash
kubectl apply -f pv.yaml
kubectl apply -f pvc.yaml
kubectl apply -f pod.yaml
kubectl apply -f service.yaml
```

