
命令如下：

在本地，硬回退到正确的提交记录

```
git reset --hard HEAD~[num] #num是要删除掉的提交，如2个提交错误
```

修改，并强制提交

```
git push origin master --force
```

参考：

http://segmentfault.com/q/1010000002898735
http://www.cnblogs.com/dudu/p/4705247.html
http://www.cnblogs.com/TianFang/p/3540911.html
