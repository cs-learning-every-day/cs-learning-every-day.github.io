### Resources
- [Learning Git Branching](https://learngitbranching.js.org/?locale=zh_CN)
- [Git Cheat Sheet: Commands and Best Practices](https://www.jrebel.com/blog/git-cheat-sheet)
- [Visualizing Git Concepts with D3](https://onlywei.github.io/explain-git-with-d3/#commit)
- [Bitbucket](https://www.atlassian.com/git/tutorials)
- [Git for Computer Scientists](https://eagain.net/articles/git-for-computer-scientists/)

> 可以配合git hook
- [Git 约定式提交](https://www.conventionalcommits.org/en/v1.0.0/)


- [Git-优雅地解决冲突：使用ours和theirs](https://blog.csdn.net/qq_41603165/article/details/104922336) 


### 提交修改代码前通常的流程 [查看 远程操作](https://learngitbranching.js.org/?locale=zh_CN)
git pull --reabse; git push
> git pull 就是 fetch 和 merge 的简写，类似的 git pull --rebase 就是 fetch 和 rebase 的简写！

### Windows 下 git bash配置

在你的安装路径\Git\etc\bash.bashrc，加入alias python='winpty python'


```
假如你刚clone了远程仓库dev分支，然后基于dev分支创建了自己的本地开发分支xyz，并进行了一些代码修改工作，这时候同事A告诉你他修复了一个重要bug，并已经merge到远程dev分支了。请问如何同步你本地的xyz分支并解释为什么
git checkout dev  && git pull -r && git checkout - && git rebase dev
```

```git
// 将本地分支推送到远程
git push <远程主机名> <本地分支名>:<远程分支名>

删除本地分支
git branch -d localBranchName

重命名
git branch -m Tesla-feat/trainning

// 删除远程分支
git push origin --delete remoteBranchName

修改github 日期

git commit
git cat-file -p HEAD > tmp.txt
# at this point, edit the file to replace the timestamp

git hash-object -t commit -w tmp.txt
#=> 2ee8fcc02658e23219143f5bcfe6f9a4615745f9
git update-ref -m 'commit: foo' refs/heads/master \
    2ee8fcc02658e23219143f5bcfe6f9a4615745f9
```


### 取消跟踪,删除远程文件
```git
git rm -r --cached .

git add .

git commit -m "update gitignore"
```

### 配置全局信息
git config --global user.name "Tesla"
git config --local user.email  "1394466835@qq.com"


### 多台电脑使用一个SSH Key
```
1. Copy id_rsa和id_rsa.pub。

2. 在新电脑上执行

ssh-keygen –t rsa –C "youremail@gmail.com"

这样会在NEW的~/.ssh/中生成新的id_rsa和id_rsa.pub

3. 用备份好的OLD中的id_rsa和id_rsa.pub文件，覆盖NEW上对应的文件

4. 确保NEW上的两个文件的权限是正确的，id_rsa是600，id_rsa.pub是644，比如：

-rw------- 1 fancy fancy 1675 2013-03-19 12:55 id_rsa

-rw-r--r-- 1 fancy fancy 406 2013-03-19 12:55 id_rsa.pub
```

### 有用的别名
git lol
```
git config --global alias.lol "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```