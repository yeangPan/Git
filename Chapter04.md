# 第三章 撤销修改及删除文件  


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;首先通过```git status```以及```cat filename```来查看git的状态和文件的具体内容。
<div align=center>
<img src="/pic/cat_file.png" width=80%/>
</div>
在我未提交之前，我发现添加"撤销修改"内容有误，所以我得马上恢复以前的版本，现在我可以有如下几种方法可以做修改：

第一：如果我知道要删掉那些内容的话，直接手动更改去掉那些需要的文件，然后add添加到暂存区，最后commit掉。
第二：我可以按以前的方法直接恢复到上一个版本。使用 git reset  --hard HEAD^
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;但是现在我不想使用上面的2种方法，我想直接想使用撤销命令该如何操作呢？首先在做撤销之前，我们可以先用 git status 查看下当前的状态。如下所示：