# Git 如何 Merge 其他Fork仓库的代码到自己的仓库

#### Requires

现有原始仓库： https://github.com/boilit/ebm.git

我Fork出来的仓库： https://github.com/subchen/ebm.git

zqq90 Fork出来的仓库：https://github.com/zqq90/ebm.git

现在我要把 zqq90 修改的代码 merge 进我的仓库。


#### 方法1

步骤如下：

1.先 clone 我的仓库导本地

```
git clone https://github.com/subchen/ebm.git
```

2.添加 zqq90 仓库

```
git remote add zqq90 https://github.com/zqq90/ebm.git
```

3.执行 merge

```
git fetch zqq90 
git merge zqq90/master
```

4.提交到 remote

```
git push origin master
```

查看本地的Git库

```
git remote -v 
git branch -a
```

#### 方法2

git pull https://github.com/zqq90/ebm.git master