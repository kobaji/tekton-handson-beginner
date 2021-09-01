# kubectlインストール
公式のページの手順に従ってインストールしてください。

例：ubuntu

## minikube インストール手順

kubectlをインストールします。

詳細はこちらの手順を確認してください。

https://kubernetes.io/ja/docs/tasks/tools/install-kubectl/

実行コマンド
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```

## インストールの確認
インストールが実施されたかを確認します。

実行コマンド
```
kubectl version --client
```

実行結果
```
Client Version: version.Info{Major:"1", Minor:"22", GitVersion:"v1.22.0", GitCommit:"c2b5237ccd9c0f1d600d3072634ca66cefdf272f", GitTreeState:"clean", BuildDate:"2021-08-04T18:03:20Z", GoVersion:"go1.16.6", Compiler:"gc", Platform:"linux/amd64"}
```