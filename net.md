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



