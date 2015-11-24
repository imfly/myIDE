#### 使用corkscrew通过http代理使用git的ssh服务
  
单位上只能使用http代理上网，但我却随时需要使用git的ssh方式使用github。

在网上找到了corkscrew这个工具完美解决了这个问题。

1. 安装corkscrew
    下载corkscrew，是源代码的包。

     我的Mac os 10.7要使用./configure --host=i686-apple来配置。

2. 在.ssh/下新建config文件内容如下:

```
    Host github.com
    User git
    Hostname ssh.github.com
    Port 443
    ProxyCommand /usr/local/bin/corkscrew $proxy-host $proxy-port %h %p
    IdentityFile /Users/myusername/.ssh/id_rsa
```

    把其中的$proxy-host和$proxy-port替换为真实的代理服务器的地址和端口就行了。

    完美解决，这样做还不影响我其它的ssh操作。

补充：
   如果有socks服务器，那么proxifier是最完美的解决方案，除了不能用vpn其余和直连一样。

[原文](http://blog.sina.com.cn/s/blog_538d55be01018ksk.html)

#### Tunneling SSH over an HTTP-Proxy Server

Can't use SSH on the standard port 22? Need to tunnel through a proxy server? Work behind a draconian firewall and can't SSH directly? No problem. This document will hopefully show you how to tunnel through an http-proxy server without any server-side modifications.

[Tunneling SSH over an HTTP-Proxy Server](http://www.mtu.net/~engstrom/ssh-proxy.php)

#### Preference

[corkscrew](http://agroman.net/corkscrew/)
