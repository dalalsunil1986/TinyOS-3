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
| 2021/3/18 | 编写并载入主引导程序MBR。 |
| 2021/3/19 | 编写内核加载器Loader，修改MBR并从硬盘读取内核加载器载入内存，从内核加载器中进入保护模式。 |
| 2021/3/20 | 增加内存检测功能，使用3种中断子功能探测内存容量。</br>完成二级页表的设置，成功开启分页机制。</br>花了2个小时弄懂了事先创建的页目录、页表与物理页的映射关系。不禁感叹，Linux的分页系统是真的巧妙。</br> 用C语言编写kernel.bin，并写入硬盘。|
| 2021/3/21 | 在loader中增加了mem_cpy字节拷贝、rd_disk_m_32硬盘读取和kernel_init内核初始化子过程，从硬盘读取kernel.bin并载入内存，接着根据elf文件头的信息，将kernel.bin中的segment载入内存中的正确位置。</br>学习特权级转换的相关知识。 |
| 2021/3/22 | 测试内核，发现gcc-m32...， ld -m elf_i386...编译链接的ELF文件中含有其他的段，这些段的虚拟地址没有分配物理块，因此在对ELF里面的段进行重定位的时候，访存错误导致了重启。</br>折腾了一天，猜测是gcc版本的问题。 |
| 2021/3/23 | 凌晨，将Ubuntu20.04.1、gcc9.3.0换成Ubuntu18.04.05、gcc7.5.0，之后一切正常，成功加载运行内核。|
| 2021/3/24 | 使用汇编实现put_char字符打印函数和put_str字符串打印函数，能够判断退格、换行以、回车符和空字符，测试成功。 |
| 2021/3/25 | 使用汇编实现put_int数字打印函数，给定32位数字，以16进制格式输出，输出时不输出前缀0，若数字全0则只输出0。 |
| 2021/3/26 | 学习中断相关的内容，内容过多，未上机实践。 |
| 2021/3/27 | 无 |

### Directories

| 目录    | 内容                               |
| ------- | ---------------------------------- |
| include | 主引导程序、内核加载器包含的头文件   |
| kernel  | 内核                              |
| tool    | 一些实用的小工具                   |
| boot    | 主引导程序和内核加载器              |
| hd      | 磁盘映像                          |
| configs | bochs配置文件                      |


