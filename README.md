# Exastro OASE Container

## OASEのみ利用したい場合
```bash
# GitHubから資材を取得
git clone https://github.com/exastro-suite/oase-container.git

cd oase-container

# networkを一つ作成
docker network create oase-monitoring

# logsディレクトリの権限を変更する
chmod 777 -R logs/

# 例: Exastro OASE コンテナの起動
docker-compose up -d
```

## OASEと監視アダプタを利用する場合

```bash
# GitHubから資材を取得
git clone https://github.com/exastro-suite/oase-container.git

cd oase-container

# networkを一つ作成
docker network create oase-monitoring

# logsディレクトリの権限を変更する
chmod 777 -R logs/

# 例1: Exastro OASE と Exastro IT Automation コンテナの起動
docker-compose --profile ita up -d

# 例2: Exastro OASE と Zabbix 連携用コンテナの起動
docker-compose --profile zabbix up -d

# 例3: Exastro OASE と Prometheus 連携用コンテナの起動
docker-compose --profile prometheus up -d

# 例4: Exastro OASE と Grafana 連携用コンテナの起動
docker-compose --profile grafana up -d

# 例5: Exastro OASE と Datadog 連携用コンテナの起動
docker-compose --profile datadog up -d

# 例6: Exastro OASE とメール連携用コンテナの起動
docker-compose --profile mail up -d

# 例7: Exastro OASE と Exastro IT Automation コンテナ、及び、監視アプリケーション連携用コンテナの起動
docker-compose --profile all up -d

# 例8: Exastro OASE と Exastro IT Automation コンテナ、及び、Zabbix 監視アプリケーション連携用コンテナの起動
docker-compose --profile ita --profile zabbix up -d

```

## Kubernetesを利用する場合

### コンテナ起動(簡易版)

```bash

# Worker Nodeでボリュームを作成
mkdir -p /tmp/oase/{business-central/data,logs,mariadb/data,rabbitmq/data,share}
chmod -R 777 /tmp/oase

# GitHub から資材を取得
git clone https://github.com/exastro-suite/oase-container.git

# Exastro OASEをデプロイ
kubectl apply -f https://raw.githubusercontent.com/exastro-suite/oase-container/main/kubernetes.yaml

```

### コンテナ起動(カスタム版)

```bash

# GitHub から資材を取得
git clone https://github.com/exastro-suite/oase-container.git

# 環境に合わせてマニフェストファイルを修正する。
# oase-container/kubernetes/overlays 配下に kustomization.yaml を配置する。

# Kustomize を使ってマニフェストファイルを適用
cd oase-container
kubectl apply -k kubernetes/overlays

```

