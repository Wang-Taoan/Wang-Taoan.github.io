# HDL下理解一个简易的CPU

## 功能

CPU可以用来读写内存中的数据、进行逻辑运算

## 组成

* 数据寄存器D：存放输入的数据和ALU计算完的数据
* 地址寄存器A（ARegister）：存放数据在内存中的地址
* ALU
* 计数器PC：用于存储下一条指令的地址，以便CPU可以顺序执行指令序列。

![](https://pic.imgdb.cn/item/6416cb50a682492fccb279a6.jpg)

---
具体内部图：

![](https://pic.imgdb.cn/item/6416d3c5a682492fccbfbcbf.jpg)


## 具体的呈现形式

1. 判断instruction指令是读写内存还是进行算数运算？
2. 所看到的过程就是汇编代码中的@1111 、M=D+M……
![](https://pic.imgdb.cn/item/6416cc40a682492fccb4108c.jpg)

## 小细节

可以看到CPU里面是有一些小的寄存器RAM来存放数据的。