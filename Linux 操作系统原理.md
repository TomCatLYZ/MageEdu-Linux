## Linux 操作系统原理

    第49天 【Linux 操作系统原理(01)】

- 程序局部性原理：
    + 空间局部性
    + 时间局部性

```
    第49天 【Linux 操作系统原理(02)】
```

- I/O 设备的组成部分：
    + 设备控制器
        * 集成在主板上的一块芯片或一组芯片
        * 每个控制器都有少量的用于通信的寄存器，每一个寄存器表现为一个 I/O 端口；
        * 所有的寄存器组合成为设备的 I/O 地址空间；
    + 设备本身
    + 驱动程序：
        * 通常应该由设备生产商
        * 位于内核中
    + 实现输入、输出：
        * 轮训：忙等待，在一定的时钟周期内去遍历每一个 I/O 设备是否有数据；
        * 中断：中断 CPU 正在运行的程序。中断向量，中断号，由设备向中断控制器注册得来；
            - 内核处理中断分为两步：
                + 中断上半步
                + 中断下半步
        * DMA:直接内存访问

- OS：
    + CPU：时间片，time slice
    + memory：虚拟地址空间
    + I/O：文件
    + 进程：
        * 资源集
            - cpu 时间
            - memory：抽象，虚拟地址空间（32bits: 4G）
            - I/O：打开的多个文件，fd(file descriptor)
                + 正常文件
                + 设备文件
                + 管道文件
        * task struct
            - 内核为每一个进程维护的一个数据结构
