# 修改错误的提交

#### 情景

* 不小心将含有密码的配置文件提交了，这时候就要删除版本库的这次提交。
* 仅仅需要某个提交以前的代码，后续的都需要删除。

#### 操作

在本地，硬回退到正确的提交记录

```
git reset --hard HEAD~[num] #num是要删除掉的提交，如2个提交错误
git push origin master --force //修改后
```

当然，也可以这样

```
git reset --hard <commit_id>
git push origin HEAD --force //修改后
```

#### 说明

根据–soft –mixed –hard，会对working tree和index和HEAD进行重置:
git reset –mixed：此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和index信息
git reset –soft：回退到某个版本，只回退了commit的信息，不会恢复到index file一级。如果还要提交，直接commit即可
git reset –hard：彻底回退到某个版本，本地的源码也会变为上一个版本的内容


HEAD 最近一个提交
HEAD^ 上一次
<commit_id>  每次commit的SHA1值. 可以用git log 看到,也可以在页面上commit标签页里找到.

#### 参考

https://www.douban.com/note/189603387/
http://segmentfault.com/q/1010000002898735
http://www.cnblogs.com/dudu/p/4705247.html
http://www.cnblogs.com/TianFang/p/3540911.html
