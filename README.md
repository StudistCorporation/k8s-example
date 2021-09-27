# k8s-tutorial

このリポジトリは、スタディストで使われているk8sやk8s周辺のツールについて学ぶためのものです。

## Requirements

- Docker ... 20.10.7 or greater
- kind ... v0.11.1 or greater
- kubectl ... v1.21.2 or greater

## セットアップ

### クラスタを作成する

今回のチュートリアルで使用する`k8s-tutorial`クラスタを作成します。

```sh
kind create cluster --name k8s-tutorial --config kindconfig.yaml
```

### Nginx Ingress Controllerをインストールする

作成したクラスタにNginx Ingress Controllerをインストールします。

```sh
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

### 動作確認

作成したクラスタに対してマニフェストを適用してページが確認できることを確認します。  
クラスタにマニフェストを適用後、[echo.lvh.me](http://echo.lvh.me)にアクセスしてページが表示されれば成功です。

```sh
kubectl apply -f echo-server/main.yaml
```

## ティアダウン

### クラスタを削除する

作成したクラスタを削除します。

```sh
kind delete cluster --name k8s-tutorial
```

## チュートリアル

TBD
