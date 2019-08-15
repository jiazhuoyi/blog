---
title: linux上的常用操作(便于自查)
date: 2019-06-18 14:14:13
tags: linux，centos，nginx， firewall

---

## linux的常用操作(centos7, 仅用于自查)

### 1.nginx

重启nginx：**nginx -s reload**

快速停止nginx：**nginx  -s stop**

正常停止或关闭nginx：**nginx -s quit**

查询nginx进程：**ps  -ef | grep nginx**

### 2.firewall

查看版本：fire-wall-cmd --version

查询ip列表： firewall-cmd --zone=public --list-ports

打开4000端口：firewall-cmd --zone=public --add-port=4000/tcp --permanent

重启防火墙：firewall-cmd --reload

删除端口:  firewall-cmd --zone=public --remove-port=4000/tcp --permanent

### 3.shell

// TODO

### 4.mongodb

// TODO

### 5.redis

// TODO