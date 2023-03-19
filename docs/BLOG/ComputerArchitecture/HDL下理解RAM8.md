# HDL下理解RAM8

本文是在HDL下理解RAM的组成原理！！

## 已经拥有的门基础

在过去已经使用了NAND、Or、And、not搭建了很多逻辑门了。包括数据选择器和数据分配器(Mux8Way16、DMux8Way)

以及，一个内置的DFF触发器：一个基本的存储器，存储单比特的存储器。

我们使用了DFF，给他加入了保持和置数的功能，把它扩展成了寄存器：一位寄存器Bit、16位寄存器Register
```css
Bit(in= ,load= ,out= )

Register(in= ,load= ,out= )
```

## 什么是RAM8

**Random Access Memory8** 

一个8个存储单元的RAM芯片，每个单元可以放一个16位数据

![](https://pic.imgdb.cn/item/640c762bf144a0100767ae08.jpg)

* Function功能
	* 输出指定address中存储的数据
	* 输入数据存入到指定的address中

* 输入口
	* in[16]
	* load
	* address[3]
* 输出口
	* out[16]

对输入的解读：当我们输入十进制数的时候，会自动转成二进制，二进制才是机器看的懂的语言。比如：5->101

被忽略的时钟信号：当时钟信号变化一次(tick tock)，才能执行一次操作。否则就一直输出out的是上一次的数据。



## 实现一个RAM8

通过8个寄存器，结合数据选择器和分配器，搭建具有**取值和读写功能**的存储器。

思路：
1. 写：因为已经有了一个可以存储16位数据的寄存器Register，如果我们用8个寄存器，就可以实现存8个16位数据了
2. 取值：要根据地址选择输出。用数据选择器Mux8Way16，在8个输入信号中选择一个进行输出。选择的根据是address[3]。比如address=101，则选择第5个信号f，进行输出。
3. 读：数据分配器DMux8Way，找到地址。

```css

CHIP RAM8 {
    IN in[16], load, address[3];
    OUT out[16];

    PARTS:
    // Put your code here:
	// 完成数据的输出
	Mux8Way16(a=oa,b=ob,c=oc,d=od,e=oe,f=of,g=og,h=oh,sel=address,out=out);

	// 完成数据的写入
	DMux8Way(in=load,sel=address,a=la,b=lb,c=lc,d=ld,e=le,f=lf,g=lg,h=lh);
	Register(in=in,load=la,out=oa);
	Register(in=in,load=lb,out=ob);
	Register(in=in,load=lc,out=oc);
	Register(in=in,load=ld,out=od);
	Register(in=in,load=le,out=oe);
	Register(in=in,load=lf,out=of);
	Register(in=in,load=lg,out=og);
	Register(in=in,load=lh,out=oh);

}
```

## 总结

把已经搭建好的元件抽象出来，只需要知道它的功能，不再需要知道它们的底层是如何实现的。

再用这层抽象，去搭建更复杂、功能更完善的元件。比如RAM64 512