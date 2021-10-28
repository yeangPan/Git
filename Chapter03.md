# 第一章 Git工作区和暂存区

## 一 基本概念
工作区：就是你在电脑上看到的目录，比如目录下myrepo里的文件(.git隐藏目录版本库除外)。或者以后需要再新建的目录文件等等都属于工作区范畴。  

版本库(Repository)：工作区有一个隐藏目录.git,这个不属于工作区，这是版本库。其中版本库里面存了很多东西，其中最重要的就是stage(暂存区)，还有Git为我们自动创建了第一个分支master,以及指向master的一个指针HEAD。  

我们前面说过使用Git提交文件到版本库有两步：  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第一步：是使用 git add 把文件添加进去，实际上就是把文件添加到暂存区。
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第二步：使用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支上。  

我们继续使用demo来演示下：
我们在Chapter05.md进行了内容的修改，接着在目录下新建一个文件为demo.md的文件，内容为demo，我们先用```git status```来查看下状态，如下：
<div align=center>
<img src="/pic/stage_pic.png" width=80%/>
</div>  

现在我们使用```git add```命令把两个文件都添加到暂存区中，再使用```git status```来查看下状态，如下
<div align=center>
<img src="/pic/add_pic.png" width=80%/>
</div>  