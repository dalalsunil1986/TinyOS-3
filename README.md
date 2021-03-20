# OS
Make a tiny OS.

### References
《X86从实模式到保护模式》

《汇编语言》王爽

《操作系统——精髓与设计原理》

《操作系统真象还原》

《跟我一起写Makefile》

《Linux命令行与Shell脚本编程大全》

《Linux/Unix系统编程手册》

### Logs
|    日期   |    事项   |
|   :----   |   :----   |
| 2021/3/18 | 载入主引导程序。 |
| 2021/3/19 | 从硬盘载入内核加载器，并进入保护模式。 |
| 2021/3/20 | 增加内存检测功能，使用3种中断子功能探测内存容量。</br>完成二级页表的设置，成功开启分页机制。</br>花了2个小时弄懂了实现创建的页目录、页表与物理页的映射关系。不禁感叹，Linux的分页系统是真的巧妙。 |

### Directories

| 目录    | 内容                               |
| ------- | ---------------------------------- |
| include | 主引导程序、内核加载器包含的头文件 |
| kernel  | 内核                               |
| tool    | 一些实用的小工具                   |

