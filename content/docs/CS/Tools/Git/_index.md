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

取消跟踪,删除远程文件
```git
git rm -r --cached .

git add .

git commit -m "update gitignore"
```