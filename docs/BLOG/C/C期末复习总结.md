# C进阶期末复习题


## 问题B： 四则运算

读入一个整数、一个操作符（仅限于+ - * /）、一个整数，求该表达式的值。

若除数为0，输出“The divisor is 0.”； 如过运算符是/，则进行整除（/）运算

例如：  5/3的结果应该是1

```
4+8
12

提示：
输入的语句可以用

scanf("%d%c%d",&a,&c,&b);
```

---

**代码实现** ：

难点：在于如何用C实现整除。当两个操作数都是整数时，C语言中的除法运算符将执行整数除法，即只返回结果的整数部分而舍弃小数部分。当两个操作数都是浮点数的话则返回浮点数结果。如果想要获得整数部分，可以用 **类型转化**

```c
#include"stdio.h"
#include"stdlib.h"

int main()
{

int a , b;
char c;
int g;
scanf("%d%c%d",&a,&c,&b);

if (b==0)
{
	printf("The divisor is 0.");
}else
{
	switch (c)
	{
	case '+':
		printf("%d",a+b);
		break;
	case '-':
		printf("%d",a-b);
		break;
	case '*':
		printf("%d",a*b);
		break;
	case '/':
		g = a / b;
		printf("%d",g);
		break;
	default:
		break;
	}

}

}
```

## 问题C： 确定数值的长度

任意输入一个整数n（n在1..100000000),统计该数是几位数 提示： 用除10运算 如：123  , (1) 123/10=12 重复以上步骤，直至该数变为0为止

```
13456
5
```

---
代码实现：

```c
#include"stdio.h"
#include"stdlib.h"

int main()
{
	int x;
	scanf("%d",&x);
	int num=0;
	
	while (x>0)
	
	{
		num++;
		x/=10;
	}
	printf("%d",num);
}
```

## 问题D： 函数printChar

编写程序，设计一个满足以下条件的printchar函数，用于在屏幕上打印若干个指定的字符。该函数的描述如下：

1. 该函数不带有返回值  
2. 该函数带有两个参数：参数一为字符型数据，说明要输出的是哪个字符，参数二为整型数据，说明参数一指定的字符要打印多少个。

输入：

1个字符ch，表示要输出的字符，然后是一个空格，空格后是一个整数n，表示要输出的字符的个数。

输出：

n个字符的ch

```
t 5
ttttt

---
#include <stdio.h>
@#1
int main()
{ int m;
  char c;
  scanf("%c%d",&c,&m);
   printChar(c,m);
  

}
@@1

@@1
```

---
代码实现：

```c
#include <stdio.h>

void printChar(char c , int m);

int main()

{

	int m;
	
	char c;
	
	scanf("%c%d", &c, &m);
	
	printChar(c, m);

}

void printChar(char c , int m){
	while (m>0)
	
	{
		
		m--;
		
		printf("%c",c);
	
	}

}
```

## 问题E： 【一维数组】求最小值及其下标

输入一组数据（最多不超过20个），存入数组中，求出该数组的最小值以及最小值的下标

第一行输入一个整数n  
第二行输入n个整数

输出最小值和最小值下标

```
5
1 2 3 4 5

1 0
```

---

代码实现：

```c
#include <stdio.h>

int main()
{

int n;

int a[30];

int i;

int min,min_flag;

scanf("%d",&n);

for ( i = 0; i < n; i++)

{

scanf("%d",&a[i]);

}

min=a[0];

min_flag=0;

for ( i = 1; i < n; i++)

{

if (min>a[i])

{

min=a[i];

min_flag=i;

}

}

printf("%d %d",min,min_flag);

return 1;

}
```

## 问题F： 【C语言】求二维数组周边元素的累加和【二维数组】

求一个二维数组周边元素的累加和。 输入一个二维数组的行数m（m<10），列数n(n<10)，二维数组的各元素值。输出周边元素之和。

输入的第一行为矩阵的行数和列数，从第二行开始，为矩阵元素的输入。

输出周边元素之和。

```
3 4
1 2 3 4 
5 6 7 8
1 2 3 4

33
```

