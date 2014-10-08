### DHCP服务器配置
### 单一网卡配置
ISC mean internet systems consortium  互联网系统协会
isc-dhcp-server(This package in the past was called dhcp3-server)
dynamic host configuration protocol

#### Installation
apt-get install isc-dhcp-server

#### Configuration
/etc/dhcpd/dhcpd.conf


default-lease-time 600;			//600 seconds
max-lease-time 7200;			//7200 seconds
option subnet-mask 255.255.255.0;	//subnet-mask
option broadcast-address 192.168.1.255;	//broadcast-address
option routers 192.168.1.254;				//router gateway
option domain-name-servers 192.168.1.1 192.168.1.2; //DNS server
option domain-name "mydomain.example";	//what does this mean

subnet 192.168.1.0 netmask 255.255.255.0  {
	range 192.168.1.10 192.168.1.100;
	range 192.168.1.150 192.168.1.200;
}


### 多网卡配置
subnet 192.168.150.0 netmask 255.255.255.0 {
	option default-lease-time 600;
	option max-lease-time 7200;
	option subnet-mask	255.255.255.0;
	option broadcast-address 192.168.150.255;
	option routers 192.168.150.254;
	option domain-name-servers 8.8.8.8;
	
	range 192.168.150.100 192.168.150.200;
	range 192.168.150.210 192.168.150.230;
}

subnet 192.168.1.0 netmask 255.255.255.0 {
	option default-lease-time 600;
	option max-lease-time 7200;
	option subnet-mask 255.255.255.0;
	option broadcast-adddress 192.168.1.255;
	option routers 192.168.1.254
	option domain-name-servers 8.8.8.8;
	
	range 192.168.1.2 192.168.1.240;
}