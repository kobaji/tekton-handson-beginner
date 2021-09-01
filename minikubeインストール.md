# minikube インストール

公式のページの手順に従ってインストールしてください。

例：ubuntu


## docker　インストール手順

dockerとminikubeを利用するため以下のリソースをインストールします。
socatはTektonでport-fowardするために利用します。

実行コマンド
```
sudo apt-get update && sudo apt-get install docker.io -y && sudo apt-get install conntrack && sudo apt-get install socat
```

## minikube インストール手順

実行コマンド
```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

実行結果
```
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 65.9M  100 65.9M    0     0  52.6M      0  0:00:01  0:00:01 --:--:-- 52.6M
```

## インストールの確認

実行コマンド
```
minikube version
```

実行結果
```
minikube version: v1.22.0
commit: a03fbcf166e6f74ef224d4a63be4277d017bb62e
```


## minikube 起動
実行コマンド
```
sudo -i

minikube start --vm-driver=none
```


## 起動と接続の確認
実行コマンド
```
kubectl get node
```

実行結果
```
NAME               STATUS   ROLES                  AGE   VERSION
ip-172-31-46-104   Ready    control-plane,master   70s   v1.21.2
```