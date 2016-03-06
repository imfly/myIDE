# 常用Plugins汇总

插件网址：

```
https://atom.io/packages
```

**注意**：安装完，需要重启，不知道为什么。

## atom-beautify

简介：美化（格式化）代码，支持很多种语言

主页：https://atom.io/packages/atom-beautify

使用：快捷键 `ctrl+alt+b`

## plantuml-preview

简介：编程的方式，绘制Uml图，即时预览

主页：https://atom.io/packages/plantuml-preview

repo: https://github.com/peele/plantuml-preview.git

必备：

(1) java和graphviz

```
sudo apt-get install java（j2ee?） Graphviz
```

http://www.graphviz.org/Documentation.php

(2) 下载plantuml.jar

http://plantuml.com/download.html

使用：预览快捷键，`Ctrl+Alt+P`

问题：快捷键不好使，配置的时候，可能会写错配置文件，需要手动去修改。

## language-plantuml

简介：支持plantuml语法高亮

主页：https://atom.io/packages/language-plantuml

repo: https://github.com/plafue/language-plantuml.git

使用：

## markdown-scroll-sync

简介：对默认预览插件进行扩展，实现自动同步浏览。

主页：
https://atom.io/packages/markdown-scroll-sync

repo: https://github.com/mark-hahn/markdown-scroll-sync.git

使用： 直接使用。预览`Ctrl+Shift+M`

## autocomplete-paths

简介：自动添加路径

主页： https://atom.io/packages/autocomplete-paths

repo: https://github.com/atom-community/autocomplete-paths

使用：直接使用。

## atom-html-preview

简介： html预览插件

主页： https://atom.io/packages/atom-html-preview

Repo: https://github.com/webBoxio/atom-html-preview.git

使用： Press `CTRL-SHIFT-H` in the editor to open the preview pane.

## Script

简介： Run code in Atom! Run scripts based on file name, a selection of code, or by line number.

主页： https://atom.io/packages/script

Repo: https://github.com/rgbkrk/atom-script

使用： `ctrl+shift+p` -> `script`

## merge-conflicts

简介： git解决合并冲突

主页： https://atom.io/packages/merge-conflicts

repo: https://github.com/smashwilson/merge-conflicts

使用： Resolve your git merge conflicts in Atom!

## JSHint

简介： Validate JavaScript with JSHint. In realtime or on save. Supports JSX (React).

主页： https://atom.io/packages/jshint

Repo： https://github.com/sindresorhus/atom-jshint

使用： 命令。

## git-plus

简介： Do git things without the terminal

主页： https://atom.io/packages/git-plus

Repo： https://github.com/akonwi/git-plus

用法： `Ctrl-Shift-H` on Windows + Linux

> Git Add ==  `git-plus:add`

> Git Add All Commit And Push == `git-plus:add-all-commit-and-push`

  __Note: This list is not exhaustive. And if what you want isn't a feature, You can use `Git Run` and enter the command__

| Command | Effect | Default key binding |
|----------|--------|------------------
| `Git Run ` | Execute a custom command. ex. `fetch --all` | |
| `Git Status ` | Show current status. | `Cmd-Shift-A S` |
| `Git Add ` | Add the current file. | `Cmd-Shift-A` |
| `Git Add All` | Adds all changed files. | |
| `Git add all commit and push` | Commit every changed file and push to a remote repo. | `Cmd-Shift-A P` |
| `Git commit` | Commit the staged changes. Git-Plus shows a commit message editor. To make the commit, save the file. To cancel the commit, close the tab. | `Cmd-Shift-C`(*`Ctrl-Shift-X`* on Windows and Linux) |
| `Git commit amend` | Amend the changes to previous commit. |  |
| `Git checkout current file` | Undo changes and checkout the current file. | |
| `Git Checkout `*`[ref]`* | Change to another ref (branch or tag). | |
| `Git Diff [All]` | Show the diff for the current file, or all files. The diff can either be against the staged or un-staged tree, as selected in the options. | |
| `Git new branch` | Create a new branch. | |
| `Git` *`[push⎮pull]`* | Push to or pull from a remote repo. If you have multiple remote repos, you can choose which to push to or pull from. | |
| `Git Add and Commit` | Add all changed files and show the commit message file. Similar to `Git add all` and `Git commit` run in succession. | `Cmd-Shift-A c` |
| `Git Add All and Commit` | Add all changed files and show the commit message file. Similar to `Git add all` and `Git commit` in succession. | `Cmd-Shift-A a` |
| `Git rm [current file]` | `git rm` the current file or open an selector to select the files to remove. You can select multiple files at once. | |
| `Git Log [Current File]` | Show the commit history [for the current file] and show display the selected commit. | |
| `Git Show` | Show the specified object, for example `HEAD`, `HEAD~2`,`3925a0d`, `origin/master` or `v2.7.3`. | |
