# DEPRECATED. Followed by [crossfire-all-in-one](https://github.com/Abreto/crossfire-all-in-one).

# docker-v2ray-ws-tls-web
Docker Compose solution: v2ray + Caddy + openntpd.

**WARNING: `ntpd` service in this app would modify the time in host.**

[English](./README.md) | 简体中文

## 开始之前（基于CentOS8）

### 安装 docker docker 

```
# 下载官方repo
sudo curl https://download.docker.com/linux/centos/docker-ce.repo -o /etc/yum.repos.d/docker-ce.repo

# 下载依赖
sudo yum install https://download.docker.com/linux/fedora/30/x86_64/stable/Packages/containerd.io-1.2.6-3.3.fc30.x86_64.rpm

# 安装
sudo yum install docker-ce

# 开机启动
sudo systemctl start docker
```

### 安装 docker-compose

```
# 安装 epel
sudo yum install -y epel-release

# 安装pip（CentOS默认安装的是python3，所以安装python3-pip）
sudo yum install -y python3-pip

# 安装 docker-compose
sudo pip3 install docker-compose --default-timeout=100

# 查看版本
sudo pip3 -V

# 查看版本
sudo docker-compose -version
```

## 使用方法

### 获取一个UUID

可以通过 https://www.guidgen.com/ 得到

### 获取一个域名

有域名的话在访问的时候会很方便

可以通过 https://www.freenom.com/ 申请一个最长为期一年的免费域名

得到域名后需要对域名进行解析，增加一条A记录指向服务器IP地址

### 运行

 &lt;UUID&gt; 换成刚获取的UUID

 &lt;HOST&gt; 换成申请的域名 


此服务会自动通过caddy申请https证书，这样就可以通过https来访问了，这样流量是经过加密的，在检测的时候和普通https流量特征相同，不容易被检测到。

```
$ ./configure <UUID> <Host>
```
启动服务
```
$ sudo docker-compose up -d
```

这个时候可以用客户端进行链接
比如 https://www.v2ray.com/awesome/tools.html
Then connect to `https://<Host>:443` via vmess over wss with `path: "/filesync"`.


# reference

https://www.cnblogs.com/ding2016/p/11592999.html

https://blog.csdn.net/weixin_42540340/article/details/104825212

https://github.com/wubaiqing/v2ray-docker-compose