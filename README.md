# mincraft_multi
自宅でmincraftサーバーを建て、管理する

# 特徴
papper サーバーで起動しています。
プラグインに「」「」を利用しているため、クロスプレイが行えます。

# 準備
1. Docker for Macをインストール
1. このプロジェクトをクローン

# 実施
1. `$ docker-compose -f ./docker/docker-compose.yml up -d`
1. `$ docker-compose -f ./docker/docker-compose.yml down`

# 構成

```bash
root
- docker
  - data
    - cache
    - logs
    - plugins
    - world
    - world_nether
    - world_the_end
  - mc-backups
- README.md
```