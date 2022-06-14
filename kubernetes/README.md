# Exastro OASE Kubernetes

## コンテナ起動(簡易版)

```bash

# Worker Nodeでボリュームを作成
mkdir -p /tmp/oase/{business-central/data,logs,mariadb/data,rabbitmq/data,share}
chmod -R 777 /tmp/oase

# GitHub から資材を取得
git clone https://github.com/exastro-suite/oase-container.git

# Exastro OASEをデプロイ
kubectl apply -f https://raw.githubusercontent.com/exastro-suite/oase-container/main/kubernetes.yaml

```

## コンテナ起動(カスタム版)

```bash

# GitHub から資材を取得
git clone https://github.com/exastro-suite/oase-container.git

# 環境に合わせてマニフェストファイルを修正する。
# oase-container/kubernetes/overlays 配下に kustomization.yaml を配置する

# Kustomize を使ってマニフェストファイルを適用
cd oase-container
kubectl apply -k kubernetes/overlays

```