---

代码实现：

```c
#include <stdio.h>

  

int main()

{

int x, y;

scanf("%d %d", &x, &y);

int a[10][10];

int i, j;

int sum = 0;

for (i = 0; i < x; i++)

{

	for (j = 0; j < y; j++)
	
	{
	
		scanf("%d", &a[i][j]);
	
	}

}

  

for (i = 0; i < x; i++)

{

	for (j = 0; j < y; j++)
	
	{
		
		if (i == 0 || j == 0 || i == 2 || j == 3)
		
		{
		
		sum += a[i][j];
		
		}
	
	}

}

printf("%d", sum);

return 1;

}
```

## 问题 G: 【字符串杂题】字符串分隔

字符串的合并与分隔，在网页编程中有非常重要。下面请你设计一个字符串分隔函数split，其功能是将一个以#为分隔标志的英文字符串，分隔到多个字符串，并保存到二维数组中。例如将英文字符串"zhangsan#lisi#wangwu#"分隔成3个字符串"zhangsan"、"lisi"、"wangwu"。

输入一个以#为分隔标志的英文字符串

输出：第1行是1个整数n，表示分隔后的字符串个数  

接下来n行，表示分隔后的n个字符串，每个字符串1行

```
zhangsan#lisi#wangwu#

3
zhangsan
lisi
wangwu
```

**分析：** 注意strncpy的使用、指针、每个词的长度、字符串结束符`'\0'`

---
charGPT:代码实现：


```c
#include <stdio.h>
#include <string.h>

#define MAX_STRINGS 100
#define MAX_LENGTH 100

void splitWithoutStrtok(const char* str, char result[MAX_STRINGS][MAX_LENGTH], int* count) {
    // 初始化字符串计数器
    *count = 0;

    // 初始化分隔位置
    int start = 0;
    int end = 0;

    // 遍历输入字符串
    while (str[end] != '\0' && *count < MAX_STRINGS) {
        // 找到分隔符的位置
        while (str[end] != '#' && str[end] != '\0') {
            end++;
        }

        // 计算分隔字符串的长度
        int length = end - start;

        // 拷贝分隔后的字符串到结果数组
        strncpy(result[*count], &str[start], length);
        result[*count][length] = '\0';
        (*count)++;

        // 跳过分隔符
        if (str[end] == '#') {
            end++;
        }

        // 更新下一个分隔字符串的起始位置
        start = end;
    }
}

int main() {
    char str[] = "zhangsan#lisi#wangwu#";
    char result[MAX_STRINGS][MAX_LENGTH];
    int count = 0;

    splitWithoutStrtok(str, result, &count);

    printf("分隔后的字符串数量：%d\n", count);
    printf("分隔后的字符串为：\n");
    for (int i = 0; i < count; i++) {
        printf("%s\n", result[i]);
    }

    return 0;
}

```

---

我的实现：

```c
#include <stdio.h>
#include <string.h>

int gc(char x[30],char st[20][20],int num);

int main() {

char st[10][20];

char x[30];

scanf("%s",x);

int num=0;

num=gc(x,st,num);

  

printf("%d\n",num);

for (int i = 0; i < num; i++)

{

printf("%s\n",st[i]);

}

return 0;

}

  

int gc(char x[30],char st[20][20],int num){

// zhangsan#lisi#wangwu#

int length=0;

int wb;

int start=0;

int cursor=0;

while (x[cursor]!='\0')

{

while (x[cursor]!='#'&x[cursor]!='\0')

{

cursor++;

// 当前第9个是#，cursor=9

}

length=cursor-start;

strncpy(st[num],&x[start],length);

wb=length++;

st[num][wb]='\0';

cursor++;

start=cursor;

num++;

}

  

return num;

}
```


## 问题 H: 【函数 数组 指针】 【1】利用函数在数组中找最大最小值（一）

输入一组数据，将该批数据存入数组中，并找出其中的最大值，最小值

第一行输入一个整数n

第二行输入n个整数

输出:

最大值和最小值

代码实现：

```c
#include"stdio.h"

void inputarray(int a[],int n);

void maxmin(int a[],int n,int *max,int *min );

  

int main()

{

int b[100];

int m,n,k;

scanf("%d",&k);

inputarray(b,k);

maxmin(b,k,&m,&n);

printf("max=%d,min=%d\n",m,n);

return 1;

}

  

void inputarray(int a[],int n){

int i;

for ( i = 0; i < n; i++)

{

scanf("%d",&a[i]);

}

  

}

void maxmin(int a[],int n,int *max,int *min ){

int i;

*max=a[0];

*min=a[0];

for ( i = 1; i < n; i++)

{

if (*max<a[i])

{

*max=a[i];

}

if (*min>a[i])

{

*min=a[i];

}

}

}
```

## 问题 I: 【C语言】【结构体】【函数】计算两个复数之和

本题要求实现一个计算复数之和的简单函数。

说明：任意两个复数的和是 (a+bi)+(c+di)=(a+c)+(b+d)i.

```c
3 4 5 6

(3+4i) + (5+6i) = 8 + 10i
----
#include <stdio.h>

struct complex{
    int real;
    int imag;
};

struct complex multiply(struct complex x, struct complex y);

int main()
{
    struct complex c, x, y;

    scanf("%d%d%d%d", &x.real, &x.imag, &y.real, &y.imag);
    c= multiply(x, y);
    printf("(%d+%di) + (%d+%di) = %d + %di\n", 
            x.real, x.imag, y.real, y.imag, c.real, c.imag);

    return 0;
}


@@1
/* 你的代码将被嵌在这里 */
@@1
```

---
```c
struct complex multiply(struct complex x, struct complex y){
	
	struct complex p;
	
	p.imag=x.imag+y.imag;
	
	p.real=x.real+y.real;
	
	return p;

}
```

## 问题 J: 【链表初步】动态链表(头插法)

利用头插法，创建类似下图所示的动态链表，其中结点数据域由键盘输入而确定。要创建下图的链表，输入的依次是DCBA。

创建好链表后，还需要依次访问各个结点，输出各个结点的数据域。

输入

1行，4个字符

输出

4个字符，次序与输入相反，中间用空格分隔。

---

**分析：** 节点p每次使用都是malloc一下、malloc的使用、销毁节点时候创建一个新节点再用free

```c
XYUW

W U Y X
--
#include <stdio.h>
#include <stdlib.h>

struct node       //结点数据类型
{
    char data;
    struct node *next; 
};

 void traverse(struct node* head);
 void destroy(struct node* head);
 struct node* headinsert(struct node* head);//该函数按照头插法，创建4个结点的动态链表，并返回第1个结点的地址

int main()
{
    struct node *head=NULL;

    head=headinsert(NULL);   //用头插法创建链表

     //遍历链表
     traverse(head);

    //释放资源，销毁链表中所有结点
    destroy(head);

}
void traverse(struct node* head){

  

while (head)

{

printf("%c ",head->data);

head=head->next;

}

}

  

void destroy(struct node* head){

struct node *p=head;

while (head)

{

p=head;

head=head->next;

free(p);

}

}

struct node* headinsert(struct node* head){

struct node *p;

  

for (int i = 0; i < 4; i++)

{

p = (struct node*)malloc(sizeof(struct node));

scanf("%c",&p->data);

if (head==NULL)

{

p->next=NULL;

}else

{

p->next=head;

}

head=p;

}

return head;

}
```

## 问题 K: 【链表初步】最大结点

已知head指向一个单链表，链表的结点的数据域是整型，设计函数求出链表中数据域值最大的结点。请完成下面的函数设计(二选一)。  

struct node * largestnode1(struct node *head);  
void largestnode2(struct node *head,struct node **ppmax);

找到最大结点后，如何将其传递给主调函数，有二种方法：  
1. 通过返回值，return回来。  
2. 通过指针的指针。主调函数传递指针变量的地址，函数将最大结点的地址，保存到这个传递过来的地址中，这样，主调函数中的指针变量，就获得了最大结点的地址。

输入：

