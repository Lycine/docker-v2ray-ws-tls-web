# DEPRECATED. Followed by [crossfire-all-in-one](https://github.com/Abreto/crossfire-all-in-one).

# docker-v2ray-ws-tls-web
Docker Compose solution: v2ray + Caddy + openntpd.

**WARNING: `ntpd` service in this app would modify the time in host.**

English | [简体中文](./README-zh_CN.md)  

## Before (CentOS8)

### Install docker

```
curl https://download.docker.com/linux/centos/docker-ce.repo -o /etc/yum.repos.d/docker-ce.repo

yum install https://download.docker.com/linux/fedora/30/x86_64/stable/Packages/containerd.io-1.2.6-3.3.fc30.x86_64.rpm

yum install docker-ce

systemctl start docker
```

### Install docker-compose

```
sudo yum install -y epel-release

sudo yum install -y python3-pip

sudo pip3 install docker-compose --default-timeout=100

pip3 -V

docker-compose -version
```

## Usage

```
$ ./configure <UUID> <Host>

$ sudo docker-compose up -d
```

Then connect to `https://<Host>:443` via vmess over wss with `path: "/filesync"`.


# reference

https://www.cnblogs.com/ding2016/p/11592999.html

https://blog.csdn.net/weixin_42540340/article/details/104825212