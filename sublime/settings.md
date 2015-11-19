# Settings


#### Proxy

1.OS

```
# 分别指定http、https、ftp协议使用的代理服务器地址
http_proxy=http://proxy.lh.petrochina:8080 
https_proxy=http://proxy.lh.petrochina:8080
socks_proxy=http://proxy.lh.petrochina:8080

# 访问局域网地址（192.168.20.0/24网段）时不使用代理，可以用逗号分隔多个地址
no_proxy=localhost, 127.0.0.1, 10. 

export http_proxy https_proxy ftp_proxy no_proxy
```

2.Package Control

menu `Preferences -> Package Settings -> Package Control -> Settings - User`, add lines:

```
{
	"bootstrapped": true,
	"http_proxy": "proxy.lh.petrochina:8080",
	"https_proxy": "proxy.lh.petrochina:8080",
	"in_process_packages":
	[
	],
	"installed_packages":
	[
		"Package Control",
		"Theme - Soda"
	]
}
```