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
```

## How to use mail

First, run `narou mail`.  Then edit your `$HOME/.narou/mail_setting.yaml` file.

## License

@ 2016-2017 Kazushi (Jam) Marukawa, All rights reserved.

This project including all of its source files is released under the terms of [GNU General Public License (version 3 or later)](http://www.gnu.org/licenses/gpl.txt)

## Related projects

narou.rb is in https://github.com/whiteleaf7/narou.  
narou-docker is in https://github.com/migimigi/narou-docker.


