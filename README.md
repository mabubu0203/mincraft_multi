# mincraft_multi
自宅の Mac Mini に mincraft サーバーを建て、管理しています。

# 特徴
`SPIGOT` サーバーで起動しています。

以下のプラグインにより、クロスプレイを実現しています。
- Geyser-Spigot
- floodgate-spigot

# 準備
1. Mac Mini に Docker for Mac をインストール
1. `git clone https://github.com/mabubu0203/mincraft_multi.git`
1. Terminalをたちあげる

# 初期セットアップ
以下、 Terminal にて

1. `$ docker-compose -f ./docker/docker-compose.yml up --build`
1. docker-composeのログより起動を確認
1. プラグインを導入
  1. `curl -L https://ci.opencollab.dev//job/GeyserMC/job/Geyser/job/master/lastSuccessfulBuild/artifact/bootstrap/spigot/target/Geyser-Spigot.jar > ./docker/data/plugins/Geyser-Spigot.jar`
  1. `curl -L https://ci.opencollab.dev//job/GeyserMC/job/Floodgate/job/master/lastSuccessfulBuild/artifact/spigot/target/floodgate-spigot.jar > ./docker/data/plugins/floodgate-spigot.jar`
1. `$ docker-compose -f ./docker/docker-compose.yml stop`
1. `$ docker-compose -f ./docker/docker-compose.yml start`

以降は、

start -> `$ docker-compose -f ./docker/docker-compose.yml start`
stop -> `$ docker-compose -f ./docker/docker-compose.yml stop`

# ディレクトリ構成

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

# プラグイン

| name | version | 用途 |
| - | - | - |
| Geyser-Spigot.jar | 2.0.3(2022/05/15) |  |
| floodgate-spigot.jar | 2.1.0(2022/03/22) |  |

# サーバー接続に必要な情報

WIP