# mincraft_multi
自宅の Mac Mini(Intel CPU) に mincraft サーバーを建て、管理しています。

# 特徴
`SPIGOT` サーバーで起動しています。

以下のプラグインにより、クロスプレイを実現しています。
- Geyser-Spigot
- floodgate-spigot

# 準備
1. Mac Mini に Docker for Mac をインストール
1. Terminalを起動
1. 初回起動  
  `$ git clone https://github.com/mabubu0203/mincraft_multi.git`  
  `$ cp ./docker/.env.sample ./docker/.env`  
  `$ vi ./docker/.env`  
    設定修正  
  `$ docker-compose -f ./docker/docker-compose.yml up --build`  
  docker-composeのログより起動を確認  
  `$ docker-compose -f ./docker/docker-compose.yml stop`  
1. 設定修正  
  `$ vi ./docker/data/plugins/Geyser-Spigot/config.yml`    
    remote.auth-type: online -> floodgate  
  `$ vi ./docker/data/plugins/floodgate/config.yml`  
    覚えていない  
  `$ docker-compose -f ./docker/docker-compose.yml start`  
  docker-composeのログより起動を確認  

# 起動と停止
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
| Geyser-Spigot.jar | 2.0.4(2022/06/07) |  |
| floodgate-spigot.jar | 2.1.0(2022/03/22) |  |

# サーバー接続に必要な情報

グローバルIP or ダイナミックDNS

# 更新について

## mincraft本体(Spigot)

1. docker-compose.ymlを書き換えてブランチにpush
1. コンテナを停止
1. ブランチに切り替え
1. コンテナを起動

## プラグイン差し替え

1. docker-compose.ymlを書き換えてブランチにpush
1. コンテナを停止
1. ブランチに切り替え
1. コンテナを起動

## 変数変更

`$ vi ./docker/.env`