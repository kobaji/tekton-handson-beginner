
# ハンズオン演習

## ファイルの準備
演習で使用するファイルを用意します。

tekton-handson/pipeline


```
sudo -i
https://github.com/kenta-fukushima-jb/tekton-handson-beginner.git
cd tekton-handson
```
## 演習１
パイプラインリソースを追加します。
Task実行の流れやparamsの受け渡しを確認してください。
```
kubectl create ns cnd-co-located-handson
kubectl -n cnd-co-located-handson apply -f pipeline/exercise-1
```


## 演習２
パイプラインリソースを追加します。
Pipeline実行の流れやWorkspace（Secret,PVC)の操作方法を確認してください。
```
kubectl -n cnd-co-located-handson apply -f pipeline/exercise-2
```

## 演習３
パイプラインリソースを追加します。
Trigger実行の流れを確認してください。
```
kubectl -n cnd-co-located-handson apply -f pipeline/exercise-3
```

## パイプラインの稼働確認
EventListenerにイベントを手動で投げるためPortForwardをします。
PortForwardを実施するため再度セッションの複製をしてください。
```
kubectl -n cnd-co-located-handson port-forward svc/el-handson-eventlistener 8080:8080
```

## イベントの送信

イベントを送信し、Tekton Dashboardで動作を確認してください。
```
curl --location --request POST 'localhost:8080' \
--header 'Content-Type: application/json' \
--data-raw '{
    "commits": [
        {
            "message": "update"
        }
    ],
    "ref": "refs/heads/main"
}'
```

以下の結果がTekton Dashboard上で表示されればOKです。
```
Hello World! CloudNative Days CI/CD HandsOn
```

こちらで終了です。お疲れ様でした。

[戻る](README.md)
