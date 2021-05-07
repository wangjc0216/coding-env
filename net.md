# 网络

## [iperf](#iperf)
iperf是一个网络性能测试工具，可以测试TCP和UDP带宽质量，可以测量最大TCP带宽，具有多种参数和UDP特性。
可以报告带宽，延迟抖动和数据包丢失。**可以用来测试一些网络设置如路由器、防火墙、交换机等的性能。**

使用iperf来测试网络速度和带宽。分别在两台机器上测试，一台作为服务器，另一台作为客户端。
```
//centos
sudo yum install -y iperf
iperf -s 
iperf -c 192.168.9.105

➜  ~ iperf -s
------------------------------------------------------------
Server listening on TCP port 5001
TCP window size: 85.3 KByte (default)
------------------------------------------------------------
[  4] local 10.0.0.199 port 5001 connected with 192.168.9.36 port 46314
[ ID] Interval       Transfer     Bandwidth
[  4]  0.0-10.0 sec   923 MBytes   773 Mbits/sec


[centos@master ~]$ iperf -c 192.168.9.105
------------------------------------------------------------
Client connecting to 192.168.9.105, TCP port 5001
TCP window size:  272 KByte (default)
------------------------------------------------------------
[  3] local 10.0.0.108 port 46314 connected with 192.168.9.105 port 5001
[ ID] Interval       Transfer     Bandwidth
[  3]  0.0-10.0 sec   923 MBytes   773 Mbits/sec
```
ref: [Linux下3种常用的网络测速工具](https://juejin.cn/post/6844904152108105742)



## [tcpdump](tcpdump)

tcpdump是通过libpcap来抓取报文的，libpcap在不同平台有不同的实现。

//todo 在极客时间记得有张图片来描述tcpdump的抓包逻辑
```
//centos tcpdump的安装
yum install -y tcpdump 
//将从eth0网卡传出，且目的地址为198的网络包 输出到198.pcap文件中，后续可以使用wireshark/termshark来解析
tpducmp -ni eth0 dst 10.0.0.198 -w 198.pcap
//将从eth0网卡传出，目的地址为192.168.100.4，端口为8080（目的端口或者源端口），tcp协议
sudo tcpdump -i eth0 '((tcp) and (port 8080) and (dst host 192.168.100.4 )  )'
```

## [termshark](termshark)
termshark就是linux终端版本的wireshark
```
//使用go get 来进行安装
go get github.com/gcla/termshark/v2/cmd/termshark
//termshark用以分析test.pcap文件
termshark -r test.pcap
//termshark也可以做抓包分析
termshark -i eth0 
```

## [httpstat](httpstat)
httpstat 是 dave chenney编写的网络请求工具
```shell
//使用go get进行安装
go get github.com/davecheney/httpstat
```
ref： [项目地址](https://github.com/davecheney/httpstat)


## [httpie](httpie)
httpie 是JSON格式支持、语法高亮、持久化会话、wget-like、插件等等。
```shell
//CentOS
yum install -y httpie
//Mac
brew install httpie
//一些使用
http github.com

http -v github.com

http -v PUT  httpbin.org/put hello=world1
```
ref: [项目地址](https://httpie.io/)