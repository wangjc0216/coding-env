# common

## [yq](#yq)

[yq源码地址](https://github.com/mikefarah/yq)

yq安装

```
# 安装software-properties-common
apt install software-properties-common
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys CC86BB64
sudo add-apt-repository ppa:rmescandon/yq
sudo apt update
sudo apt install yq -y
```

[yq使用](https://lyyao09.github.io/2019/08/02/tools/The-usage-of-yq-read-write/)

使用示例：
```
kubectl get ing airflow -oyaml   | yq r - 
kubectl get ing airflow -oyaml   | yq r - spec
```


