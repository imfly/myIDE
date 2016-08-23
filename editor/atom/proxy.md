atom有时候需要代理去安装一些插件，设置方法如下：

（1）新建（或打开） ~/.atom 下的文件 .apmrc 文件

（2）填写下面的代码：

```
http-proxy=http://proxy.domain.com:8080
https-proxy=http://127.0.0.1:1080
strict-ssl=false
```

把其中的代理服务器和端口号改为自己的。
