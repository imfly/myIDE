# 安装主程序和插件控制器

#### 从官网下载安装包

[ubuntu 64位安装包](http://c758482.r82.cf2.rackcdn.com/sublime-text_build-3083_amd64.deb)
[ubuntu 32位安装包](http://c758482.r82.cf2.rackcdn.com/sublime-text_build-3083_i386.deb)

点击安装包，通过软件中心安装

#### 安装插件控制器

1.进入控制器官网

https://packagecontrol.io/installation

按照说明操作

2.打开命令行控制台

`ctrl+`快捷键或鼠标选择`View > Show Console`进入，

3.复制下面的代码到控制台，然后回车，安装成功

```
import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

4.使用控制器

使用快捷键`ctrl+shift+p`打开命令窗口，输入`install`，选择相应命令，进入对应插件列表窗口
