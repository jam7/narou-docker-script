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

First time of execution, it downloads docker images named migimigi/narou.  It also initialize configuration something like:

```
$ narou list
Unable to find image 'migimigi/narou:latest' locally
latest: Pulling from migimigi/narou
d54efb8db41d: Pull complete 
f8b845f45a87: Pull complete 
e8db7bf7c39f: Pull complete 
9654c40e9079: Pull complete 
6d9ef359eaaa: Pull complete 
b6bcc4641e3e: Pull complete 
0634427bbb87: Pull complete 
746dc8c8dbd4: Pull complete 
32338345e63b: Pull complete 
fe4231fb54f8: Pull complete 
12ee4766ea36: Pull complete 
727c7e2f411d: Pull complete 
Digest: sha256:d5d5c643bfd18249fec3d81321808aa6ea3b5dff6f719b161093452341e3c6f4
Status: Downloaded newer image for migimigi/narou:latest
spawn narou init
.narou/ を作成しました
小説データ/ を作成しました
------------------------------
AozoraEpub3の設定を行います
                            !!!WARNING!!!                             
AozoraEpub3の構成ファイルを書き換えます。narouコマンド用に別途新規インストールしておくことをオススメします

AozoraEpub3のあるフォルダを入力して下さい:
(未入力でスキップ)
>/opt/AozoraEpub3

(次のファイルを書き換えました)
/opt/AozoraEpub3/chuki_tag.txt

(次のファイルをコピーor上書きしました)
/opt/AozoraEpub3/AozoraEpub3.ini
/opt/AozoraEpub3/template/OPS/css_custom/vertical_font.css
AozoraEpub3の設定を終了しました
初期化が完了しました！
現在のフォルダ下で各種コマンドが使用出来るようになりました。
まずは narou help で簡単な説明を御覧ください。
device を kindle に設定しました
端末をKindleに指定したことで、以下の関連設定が変更されました
  → default.enable_half_indent_bracket が true に変更されました
server-bind を * に設定しました
 ID  |  更新日  |      タイトル
```

## Where is data directory

All data are stored in `$HOME/.narou`

## How to use web UI

Run `narou web`.  Then connect to the machine using 8000 port.

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

@ 2016-2017 Kazushi (Jam) Marukawa, All rights reserved.

This project including all of its source files is released under the terms of [GNU General Public License (version 3 or later)](http://www.gnu.org/licenses/gpl.txt)

## Related projects

narou.rb is in https://github.com/whiteleaf7/narou.  
narou-docker is in https://github.com/migimigi/narou-docker.


