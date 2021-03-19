# Code

## [Go](#Go)

```
//centos
1. 下载需要的版本，有一些项目对Go版本有一定要求  https://golang.org/dl/
2. 对压缩包解压并安装，例如： rm -rf /usr/local/go && tar -C /usr/local -xzf go1.16.2.linux-amd64.tar.gz
3. 在/etc/profile中配置环境变量，如：
...
export GOPATH=/home/centos/gopath
export PATH=$PATH:$GOPATH:/usr/local/go/bin

4.设置代理(在较高版本都需要GOPROXY)
go env -w GOPROXY=https://goproxy.cn,direct

5.查看go安装情况
go version
```
ref: [Go官网](https://golang.org/dl/)


## [GCC](#GCC)
```
//centos
sudo yum install -y gcc
```
