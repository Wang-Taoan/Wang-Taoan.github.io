# 计算机基础记录
## 0 Summary

"虽然计算机领域新技术在不断涌现，但是计算机所做的事情，始终都是对输入的数据进行运算，将结果输出，这一点是永远不会变化的。"

## 1 一个内存IC的容量

### 内存IC引脚的示意图

![](https://pic.imgdb.cn/item/641fe344a682492fcc5f3892.jpg)


### 计算这个IC能存多少数据

首先需要明确知道：一个地址可以存放一个8位的数据（8bit=1byte）

地址端共有10个引脚A0-A9

00000 00000 - 11111 11111 = 2的10次方=1024个地址

每个地址存放1byte数据，则总共容量为1024byte=1KB

### 总结和扩展

> <https://blog.csdn.net/shizheng_Li/article/details/108899695>

通常情况下一个内存IC引脚越多，能存放的数据也越多。

上面看到的就是地址总线10位的CPU。

这里引入内存中的 数据总线的宽度 和 地址总线位宽 的概念。

一个数据总线宽度为64位的内存模块，它的地址总线的位宽通常为64位。

64位地址总线：能够寻址的内存地址数量最多为2^64个；64位数据总线：一次可以传输的数据位数为64位=8个字节。

---

上面都在说的是内存，那我们说的操作系统32位、64位那又是什么呢？

32位和64位是指计算机操作系统和CPU的架构类型。其中，32位和64位指的是CPU的寻址能力，即CPU能够寻址的最大内存数量。

32位的寻址能力是仅限于32位的地址；64位的寻址能力是64位，可以兼容32位。

在实际应用中，64位操作系统和CPU相比32位操作系统和CPU具有更好的性能和更高的处理速度。这是因为64位CPU可以同时处理更多的数据，同时支持更多的内存，从而提高计算机的整体性能。

32位系统的最大寻址空间是2的32次方=4294967296(bit)= 4(GB)左右;64位系统的最大寻址空间为2的64次方=4294967296(bit)的32次方，数值大于1亿GB;

也就是说32位系统的处理器最大只支持到4G内存，而64位系统最大支持的内存高达亿位数，实际运用过程中大多数的电脑32位系统最多识别3.5GB内存，64位系统最多识别128GB内存。



> 为什么1字节=8位？因为8位可以涵盖所有字符编码


### 【补充】数据类型在内存中

我们都知道：
* char占一个字节
* short占两个字节
* long占四个字节

如果把它们放在内存中，可以看到char占1个地址，short占2个地址，long占4个地址

![](https://pic.imgdb.cn/item/641fe572a682492fcc62654f.jpg)


这里的数据`123` 没有超过每个类型的最大长度，所以short、long占用的其他内存空间的数值为0.

## 2 硬盘和内存

 程序不读入内存就无法运行

程序必须从硬盘读入到内存，才可以运行。

因为负责解析和运行的CPU需要PC来指定内存地址从而读出程序指令，而内存具有比硬盘更快的访问速度，能够更快地提供程序所需的指令和数据，从而加速程序的执行。

## 3 计算机主板

计算机主板是计算机系统的核心部件之一，也被称为主机板、母板、系统板、底板等，它主要有以下几个作用：

1.  连接各种计算机组件：主板上有各种插槽和接口，可以连接处理器、内存、扩展卡、硬盘、光驱等各种计算机组件，形成一个完整的计算机系统。
    
2.  控制和协调各个组件的工作：主板上的芯片组负责控制和协调各个组件的工作，使它们能够有序地运作。例如，芯片组可以管理内存的读写、处理器的运行、硬盘的读写等等。
    
3.  提供扩展性：主板上有各种扩展插槽，可以插入不同类型的扩展卡，例如显卡、声卡、网卡等，使计算机系统具有更多的功能和性能。
    
4.  提供电源管理：主板上有电源连接口和电源管理芯片，可以控制整个计算机系统的电源开关、电源供应和电源管理等。
    

总之，计算机主板是整个计算机系统的核心部件，它负责连接、控制、协调和扩展各种计算机组件，是计算机系统正常工作的关键之一。


---

主板里面了ROM，ROM里面有BIOS。

## 4 认识一下虚拟机

* `虚拟机软件` : 在同一个操作系统上可以运行其他操作系统
* `虚拟机(Virtual Machine)`:  它模拟了一个完整的计算机系统，包括硬件和操作系统。


### 以Java虚拟机为例

> JAVA有两层意思，一个作为编程语言的Java，一个是作为运行环境的Java

先看一个普通的C源代码的运行流程

![](https://pic.imgdb.cn/item/642007f4a682492fcca02c6f.jpg)

---
再来看看Java虚拟机下的

![](https://pic.imgdb.cn/item/64200867a682492fcca0de22.jpg)

Java虚拟机在Windows上是专门的Windows虚拟机，Macintosh上是Macintosh虚拟机，Linux上是专门的Linux虚拟机

可以看到两张图对比，少了本地代码、CPU运行的过程？？

不妨可以再来看看虚拟机的概念，它模拟了一个完整的计算机系统，包括硬件和操作系统。

我们就可以知道原来这些过程放在了虚拟机里面啊

所以我们通过编译得到的Java字节码文件，可以不受操作系统影响

从操作系统角度看，Java虚拟机就是一个应用，从运行环境来看，Java虚拟机就是运行环境。


## 5 认识一下BIOS

### BIOS是什么

BIOS（Basic Input/Output System) 存储在ROM上，是预先内置在计算机主机内部的程序。

BIOS可以实现`对硬件的基本控制`（键盘、磁盘、显卡等）还有`引导程序`的功能

`引导程序`：把OS从磁盘加载到内存中运行

### BIOS的基本流程

电脑开机后，BIOS会确定硬件是否正常运行，没有异常，就会启动引导程序，把OS从磁盘加载到内存中运行。

虽然启动程序是OS的任务，但是OS不能启动自己，需要BIOS的引导程序来启动。

---


### BIOS的更新

BIOS是存储在ROM的，不能直接修改，那现在的电脑提到的BIOS更新程序是什么鬼？

问了ChatGPT，得到了解释。

固件更新工具并不是直接修改BIOS存储在ROM中的内容。相反，它使用一个特殊的机制将更新的固件映射到计算机的内存中，并使用该固件来启动系统。这种机制称为"固件更新机制"或"BIOS更新机制"，它允许在运行系统时将新的BIOS固件加载到内存中，而不是直接修改ROM中的数据。

当您运行固件更新程序时，该程序会将新的BIOS固件文件复制到特定的存储位置，通常是在硬盘驱动器上的一个特定目录中。然后，固件更新程序会将计算机的BIOS设置为在启动时从该位置加载固件文件。当计算机重新启动时，它会从该位置加载新的BIOS固件，并用它来启动系统。

总之，固件更新工具并没有直接修改ROM的内容，而是使用BIOS更新机制将新的固件文件映射到内存中，并用它来启动系统。这个机制使得BIOS更新更加方便和安全，同时也更容易回滚到旧的BIOS固件版本，以避免可能的问题。

---
我的理解：

这个会占用一些磁盘资源。

更新BIOS之后。开机启动，不再运行原来存在ROM上的BIOS，而是运行硬盘驱动器上的一个特定目录中的BIOS，从这个位置加载新的BIOS固件，并用它来启动系统。

## 6 操作系统的API差异


键盘输入、鼠标输入、显示器输出、文件输入输出都是API提供的功能。

不同的操作系统提供的API都是不同的

这样Windows应用程序不能直接移植到Linux上来


### 不同CPU类型的差异

CPU类型不同，对应的机器的语言也不同

所以相同的操作系统，API几乎相同，但是由于CPU类型不同，本地代码也不相同。

## 7 二进制求负数

我们把二进制的最高位当作是符号位

概述：求二进制负数,先求它的补数，然后再+1

求1的负数

1= 0000 0001

求其补数= 1111 1110

+1 = 1111 1111

所以-1的二进制为 1111 1111

### 【拓展】

二进制负数不能直接用十进制来表示。也就是说二进制负数直接按权相加，得到的十进制不是负数

怎么办？

将二进制负数 取反后+1 ，再在十进制的结果上加上符号位

比如 `1111 1110 -> 0000 0010 -> 2 -> -2`

## 8 函数调用机制的理解

### 前置知识

* 程序计数器Program Counter：用来存储下一条指令所在的地址
* 三大条件控制流程
	* 顺序：最简单，就是PC++
	* 条件、循环：使PC指向任意的地址，这样程序就可以跳转到任意指令了。

### 函数调用机制

![](https://pic.imgdb.cn/item/641fd171a682492fcc41d7ac.jpg)

执行MyFun函数过程
* 调用函数执行 `call指令` 把下一个指令的地址 0154 存放在一个叫“栈”的主存中。
* 并把调用函数的地址 0260 设置到PC上
* 完成函数。执行`return指令`,函数结束后，会从栈中拿回下一个指令的地址0154，并且把它设置到PC上

### 【补充】数组的实现

基址寄存器+变址寄存器=实现数组

![](https://pic.imgdb.cn/item/641fddc2a682492fcc56d8a5.jpg)


## 9 初识多线程

多线程的核心就是CPU的切换

![](https://pic.imgdb.cn/item/64202f13a682492fcce266c6.jpg)

### 用C来举个例子

![](https://pic.imgdb.cn/item/64202f59a682492fcce34081.jpg)

---
汇编代码

![](https://pic.imgdb.cn/item/64202f90a682492fcce3d070.jpg)

----

![](https://pic.imgdb.cn/item/64202feea682492fcce44c4b.jpg)

## 10 初识中断

### 中断处理器的示意图

![](https://pic.imgdb.cn/item/642033d2a682492fcce9e64c.jpg)


### 中断处理器的功能

CPU接收到中断请求->切换到中断处理器

下面是中断处理器的过程
1. 把CPU中所有寄存器中的数据保存到内存的栈中，备份数据
2. 完成对外围设备的控制，还原寄存器中的数据

![](https://pic.imgdb.cn/item/6420348ea682492fcceb2bca.jpg)

## 11 Windows操作系统的特性

### 32位和64位

32位操作系统表示处理效率最高的数据大小

比如最高能处理的数据是32位的

64位同理

### API函数集来提供系统调用

> DLL（Dynamic Link Library）文件是Windows操作系统中常见的一种动态链接库文件，它包含了一些可供其他程序调用的函数和数据。DLL文件通常是在运行时动态加载到内存中的，它们允许程序在不复制大量代码的情况下共享代码和数据，从而提高程序的性能和可维护性。

API通过多个DLL文件来提供，每个API的实体都是用C来编写的，所以C语言使用API更加容易。

API是应用程序和OS之间的接口，提供系统调用，也就是间接对硬件操作。

## 12 DMA

DMA（Direct Memory Access）是一种计算机技术，用于提高计算机设备之间数据传输的效率。传统的计算机数据传输方式需要通过CPU来控制，数据从设备传输到CPU，再从CPU传输到目标设备，这种方式效率较低，会占用CPU的大量处理时间。

DMA技术的原理是将数据传输的控制权从CPU转移到DMA控制器，DMA控制器直接从设备读取数据并将其存储到内存中，或者直接从内存中读取数据并将其发送到设备中，而不需要CPU的干预。这样可以极大地提高数据传输的速度和效率，同时也减轻了CPU的负担，提高了整个系统的性能。

DMA技术广泛应用于许多计算机设备之间的数据传输中，例如硬盘、光驱、网卡、声卡等设备与内存之间的数据传输。通过使用DMA技术，这些设备可以在不占用CPU处理时间的情况下，直接进行高速数据传输，提高了系统的整体性能和响应速度。

## 13 VRAM和GPU

### VRAM

VRAM（ Video Random Access Memory ）：用于存储图像和视频数据。

通常来说，显存容量越大、带宽越高的显卡，性能越好，能够处理更高质量的图像和视频。

需要注意的是，显存和系统内存是两个不同的概念。系统内存是计算机主板上的内存，用于存储操作系统和应用程序等数据，而显存是显卡上的专用内存，用于存储图像和视频数据。

### GPU

GPU（Graphics Processing Unit）：是计算机中的一种特殊处理器，主要用于图形和图像的计算和处理。

与传统的中央处理器（CPU）相比，GPU通常拥有更多的计算核心和更高的**并行处理能力**，可以同时处理多个数据和任务，因此在图形和图像处理方面表现更加出色。

需要注意的是，GPU通常需要和显存一起使用，因为显存能够提供快速的图像数据存取和处理，帮助GPU更加高效地进行图形渲染和图像处理。因此，显卡通常包括GPU芯片和显存两部分，一起构成一个完整的图形处理单元。

---

![](https://pic.imgdb.cn/item/64203635a682492fcced8237.jpg)

在MS-DOS时代VRAM是和主存一起的。Windows中将他们分开了，并集成到了显卡中。
