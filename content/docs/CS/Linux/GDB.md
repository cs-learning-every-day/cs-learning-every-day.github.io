#### GCC

- -E 获取预处理后的文件内容

- -V 将编译、链接过程打印
- -g 用于GDB调试

ltrace 命令用来跟踪程序运行时调用的库函数

- -S 查看系统调用
- -e trace=write 只看write系统调用

strace 查看系统调用的封装函数

#### GDB

Segment Fault快速定位 

```bash
首先生成core文件
使用ulimit -a 查看core file size为0则是不会输出(改成不限制 ulimit -c unlimited)
运行程序出错则会输出，调试时gdb ./hello core
```

- list
- start
- ctrl + x + a