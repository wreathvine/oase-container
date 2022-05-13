# oase-container

## イメージのビルド

```bash
# GitHubから資材を取得
git clone https://github.com/exastro-suite/oase-container.git
```

次のコマンドを順に実行する

```bash
# 対象のバージョンに合わせる
OASE_VERSION="v1.6.0"

# oase-baseのビルド
OASE_VERSION=$OASE_VERSION COMPOSE_PROFILES=base docker-compose build --no-cache

# oase-backyardのビルド
OASE_VERSION=$OASE_VERSION COMPOSE_PROFILES=backyard docker-compose build --no-cache

# これらの資材をベースとする各サービスのイメージを作成
OASE_VERSION=$OASE_VERSION COMPOSE_PROFILES=build docker-compose build --no-cache
```

latestタグを付与

```awk
for i in `docker images | grep $OASE_VERSION | awk '{print $1}'`; do docker tag $i:$OASE_VERSION $i:latest; done
```

pushを行う
```bash
# バージョンタグの資材のpush
COMPOSE_PROFILES=push OASE_VERSION=$OASE_VERSION docker-compose push

# latestタグの資材のpush
COMPOSE_PROFILES=push OASE_VERSION=latest docker-compose push