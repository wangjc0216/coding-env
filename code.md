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
5.GO Modules配置
go env -w GO111MODULE=auto
 

5.查看go安装情况
go version
```
ref: [Go官网](https://golang.org/dl/)

## [godoc](#godoc)
```shell
//在Go1.12版本之后，就不再默认安装godoc工具了，需要自己手动安装
go get -u -v golang.org/x/tools/cmd/godoc
//启动godoc服务
godoc -http=:6060
```
我们会发现，开源的包会提供一些代码示例(Example)，这个在godoc文档中也会有体现。


## [GCC](#GCC)
```
//centos
sudo yum install -y gcc
```

## [dlv](#dlv)

dlv 的安装：
```shell
go get -u github.com/go-delve/delve/cmd/dlv
dlv version
```
在相应的源码路径下，使用dlv：
```
//可以远程调试main函数 
dlv debug --headless --listen=:2345 --api-version=2 [main]|[main.go] 
//对main函数可以添加参数
dlv debug --headless --listen=:2345 --api-version=2 [main]|[main.go] -- -param1 p1 -param2 p2
//可以远程调试测试文件
dlv  test --headless --listen=:2345 --api-version=2
//可以远程调试可执行文件,wd代表执行文件所执行所在的目录
dlv  --headless --listen=:2345 --api-version=2 exec ./executeable  (--wd  workspace)  -- -param1 p1 -param2 p2 
```
需要了解，
```shell
//因为我们使用dlv调试，所以需要构建的时候需要阻止Go的优化内联等操作
go build -gcflags \"all=-N -l\" github.com/app/demo  
```


## [graphviz](#graphviz)
`graphviz`是开源的图形可视化软件，可以将抽象信息进行可视化(如Go中的prof文件可以使用graphviz进行可视化；如puml文件可以通过graphviz进行可视化)。
[官方链接](http://www.graphviz.org/)
```
//Mac

```

## [Chrome MYSQL Admin](#mysql)
`Chrome MYSQL Admin`是一个轻量的Mysql客户端，还可以计算吞吐量，收发字节数等。
[官方链接](https://chrome.google.com/webstore/detail/chrome-mysql-admin/ndgnpnpakfcdjmpgmcaknimfgcldechn/related)


## [Goland](#goland)

- [x] Docker 

需要在测试机让Docker可以远程连接TCP服务。在/etc/docker/daemon.json
```shell
{
 "hosts":[
    "tcp://0.0.0.0:2375"
  ],
 "registry-mirrors": ["http://f1361db2.m.daocloud.io"]
}
```
[相关参考](https://zhuanlan.zhihu.com/p/94224305)


- [x] Kubernetes 

Market可以下载并且配置.kube/config文件，即可使用
