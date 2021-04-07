# 编码环境

## 编写目的

对于开发环境的一个整理集成。方便在分配到新的测试机后快速适配环境。


## 容器 

- [ ] docker
- [ ] kubernetes
>注： 这里为rancher2.2 部署的Kubernetes v1.19版本

## 软件包管理
- [ ] yum
- [ ] apt

## 开发环境
- [x] [Go](code.md#Go):Go编译器
  
- [ ] [godoc](code.md#godoc):godoc 
- [ ] [gv]: pprof 相关视图
- [x] [GCC](code.md#GCC):C编译器
- [x] [dlv](code.md#dlv):Go调试工具
- [ ] [Git](git.md):最常用的版本控制系统
- [ ] [graphviz](code.md#graphviz): 常用的图形可视化工具
# 运维

### 网络

- [x] [tcpdump](net.md#tcpdump):网络抓包
- [x] [termshark](net.md#termshark):linux终端版本的wireshark
- [ ] iftop
- [x] [iperf](net.md#iperf)：测试网速与带宽.
- [x] ifconfig/ip addr

### 磁盘
- [x] [duf](disk.md#duf):查看磁盘信息
- [x] df

### 内存 CPU
- [x] top
- [ ] htop




