---
title: ubuntu搭建shadowsocks服务
date: 2018-02-27 13:25:39
categories: 
- 成长日记
tags:
- ubuntu
- shadowsocks
permalink: :category/buildss
---

# 环境
* ubuntu 16.04
---
# 开始
* __安装Shadowsocks__
		sudo apt-get update
		sudo apt-get install python-gevent python-pip
		sudo pip install shadowsocks
		apt-get install python-m2crypto
在新版本的python中包含了一些，不用再次安装。

* __配置Shadowsocks__
创建config.json配置文件:
	sudo vim /etc/shadowsocks.json
添加以下内容:
		{
			"server":"0.0.0.0",
			"server_port":8388,
			"local_port":1080,
			"password":"password",
			"timeout":600,
			"method":"aes-256-cfb"
		}
修改server为你的主机的IP。
修改password为你的密码。

* __配置防火墙__
打开server_port端口

* __运行Shadowsocks和关闭Shadowsocks__
		sudo ssserver -c /etc/shadowsocks.json -d start
		sudo ssserver -c /etc/shadowsocks.json -d stop

# 结束
至此，shadowsocks的小梯子已经搭好。
