# Exastro OASE Kubernetes

## マニフェストファイル作成

```bash
# GitHub から資材を取得
git clone https://github.com/exastro-suite/oase-container.git

# Kustomize を使ってマニフェストファイルを生成
cd oase-container
kubectl kustomize kubernetes/base > kubernetes.yaml
```

## デプロイ

```bash
# 方法1) 一般的なデプロイ
kubectl apply -f https://raw.githubusercontent.com/exastro-suite/oase-container/main/kubernetes.yaml

# 方法2) ユーザがカスタマイズしたマニフェストのデプロイ
kubernetes 
```