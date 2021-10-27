# 第四章 远程仓库

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在了解之前，先注册github账号，由于你的本地Git仓库和github仓库之间的传输是通过SSH加密的，所以需要一点设置：  

第一步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果有的话，直接跳过此如下命令，如果没有的话，打开命令行，输入如下命令：```ssh-keygen  -t rsa –C youremail@example.com```&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;由于我本地此前运行过一次，所以本地有，如下所示：
<div align=center>
<img src="/pic/remote_repo.png" width=80%/>
</div>
<div align=center>
<img src="/pic/rsa.png" width=80%/>
</div>
id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。  

第二步：登录github,打开” settings”中的SSH Keys页面，然后点击“Add SSH Key”,填上任意title，在Key文本框里黏贴id_rsa.pub文件的内容。
<div align=center>
<img src="/pic/remote_step1.png" width=80%/>
</div>
<div align=center>
<img src="/pic/remote_step2.png" width=80%/>
</div>
<div align=center>
<img src="/pic/remote_step3.png" width=80%/>
</div>
<div align=center>
<img src="/pic/remote_step4.png" width=80%/>
</div>  

第三步：现在的情景是，我们已经在本地创建了一个Git仓库后，又想在github创建一个Git仓库，并且希望这两个仓库进行远程同步，这样github的仓库可以作为备份，又可以其他人通过该仓库来协作。

首先，登录github上，然后在右上角找到“new repository”创建一个新的仓库。如下：
<div align=center>
<img src="/pic/new_repo.png" width=80%/>
</div>  

第四步：关联本地与远程仓库。
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;目前，在GitHub上的这个testgit仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

现在，我们根据GitHub的提示，在本地的testgit仓库下运行命令：```git remote add origin rep_url/repo.git```

第五步：本地项目第一次推送远程仓库
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;把本地库的内容推送到远程，使用```git push -u origin master```命令，实际上是把当前分支master推送到远程。由于远程库是空的，我们第一次推送master分支时，加上了 –u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。推送成功后，可以立刻在github页面中看到远程库的内容已经和本地一模一样了。  
<div align=center>
<img src="/pic/first_push.png" width=80%/>
</div>  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;从现在起，只要本地作了提交，就可以通过如下命令： 
```git push origin master```  把本地master分支的最新修改推送到github上了，现在你就拥有了真正的分布式版本库了。

