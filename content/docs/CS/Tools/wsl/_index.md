---
bookFlatSection: true
---

- [安装WSL](https://zhuanlan.zhihu.com/p/337104547)
- [WSL2 配置Xlaunch图形化界面]({{< relref "/docs/CS/Tools/wsl/xlaunch.md" >}})
- [为WSL2加图形化界面配置](https://blog.csdn.net/weixin_30810127/article/details/112238239)
- [配置OH My ZSH](https://zhuanlan.zhihu.com/p/35283688)
- [Ubuntu换源](https://zhuanlan.zhihu.com/p/142014944)



> sudo: /usr/bin/sudo must be owned by uid 0 and have the setuid bit set 错误

1 - on an elevated CMD change default user to root:
ubuntu1804.exe config --default-user root

2 - open bash (zsh in my case) and change ownership:
chown root:root /usr/bin/sudo && chmod 4755 /usr/bin/sudo

3 - on an elevated CMD change default user back to my username
ubuntu1804.exe config --default-user [my_username]