# 第一章 Git基本操作

## 一 新建仓库

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;什么是版本库？版本库又名仓库，英文名repository,你可以简单的理解一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改，删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻还可以将文件”还原”。

1. 使用命令 ```git init```来新建仓库
<div align=center>
<img src="/pic/git%20init.png" width=80%/>
</div>

1. 使用命令 ```git add file```及提交修改命令```git commit -m "注释内容"```
<div align=center>
<img src="/pic/git_add.png" width=80%/>
</div>

3. 使用命令```git diff file```来查看修改
<div align=center>
<img src="/pic/git_diff.png" width=80%/>
</div>

## 二 版本回退
1. 使用命令```git log```或者```git log --oretty=oneline```(单行模式)查看历史版本
<div align=center>
<img src="/pic/git_log.png" width=80%/>
</div>

