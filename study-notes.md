# \#Github学习笔记

\##2024/9/11

#### 创建仓库至推送流程

浏览器打开github,点击New repository

仓库名和本地文件夹名保持一致

点击create repository

<<<<<<< HEAD
=======
dev分支的修改内容
>>>>>>> 379e8d8 (dev修改第五行)

mkdir      *#新建文件夹*

cd            *#进入文件夹*

git init    *#初始化，会生成隐藏的.git文件夹*

echo "内容" > 文件名.txt     *#创建文本文件*

git add .       *#添加所有文件到暂存区*

git commit -m "提交说明"   *#提交并写注释*

\##关联远程仓库并推送 dev #

cmd  git remote add origin https://github.com/你的用户名/仓库名.git

git branch -M main

git push -u origin main

##### 命令

git log --oneline  *#查看提交记录*

git status              *#确认无未提交内容*

git log                #查看提交历史

\##2024/9/13

#### 分支

git branch dev   *#创建开发分支*

git checkout dev  *#切换分支*

git push -u origin dev *#推送分支*

\##在dev分支修改文件并推送：

echo“dev分支修改” >>文件夹名.txt

git add .

git commit -m "dev分支更新"

git push      *#自动推送到origin/dev*

\##切回main分支查看区别

git cheakout main

type  文件名.txt *#查看文件内容*

git cheakout dev  *#切换回分支*

git push   *#推送dev分支的修改*

\##分支合并（把dev的修改合并到main分支）

git cheakout main  *#切换到主分支*

git merge dev    *#将dev分支合并到当前分支（main）*

git push origin main *#推送合并后的main分支*

type 文件夹名.txt   *#验证合并结果*

\##删除dev分支（如果需要）

git branch -d dev *#删除本地dev分支*

git push origin --delete dev  *#删除远程dev分支*

##### 写笔记 


cd C:\\Users\\xxxx\\文件夹名  #进入储存笔记的github仓库 


notepad 网络笔记.md   #打开记事本续写笔记，写完Ctrl+S保存（dir /s \*网络笔记.md    #如果忘了笔记在哪） 


git status   #检查状态（推送前执行） 


git add . #添加修改 


git commit -m "提交说明" 


git push 

##分支冲突解决 

1.制造冲突 

git checkout main 

echo "main分支的修改" >>study-notes.md 

git add . 

git commit -m "main分支更新" 

2.在dev分支修改同一行 

git branch dev 

git checkout dev 

echo "dev分支的修改" >>study-notes.md 

git add . 

git commit -m "dev分支更新 " 

3.触发冲突

git checkout main 

git merge dev  #报CONFLICT

4.解决冲突

打开冲突文件

删除冲突标记

5.完成合并

git add study-notes.md

git commit -m "解决main与dev冲突"

git push origin main 

##退回版本

回退到上一个版本：

git reset --hard HEAD^

git reset --hard HEAD~n(n表示退回的步数)

回退到指定commit

git reset --hard<commit_id>(用git log 查看commit_id,前7位即可)

强制推送覆盖远程（慎用）

git push -f origin main

##暂存操作

临时保存修改

git stash

恢复暂存内容

git stash pop #恢复最后一次暂存并删除记录

git stash apply #恢复但不删除记录

##比较差异

比较工作区和暂存区

git diff  #查看未add的修改

比较暂存区和仓库

git diff --cached  #查看已add但未commit的修改

比较两个分支

git diff main. .dev #比较main和dev的差异











<<<<<<< HEAD
=======
# 

"main֧޸"

>>>>>>> 379e8d8 (dev修改第五行)
"cherry-pick��������" 
