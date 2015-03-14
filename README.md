# dockerとは
* 通常のサーバと違って、サーバのセットをファイルとして、扱えるようにしたもの
* Docker is able to handle server as file.

# dockerによってできること
* 例えば、リリース時にリリースサーバをdockerで作っておいて、それをどこかのサーバでインストール？してテスト
* テスト完了後にリリースすれば、より安全なリリースが可能に
* 

# to use docler on mac
* http://docs.docker.com/installation/mac/
* First of all,you should install boot2docker
* Maybe you should run follow command
```
% boot2docker init
% boot2docker up
```
* Maybe boot2docker will launch.then i am going to be able to use docker-command.

## about some error
* if this error occuered,you should check below link 
```
FATA[0000] Error: client and server don't have same version (client : 1.17, server: 1.15)
```
http://qiita.com/koudaiii/items/3dd26448ec3210338bba

## to check whether to run docker correctly
```
$ boot2docker status
$ docker version
```


