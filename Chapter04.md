# 第三章 撤销修改及删除文件  

## 一 撤销修改

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;首先通过```git status```以及```cat filename```来查看git的状态和文件的具体内容。
<div align=center>
<img src="/pic/cat_file.png" width=80%/>
</div>
在我未提交之前，我发现添加"撤销修改"内容有误，所以我得马上恢复以前的版本，现在我可以有如下几种方法可以做修改：

第一：如果我知道要删掉那些内容的话，直接手动更改去掉那些需要的文件，然后add添加到暂存区，最后commit掉。
第二：我可以按以前的方法直接恢复到上一个版本。使用 git reset  --hard HEAD^
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;但是现在我不想使用上面的2种方法，我想直接想使用撤销命令该如何操作呢？首先在做撤销之前，我们可以先用 git status 查看下当前的状态。如下所示：
<div align=center>
<img src="/pic/checkout_file.png" width=80%/>
</div>

命令 git checkout -- demo.md 意思就是，把demo.md文件在工作区做的修改全部撤销，这里有2种情况，如下：

demo.md自动修改后，还没有放到暂存区，使用 撤销修改就回到和版本库一模一样的状态。
另外一种是demo.md已经放入暂存区了，接着又作了修改，撤销修改就回到添加暂存区后的状态。
对于第二种情况，我想我们继续做demo来看下，假如现在我对demo.md添加一行 内容为"第一行，该行添加到暂存区"，我git add 增加到暂存区后，接着添加内容"第二行，该行未添加到暂存区"，我想通过撤销命令让其回到暂存区后的状态。如下所示：
<div align=center>
<img src="/pic/checkout_stage.png" width=80%/>
</div>
注意：命令git checkout -- demo.md 中的 -- 很重要，如果没有 -- 的话，那么命令变成创建分支了。

## 二 删除文件
假如我现在版本库testgit目录添加一个文件rm.txt,然后提交。如下：
