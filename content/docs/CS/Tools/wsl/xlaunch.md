
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
$ cat /etc/resolv.conf

sudo rm /etc/resolv.conf
sudo bash -c 'echo "nameserver windows ip" > /etc/resolv.conf'
sudo bash -c 'echo "[network]" > /etc/wsl.conf'
sudo bash -c 'echo "generateResolvConf = false" >> /etc/wsl.conf'
 
 # 导出
$ vim ~/.bashrc
# 在文件最后追加下面内容,地址使用上面查看到的
export DISPLAY=192.168.112.1:0

# 启动
sudo startxfce4

# 上面有坑，文件会被覆盖
# https://blog.csdn.net/IToBeNo_1/article/details/116333419
需要在cmd里wsl --shutdown
我目前是连的手机热点所以会变IP，不需要配置固定的windows IP
这里写个Bash小脚本
export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
```