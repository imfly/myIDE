# 关于.gitignore文件小问题


一个简单的原则：在使用`git add .`命令（也包括`git commit -a`命令)之前，修改`.gitignore`文件，才会被正确忽略。

## 解析

`.gitignore`的本意是忽略一些文件（不跟踪），而已经跟踪(git add)的文件，自然无法再忽略，不然就是`分裂症`。对于已经跟踪的文件，需要手动删除，然后再忽略。

## 参考

https://segmentfault.com/q/1010000000619246
