# Narou-docker-script is merged into [narou-docker-alpine](https://github.com/jam7/narou-docker-alpine).

# narou-docker-script
A narou script in order to run narou-docker transparently / narou-dockerを透過的に実行するスクリプト

## Prerequisite

Need to install docker.

## Install

Copy narou script to your facorite binary directory.

```
$ wget https://raw.githubusercontent.com/jam7/narou-docker-script/master/narou -O $HOME/bin/narou
$ chmod a+x $HOME/bin/narou
```

## Usage

Run narou script as narou like:

```
$ narou l
$ narou download
$ narou mail
```

First time of execution, it downloads docker images named jam7/narou-alpine and configure narou environment like below:

```
$ narou list
Unable to find image 'jam7/narou-alpine:latest' locally
latest: Pulling from jam7/narou-alpine
627beaf3eaaf: Already exists
1de20f2d8b83: Already exists
74e619d34827: Already exists
5ce74db8fefd: Pull complete
a67c897e7e75: Pull complete
ca7d3d9dc7e1: Pull complete
e0bbdd03fe58: Pull complete
f06199afada5: Pull complete
f800562d9d65: Pull complete
4621b6cf5865: Pull complete
Digest: sha256:af9520cc65ad8f53e60a3b779e912de2a5d534e00a4b8fa59e4748707265cd14
Status: Downloaded newer image for jam7/narou-alpine:latest
.narou/ を作成しました
小説データ/ を作成しました
------------------------------
AozoraEpub3の設定を行います
                            !!!WARNING!!!
AozoraEpub3の構成ファイルを書き換えます。narouコマンド用に別途新規インストールしておくことをオススメします

(次のファイルを書き換えました)
/opt/narou/AozoraEpub3/chuki_tag.txt

(次のファイルをコピーor上書きしました)
/opt/narou/AozoraEpub3/AozoraEpub3.ini
/opt/narou/AozoraEpub3/template/OPS/css_custom/vertical_font.css
AozoraEpub3の設定を終了しました
初期化が完了しました！
現在のフォルダ下で各種コマンドが使用出来るようになりました。
まずは narou help で簡単な説明を御覧ください。
device を kindle に設定しました
端末をKindleに指定したことで、以下の関連設定が変更されました
  → default.enable_half_indent_bracket が true に変更されました
 ID  |  更新日  |      タイトル

```

## Where is data directory

All data are stored in `$HOME/.narou`

## How to use web UI

Run `narou web`.  Then connect to port 8000 of the docker host.
It is required to use direct connection without proxies since
push_server uses port 8001 which doesn't use http.

## How to convert narou-syousetsu with images

Run `narou download` or `narou convert`.  `jam7/narou-alpine` image uses
modified AozoraEpub3 which run well with OpenJDK.  Modification is
already filed as PR.

## How to use mail

First, run `narou mail`.  Then edit your `$HOME/.narou/mail_setting.yaml` file.

```
$ narou mail
created /opt/narou/mail_setting.yaml
メールの設定用ファイルを作成しました。設定ファイルを書き換えることで mail コマンドが有効になります。
注意：次回以降のupdateで新着があった場合に送信可能フラグが立ちます
設定ファイルがあるフォルダを開きますか (y/n)?: n
```

## License

@ 2017 Kazushi (Jam) Marukawa, All rights reserved.

This project including all of its source files is released under the terms of [GNU General Public License (version 3 or later)](http://www.gnu.org/licenses/gpl.txt)

## Related projects

narou.rb is in https://github.com/whiteleaf7/narou.  
narou-docker is in https://github.com/migimigi/narou-docker.  
narou-docker-alpine is in https://github.com/jam7/narou-docker-alpine.
