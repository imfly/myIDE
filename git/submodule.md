
# Submodule的使用

#### 情景

对于一些比较大的工程，为了便于复用，常常需要抽取子项目。这些子项目都以git submodule的形式，增加到工程中。

#### 操作

(1)添加子模块

应该在版本库的基础上进行，不然即便是有.submodule文件，也无法使用git submodule update下载子模块。

```
$ git submodule add repo-url path
```

(2)更新子模块

```
$ git pull //更新主版本库
$ git status //看子模块是否有修改，及时更新
$ git submodule update //第一次可能要自行 init操作
```

更复杂一些，如果你的submodule又依赖了submodule，那么很可能你需要在git pull 和 git submodule update之后，再分别到每个submodule中再执行一次git submodule update，这里可以使用 git submodule foreach命令来实现：

```
$ git submodule foreach git submodule update
```

(3)修改子模块

默认git submodule update并不会将submodule切到任何branch，所以，submodule的HEAD是处于游离状态的(‘detached HEAD’ state)。修改前，当前的submodule分支切换到master，然后才能做修改和提交。命令：

```
$ git checkout master
```

如果不慎忘记切换到master分支，又做了提交，可以用cherry-pick命令挽救。具体做法如下：
1.用 git checkout master 将HEAD从游离状态切换到 master 分支, 这时候，git会报Warning说有一个提交没有在branch上，记住这个提交的change-id（假如change-id为 aaaa)
2.用 git cherry-pick aaaa 来将刚刚的提交作用在master分支上
3.用 git push 将更新提交到远程版本库中

(4)删除子模块

最复杂，请看：

* Delete the relevant section from the .gitmodules file.
* Stage the .gitmodules changes git add .gitmodules
* Delete the relevant section from .git/config.
* Run git rm --cached path_to_submodule (no trailing slash).
* Run rm -rf .git/modules/path_to_submodule
* Commit git commit -m "Removed submodule <name>"
* Delete the now untracked submodule files
* rm -rf path_to_submodule

(5)将子模块设定为某个分支

上述命令默认是`master`分支，比如，要修改为`release`分支，那么可以使用命令：

```
# add submodule to track master branch
git submodule add -b master [URL to Git repo]

# update your submodule
# --remote will also fetch and ensure that
# the latest commit from the branch is used
git submodule update --remote

# to avoid fetching use
git submodule update --remote --no-fetch
```

Tracking commits

```
# update submodule in the master branch
# skip this if you use --recurse-submodules
# and have the master branch checked out
cd [submodule directory]
git checkout master
git pull

# commit the change in main repo
# to use the latest commit in master of the submodule
cd ..
git add [submodule directory]
git commit -m "move submodule to latest commit in master"

# share your changes
git push
```

Another developer can get the update by pulling in the changes and running the submodules update command.

```
# another developer wants to get the changes
git pull

# this updates the submodule to the latest
# commit in master as set in the last example
git submodule update
```

如果是已经添加了子模块，那么最简单的方法是，直接修改`.gitsubmodules`文件，如：

```
[submodule "SubmoduleTestRepo"]
    path = SubmoduleTestRepo
    url = https://github.com/jzaccone/SubmoduleTestRepo.git
    branch = release
```

or

```
[submodule "SubmoduleTestRepo"]
    path = SubmoduleTestRepo
    url = https://github.com/jzaccone/SubmoduleTestRepo.git
    branch = <sha-commit-id>
```

更新的时候，可以使用：

```
git submodule update --remote
```

#### 参考

官方文档：http://www.vogella.com/tutorials/Git/article.html#submodules

问答文档: http://stackoverflow.com/questions/1777854/git-submodules-specify-a-branch-tag

Git Submodule的坑: http://www.cocoachina.com/industry/20130509/6161.html

Git submodule tutorial: http://fiji.sc/Git_submodule_tutorial

http://www.stormzhang.com/git/2014/02/13/git-submodule/

删除子模块: http://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule
