# HDL理解一个简易的Memory

## Memory组成

首先Memory里面分别有RAM16K和Screen、Keyboard组成

![](https://pic.imgdb.cn/item/6416c61fa682492fcca87b51.jpg)

0-16383 属于RAM16K

16384-24575 属于Screen

24576 属于Keyboard

## 功能

作为一个Memory的功能当然是读写数据了

* load：用来判断是否要写入数据
* address：来判断该写/读的数据是在RAM里还是在IO里
---

具体来看address：

-   为了选择要输出的内容，使用“Mux16”模块。当“address”输入的第13位为0时，将“o1”输出作为选择的输出，“address[13]”输入表示选择RAM16K模块的输出。当“address”输入的第13位为1时，将“o21”和“o22”输出作为选择的输出，“address[13]”输入表示选择屏幕输出，与“address[14]”输入进行多路复用。
-   为了选择要写入的内存，使用“DMux”模块。当“address”输入的第14位为0时，选择RAM16K模块进行写入。当“address”输入的第14位为1时，选择屏幕或键盘进行写入。该模块将“load”输入进行解复用，将其分别输出到“l1”和“l2”。