1行，共6个整数，表示链表中的6个结点的数据域的值，这6个结点，按照头插法，插入到链表中

输出：

一个整数，表示最大结点的数据域的值。

```c
9 2 17 8 11 13

17
--
#include <stdio.h>
#include <stdlib.h>
struct node       //结点数据类型
{
    int data;
    struct node *next;
};

//实现以下二个函数中的一个。
struct node * largestnode1(struct node *head);
void largestnode2(struct node *head,struct node **ppmax);


 void destroy(struct node* head);
 struct node* headinsert(struct node* head);
 
main()
{
    struct node *head=NULL;
    struct node * pmax;
    head=headinsert(NULL);   //用前插法创建链表

    //找到最大结点，将其地址传给pmax
    // pmax=largestnode1(head);
    //largestnode2(head,&pmax);
     @#1    //选择上面二个被注释掉的语句中1个，并实现相应的函数。建议有的同学，可以二种都尝试一下，并提交二次


   printf("%d",pmax->data);

    //释放资源
    destroy(head);

}


struct node* headinsert(struct node* head)
 {   struct node *p;
     int n=0;
    //采用相同的方式创建6个结点，并且前插
    while(n<6)
    {
        //申请结点空间，创建新结点，并让p指向新结点
        p =  (struct node *)malloc(sizeof(struct node));
                 
        //初始化结点数据域  
        scanf("%d",&(p->data));         
        //挂链
        p->next=head;      //新结点的指针域，指向原来的第1个结点
        head=p;            //让新结点成为第1个结点
        n++;
    }
    return   head;             //返回第1个结点的地址
 }

struct node * largestnode1(struct node* head)
{   struct node *pmax=head;             //先假定第1个结点最大
    struct node *p=head->next;          //p指向第2个结点
    @@1
    如何找到最大结点，并让pmax指向最大结点？
    @@1
    return pmax;
}

void largestnode2(struct node *head,struct node **ppmax)
{   
    *ppmax=head;             //先假定第1个结点最大
    struct node *p=head->next;          //p指向第2个结点
    @@2
    如何找到最大结点，并让ppmax指向最大结点？
    由于是函数是void类型,如何把ppmax,传回给主调函数？
    @@2
}

 void destroy(struct node* head)
{   struct node *p;
    while(head!=NULL)
    {
        p = head;             //p指向要销毁的结点
        head = head ->next;   //head指向再下一个要销毁的结点
        free(p);               //销毁p指向的结点
    }
}
```

## 问题 L: 【C语言】【一维数组】组最小数

给定数字0-9各若干个。你可以以任意顺序排列这些数字，但必须全部使用。目标是使得最后得到的数尽可能小（注意0不能做首位）。例如：给定两个0，两个1，三个5，一个8，我们得到的最小的数就是10015558。

现给定数字，请编写程序输出能够组成的最小的数。

输入：

输入在一行中给出10个非负整数，顺序表示我们拥有数字0、数字1、……数字9的个数。整数间用一个空格分隔。10个数字的总个数不超过50，且至少拥有1个非0的数字。

输出：

在一行中输出能够组成的最小的数。

```
2 2 0 0 0 3 0 0 1 0

1000000223
```

---

代码实现：

```c
#include <stdio.h>

#include <stdlib.h>

  

int main()

{

// 放到数组中，第一步 先找到首位（不能是0，且最小）用完之后该位设置为-1

int a[10];

int i, j;

  

for (i = 0; i < 10; i++)

{

scanf("%d", &a[i]);

}

int min = 10;

int min_flag = -1;

for (i = 0; i < 10; i++)

{

if (min > a[i] && a[i] != 0)

{

min = a[i];

min_flag = i;

}

}

a[min_flag] = -1;

printf("%d", min);

min = 100;

min_flag = -1;

  

for (i = 0; i < 9; i++)

{

for (j = 0; j < 10; j++)

{

if (min >= a[j] && a[j] >= 0)

{

min = a[j];

min_flag = j;

}

}

a[min_flag] = -1;

printf("%d", min);

min = 100;

min_flag = -1;

}

  

return 1;

}
```


