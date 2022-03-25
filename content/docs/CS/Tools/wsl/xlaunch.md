
### Windows安装VcXsrc
> [下载](https://sourceforge.net/projects/vcxsrv/)

选择显示模式
![image](https://cdn.jsdelivr.net/gh/XmchxUp/cloudimg@master/20220310/image.4x6bfgnmvq40.webp)

默认选择，最后勾选
![image](https://cdn.jsdelivr.net/gh/XmchxUp/cloudimg@master/20220310/image.vtckz6dhwv4.webp)

允许防火墙
![image](https://cdn.jsdelivr.net/gh/XmchxUp/cloudimg@master/20220310/image.7ijkztoqqms0.webp)

### WSL配置与启动xfce4
```bash
sudo apt install -y xfce4
```
```shell
# 首先需要查看Windows系统和WSL2通信使用的虚拟网卡地址
$ sudo vim /etc/resolv.conf
# nameserver后面的地址就是Windows系统虚拟网卡的地址,记一下,同时需要取消下面两行内容的注释,禁用自动重新生成配置文件,否则重启后这个地址会变
[network]
generateResolvConf = false
 
 
$ vim ~/.bashrc
# 在文件最后追加下面内容,地址使用上面查看到的
export DISPLAY=192.168.112.1:0

# 启动
sudo startxfce4
```