#git操作命令

**1、创建repository：**

​	命令：mkdir  name<br>
​	解释：name就是就是一个文件夹名称，即创建一个空目录，这个目录初始化之后，里面所有的文件都可以被Git管理起来。
​	

**2、初始化repository**

​	命令：git init<br>
​	解释：初始化仓库repository，使得这个仓库目录里面的所有文件都能被Git管理。
​	

**3、添加文件到缓存区**

​	命令：git add <file><br>
​	解释：将文件提交道Git之前，需要将其先添加到stage缓存区，等待被提交，可以添加多个文件到缓存区，然后一起提交。
​	

**4、添加文件到Git仓库**

​	命令：git commit -m <message><br>
​	解释：-m后面的<message>可以是任何文字，通常建议键入有意义的文字以表示提交的内容，如：-m "添加readme.txt文件"。
​	

**5、查看工作区的状态：**

​	命令：git status<br>
​	解释：查看工作区当前做了哪些改变。
​	

**6、查看工作区修改的内容**

​	命令：git diff<br>
​	解释：查看工作区修改的详细内容，diff即different，不一样的地方。
​	

**7、定位到历史版本**

​	命令：git reset --hard commit_id<br>
​	解释：HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭。commit_id指的是提交ID，
​	如：git reset --hard 1094a，就是回到1094a的版本。
​	

**8、查看提交历史**

​	命令：git log<br>
​	解释：这个命令会显示所有已经提交的版本内容，包涵commit_id和提交时的<message>，用以确定要退回到哪个版本。
​	

**9、查看命令历史**

​	命令：git reflog<br>
​	解释：查看所有命令历史，以确定要回到未来的哪个版本。
​	

**10、查看文件内容**

​	命令：cat <file><br>
​	解释：如：cat readme.txt，查看文本文件readme中的详细内容。
​	

**11、查看工作区和版本库里面相应文件的区别**

​	命令：git diff HEAD -- <file><br>
​	解释：如git diff HEAD -- readme.txt，用以查看工作区中readme文件和版本库中readme文件的区别。
​	

**12、丢弃工作区的修改**

​	命令：git checkout -- <file><br>
​	解释：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file
​	注：git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
​	

**13、丢弃已被加入到缓存区的修改**

​	命令1：git reset HEAD <file><br>
​	命令2：git checkout -- <fiel><br>
​	解释：命令1将文件从缓存区退回到工作区，命令2将退回到工作区的文件里面的修改丢弃掉。
​	注：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
​	

**14、从版本库删除文件**

​	命令：git rm <file><br>
​	解释：如要从版本库中删除test.txt文件，就用：git rm test.txt
​	

**15、把本地master分支的最新修改推送到GitHub远程仓库**

​	命令：git push origin master<br>
​	解释：master代表主分支，如要推送其他分支可以master换成相应的分支名，如：git push origin dev，就是推送dev分支。

**16、当在github上删除了一些文件后，本地仓库数据和远程仓库数据不一致。**

下面两个操作可以同步仓库和本地的全部内容：
1.先抓取并合并远程仓库全部内容git pull origin master
2.再推送本地仓库数据git push origin master

