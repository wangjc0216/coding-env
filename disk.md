# 磁盘

## [duf](#duf)

duf是一款golang编写的磁盘信息查看工具，可以查看磁盘总空间、剩余空间、inodes、挂载点等等，可以算是df -hT的高级版吧。

GITHUB：https://github.com/muesli/duf
```
//centos
wget https://github.com/muesli/duf/releases/download/v0.5.0/duf_0.5.0_linux_amd64.rpm
sudo rpm -ivh duf_0.5.0_linux_amd64.rpm
```
ref: [分享一款高逼格的Linux磁盘信息查看工具](https://mp.weixin.qq.com/s/pKMZDaurweBSRlaEYtq5tw)

## [ncdu](#ncdu)
du(disk usage)是linux查看目录占用磁盘空间的linux命令。ncdu是基于du的命令，可视化效果比du更好
```shell
//MacOS
brew install 
//ubuntu
sudo apt install ncdu
//centos
sudo yum install ncdu
```
ref: [How to install ncdu on Linux / Unix to see disk usage](https://www.cyberciti.biz/open-source/install-ncdu-on-linux-unix-ncurses-disk-usage/)