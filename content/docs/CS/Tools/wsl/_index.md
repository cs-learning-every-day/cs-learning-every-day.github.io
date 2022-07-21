---
bookFlatSection: true
---

- [安装WSL](https://zhuanlan.zhihu.com/p/337104547)
- [WSL2 配置Xlaunch图形化界面]({{< relref "/docs/CS/Tools/wsl/xlaunch.md" >}})
- [为WSL2加图形化界面配置](https://blog.csdn.net/weixin_30810127/article/details/112238239)
- [配置OH My ZSH](https://zhuanlan.zhihu.com/p/35283688)
- [Ubuntu换源](https://zhuanlan.zhihu.com/p/142014944)

关闭wsl 在adming下的cmd wsl --shutdown


### 解决WSL2中Vmmem内存占用过大问题
1按下Windows + R 键，输入 %UserProfile% 并运行进入用户文件夹

2新建文件 .wslconfig ，然后记事本编辑

3 填入以下内容并保存, memory为系统内存上限，这里我限制最大2gb，可根据自身电脑配置设置
```
[wsl2]
memory=2GB
swap=0
localhostForwarding=true
```
4 然后启动cmd命令提示符，输入 wsl --shutdown 来关闭当前的子系统

### WSL安装Dcoerk
> [Link](https://zhuanlan.zhihu.com/p/148511634)
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo service docker start
```

检测
```
# 检查dockerd进程启动
service docker status
ps aux|grep docker
# 检查拉取镜像等正常
docker pull busybox
docker images
```



### ZSH
> sudo: /usr/bin/sudo must be owned by uid 0 and have the setuid bit set 错误

1 - on an elevated CMD change default user to root:
ubuntu1804.exe config --default-user root

2 - open bash (zsh in my case) and change ownership:
chown root:root /usr/bin/sudo && chmod 4755 /usr/bin/sudo

3 - on an elevated CMD change default user back to my username
ubuntu1804.exe config --default-user [my_username]