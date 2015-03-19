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

## some tutorial command
```
docker run ubuntu:14.04 /bin/echo 'Hello world'
```
above command run on ubuntu-docker.Process will not alive future.
if will alive,i must use daemon

*** run daemon


### for example

```
{15-03-18 10:05}[ruby-2.1.0]server:~/nurse@pager✗✗✗✗✗✗ shiratsu% docker run ubuntu:14.04 /bin/echo 'Hello world'
Hello world
{15-03-18 10:28}[ruby-2.1.0]server:~/nurse@pager✗✗✗✗✗✗ shiratsu% docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
{15-03-18 10:28}[ruby-2.1.0]server:~/nurse@pager✗✗✗✗✗✗ shiratsu% docker run -d ubuntu:14.04 /bin/sh -c "while true; do echo hello world; sleep 1; done"
839feb723ad8a7957a26e07f763742621c2c4157ce6fb0d7bf0a38a04079b9ba
{15-03-18 10:29}[ruby-2.1.0]server:~/nurse@pager✗✗✗✗✗✗ shiratsu% docker ps
CONTAINER ID        IMAGE               COMMAND                CREATED             STATUS              PORTS               NAMES
839feb723ad8        ubuntu:14.04        "/bin/sh -c 'while t   About an hour ago   Up 2 seconds                            tender_nobel
```

## to login docker-hub by command
```
{15-03-19 11:58}[ruby-2.1.0]server:~@master✗✗✗✗✗✗ shiratsu% docker login
Username: xxxxx
Password:
Email: xxxxx@yahoo.co.jp
FATA[0033] Error response from daemon: Server Error: Post https://index.docker.io/v1/users/: dial tcp: lookup index.docker.io on 192.168.1.1:53: read udp 192.168.1.1:53: i/o timeout
```
* if above error produced,you should restart boot2docker
```
{15-03-19 11:59}[ruby-2.1.0]server:~@master✗✗✗✗✗✗ shiratsu% boot2docker stop
{15-03-19 14:29}[ruby-2.1.0]server:~@master✗✗✗✗✗✗ shiratsu% boot2docker start
Waiting for VM and Docker daemon to start...
.................ooo
Started.
Writing /Users/shiratsu/.boot2docker/certs/boot2docker-vm/ca.pem
Writing /Users/shiratsu/.boot2docker/certs/boot2docker-vm/cert.pem
Writing /Users/shiratsu/.boot2docker/certs/boot2docker-vm/key.pem
Your environment variables are already set correctly.

{15-03-19 14:30}[ruby-2.1.0]server:~@master✗✗✗✗✗✗ shiratsu% docker login
Username: xxxxx
Password:
Email: xxxxxx@yahoo.co.jp
Login Succeeded
```
### reference
https://github.com/docker/docker/issues/11490#issuecomment-83336706




