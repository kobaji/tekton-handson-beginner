# Tekton インストール

ハンズオンに必要なリソースをインストールします。

## Tekton Pipeline インストール
pipeline v0.26.0をインストールする手順です。

公式のインストール手順はこちら

https://github.com/tektoncd/pipeline/releases
```
kubectl apply -f https://storage.googleapis.com/tekton-releases/pipeline/previous/v0.26.0/release.yaml
```
## Tekton Trriger  インストール
trriger v0.15.0をインストールする手順です。

公式のインストール手順はこちら

https://github.com/tektoncd/triggers/releases
```
kubectl apply -f https://storage.googleapis.com/tekton-releases/triggers/previous/v0.15.0/release.yaml
kubectl apply -f https://storage.googleapis.com/tekton-releases/triggers/previous/v0.15.0/interceptors.yaml
```
## Tekton Dashboard インストール
Dashboard v0.18.0をインストールする手順です。

公式のインストール手順はこちら

https://github.com/tektoncd/dashboard/releases
```
kubectl apply --filename https://storage.googleapis.com/tekton-releases/dashboard/previous/v0.19.0/tekton-dashboard-release.yaml
```

## 稼働の確認
すべて動き出したらOK
```
kubectl get pod -n tekton-pipelines
```

実行結果
```
NAME                                                 READY   STATUS    RESTARTS   AGE
tekton-dashboard-5fdd465495-v9qh2                    1/1     Running   0          91s
tekton-pipelines-controller-78d8d6d4b-rj4qj          1/1     Running   0          112s
tekton-pipelines-webhook-64fd67d65-4z42r             1/1     Running   0          112s
tekton-triggers-controller-6c7c9cfd47-bltkr          1/1     Running   0          100s
tekton-triggers-core-interceptors-5b6f7b6c56-mcj5m   1/1     Running   0          96s
tekton-triggers-webhook-7f5c9477cc-sx54x             1/1     Running   0          100s
```

## ダッシュボードへの接続
コマンドを実行後ブラウザで以下のURLに接続できたらOK

```
kubectl -n tekton-pipelines port-forward svc/tekton-dashboard 9097:9097
```

### Tera TermでSSH転送の設定

「設定」⇒「SSH転送」⇒「追加」を選択し、以下を設定してください。

| 項目 | 内容 |
| -------- | -------- |
| ローカルのポート     | 9097     |
| リモート側ホスト　ポート | 907 |

### Tekton Dashboardの表示

以下のURLをブラウザで開きます。

http://localhost:9097/

### セッションの複製
SSH転送をすると端末が操作できなくなります。

そのためTera Termの操作画面を以下の操作で増やしてください。

- 「ファイル」⇒「セッションの複製」を選択

次は[こちら](Tekton実践.md)です。