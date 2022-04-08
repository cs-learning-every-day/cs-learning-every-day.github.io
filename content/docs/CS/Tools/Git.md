### Resources
- [Learning Git Branching](https://learngitbranching.js.org/?locale=zh_CN)
- [Git Cheat Sheet: Commands and Best Practices](https://www.jrebel.com/blog/git-cheat-sheet)
- [Visualizing Git Concepts with D3](https://onlywei.github.io/explain-git-with-d3/#commit)

// 将本地分支推送到远程
git push <远程主机名> <本地分支名>:<远程分支名>

// 删除本地分支
git branch -d localBranchName

// 删除远程分支
git push origin --delete remoteBranchName

修改github 日期
```git
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