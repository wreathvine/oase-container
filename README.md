# oase-container

## OASE起動方法

```bash
# GitHubから資材を取得
git clone https://github.com/exastro-suite/oase-container.git

# networkを一つ作成
docker network create oase-monitoring

# 次のコマンドで起動
cd oase-container
docker-compose up -d

# 監視アダプタを利用する場合
docker-compose -f docker-compose.yml -f docker-compose.zabbix.yml up -d
```
