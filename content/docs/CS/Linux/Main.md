---
---

- strace 跟踪系统调用
- stat 打印文件信息
- mount 查看挂载的文件系统
- grep telnet /etc/services 包含了一些熟知的端口号
- ldd proc 列出程序的动态依赖性
- ip addr / ping baidu.com
- df -h /
- find . -name "*.cpp"
- fdisk /dev/sdb
- shutdown -h 0
- apt install qemu-system
- pdfjoin a.pdf b.pdf
- iconv -f gbk -t utf-8 file.txt

输出当前用户是不是 root

- `[ $UID -eq 0 ] && echo "is root!"`

查看磁盘引导扇区 (Master Boot Record)

- `cat /dev/sdb | head -c 512 | ndisasm -b 16 -o 0x7c00 -`

统计所有 cpp 文件的行数

- `find . | grep '\.cpp$' | xargs cat | wc -l`

统计命令行命令的频率

- `history | tr -s ' ' | cut -d ' ' -f3 | sort | uniq -c | sort -nr`

- 文件管理 - `cd`, `pwd`, `mkdir`, `rmdir`, `ls`, `cp`, `rm`, `mv`, `tar`
- 文件检索 - `cat`, `more`, `less`, `head`, `tail`, `file`, `find`
- 输入输出控制 - 重定向, 管道, `tee`, `xargs`
- 文本处理 - `vim`, `grep`, `awk`, `sed`, `sort`, `wc`, `uniq`, `cut`, `tr`
- 正则表达式
- 系统监控 - `jobs`, `ps`, `top`, `kill`, `free`, `demsg`, `lsof`

1. 如何比较两个文件是否完全相同?

> diff or md5sum

1. 如何列出一个C语言项目中所有被包含过的头文件?

> find . -name "*.[ch]" | xargs grep "#include" | sort | uniq





































p@ssw0rd