Title: iptables problem after rc-update
Date: 2014-8-14
Tags: iptables
Category: Linux

###  背景&问题产生
实验室限制ipv4流量每月2G。为了让后端设备可以顺畅的访问互联网，想出了方案
![image](http://www.wstnap.com/images/net-for-baha.png)
最近在Dell的小机箱安装了ubuntu.配置了openvpn client和ap-hotspot.买了linode的最低配的VPS.

sysctl net.ipvt.forward=1
iptables -t nat -s 192.168.150.0/24 -d 

每次开机总要输入这些命令很不爽，那只好配置开机启动服务了。不幸的事情发生了，同样在内网环境下的192.168.150.0/24 访问不了和Dell小机器位于同一网段的SharePoint 2013服务器。（之前没有发生过，）

	iptables -t nat -A POSTROUTING -s 192.168.150.0/24 -j SNAT --to-source 10.8.0.10
	
在linux完成routing之后还没有送出包之前。将数据包的原地址修改为 10.8.0.10 完成SNAT(原地址转换)
	

###  思考

1. 查看arp

		arp -d
		arp -a

2. 用192.168.1.166访问192.168.1.216

3. 192.168.150.x

		ping 192.168.1.216
		//time out  
4. .1.166 tcpdump 'icmp' 

	only 			192.168.150.x --> 192.168.1.216
	
	do not back		192.168.1.216 --> 192.168.150.x

5. 猜想是iptables的问题，没有转发or sth else.
 
### 解决

iptables -t nat -A POSTROUTING -d 192.168.1.0/24 -j SNAT --to-source 192.168.1.166

###  总结
1. tcpdump
2. iptables配置
