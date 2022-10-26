# Bitwarden server

## 使い方

### Bitwarden の管理
#### スクリプトを用いる方法
1. 起動
```shell
$ launch.sh start
```
2. 起動 (バックグラウンドで動作させる場合)
```shell
$ launch.sh start -d
```
3. 起動 (ポートを指定する場合)
```shell
$ launch.sh start -p 80
```
4. 停止
```shell
$ launch.sh stop
```
5. 再起動
```shell
$ launch.sh restart -d -p 80
```
6. ステータス確認
```shell
$ launch.sh status
```

より詳細な使い方については以下のコマンドを実行
```shell
$ launch.sh help
```

#### systemd を用いる手法
+ 事前準備
    1. `systemd_conf/bitwarden.service` を `/etc/systemd/system` にコピー
    ```shell
    # cp systemd_conf/bitwarden.service /etc/systemd/system/
    ```
    2. コピーした `bitwarden.service` を書き換える
    ```shell
    # vim /etc/systemd/system/bitwarden.service
    ```
+ 管理
    + 起動
    ```shell
    # systemctl start bitwarden.service
    ```
    + 停止
    ```shell
    # systemctl stop bitwarden.service
    ```
    + ステータス確認
    ```shell
    # systemctl status bitwarden.service
    ```
    + 自動起動
    ```shell
    # systemctl enable bitwarden.serive
    ```
