# 「01」初学C语言笔记



## 1.第一个C语言程序

```C
#include <stdio.h>

 int main()

{

    /* 我的第一个 C 程序 */

    printf("Hello, World! \n");

 

    return 0;

}
```

讲解一下上面一段代码结构

>  

1. > *#include是预处理命令； <stdio.h>* 是头文件。告诉 C 编译器在实际编译之前要包含 stdio.h 文件

2. > *int main()* 是主函数，程序从这里开始执行。

3. > **/\*...\*/** 称为程序的注释。

4. > **return 0；** 终止 main() 函数，并返回值 0。

## 2.奇怪的知识点

###1.任何非0整数值就是逻辑的true

在while等条件判断语句中出现while(y)意思是只要y!=0 ，这个程序就会一直运行下去

所以while(!y) 意思是只要y==0,程序就会一直运行 

###2.对C来说,*char跟int的区别*只是一个占用的字节数少一个占用的字节数多

##3.写代码的顺序

1.先写代码整体结构的开头结尾

```C
Int i ;



for (int i=0,i< n,i++)

{ if (XXX);

    xxxxxx

    break;

}

Return i;
```

2.再写循环，执行or退出条件---注意插入达到目的后的break

> **为了方便定义变量类型，可以把**  **定义变量类型与赋值语句**  **写在一起**

##4.指针

![img](https://xij53lomtq.feishu.cn/space/api/box/stream/download/asynccode/?code=YjNhOTVmMTA3YWU3ZjhhMzQ2NDgyYTIwODEwZTVlNWNfbFhiUWMzcjBmdWtaZVY0TnRLQ2h3MWhHZERiNzVnMk1fVG9rZW46Ym94Y240T1l3YTVrQXNGc3VWdUpONUl0YzJjXzE2NzM1MzMwNDA6MTY3MzUzNjY0MF9WNA)



> 使用指针时会频繁进行以下几个操作：

> 1.**定义**一个指针变量、

> 2.把变量**地址赋值**给指针、

> 3.访问指针变量中可用地址的**值**。*p





具体了解指针数组看菜鸟教程