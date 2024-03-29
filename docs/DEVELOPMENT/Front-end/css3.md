# CSS3 Notes
## 1 选择器

* 标签选择器：`标签名{属性名：属性值;}`

这个标签就是HTML的各种标签，比如p、h12345

* 类选择器：`.类名{属性名：属性值;}`

这个类名是在HTML写在标签里的 `class=“类名”`

> 命名规则：数字字母、中线-、下划线_
> 
> 一个标签可以用多个类名，多个类名之间用空格隔开

* id选择器:`#id名{属性名：属性值;}`

> 这个主要是配合JS来使用的

* 通配符选择器:`*{属性名：属性值;}`
```css
* {
 margin:0;
 padding:0;
}
```

## 2 字体-文本样式

**字体：**

1. 文字大小：`font-size:数字+px` 默认是16px
2. 文字粗细：`font-weight:400正常700加粗`
3. 字体：`font-family:`
4. font的复合属性`font:style weight font family` 
5. 去掉ul的列表点：`list-style:none`


---
**文本样式：**

1. 文本缩进：`text-indent:数字2+em;` 2表示首行缩进2个字的大小
2. 容器里的内容**水平对齐**：`text-align:center/left/right;`
3. 去掉a标签的下划线：`text-decoration:none`

>text-align 这个对齐不仅适用于文本，还有p、img、span、a.


1. 容器内文字 **垂直对齐** 用行高：`line-height:数字+px` 


## 3 选择器进阶

1. 后代选择器：空格隔开 `父选择器 后代选择器{}`
2. 子代选择器：> `父选择器>子代选择器{}`
3. 并集选择器：, `选择器1>选择器2{}`
4. 伪类（鼠标悬停的时候出现的效果）：`选择器:hover{}`

## 4 emmet语法

* 快速写出类选择器`div.red` ----> `<div class="red"></div>`
* 创建多个子代选择器`ul>li*3` ----> `<ul><li></li><li></li><li></li></ul>`
* 快速写出同级标签 `div+span`

以上这些在css中都是适用的

## 5 背景

1. 背景颜色:`bgc`
2. 背景图片：`bgi`
3. 背景平铺：`bgr：no-repeat/repeat/repeat-x/repeat-y`
4. 背景位置：`background-position:水平 垂直`
	* 水平：left/right/center
	* 垂直：top/bottom/center
	* 数字形式：数字+px
5. background的复合属性:`bg:color image repeat position(不分先后顺序)`

> Q：css中的bgi和HTML中的img如何去选择？
> 
> A：重要的用img，不重要且不影响功能的就用bgi

## 6 显示模式

* 块级：独占一行的
	* div、p、h
	* 可以设置宽高
* 行内：一行可以显示多个的
	* span、a
	* **不可以设置宽高，宽高由内容大小多少撑开，自适应**
* **行内块：一行可以显示多个，且可以设置宽高**
	* img、input、textarea

---

* 显示模式的转换：
	* 方法一：改标签div->span
	* 方法二：写属性`display: block/inline-block`   分别转成块和行内块


## 7 调试工具-Google

看到有问题，第一时间应该打开Google开发者调试工具(F12)，而不是源代码

## 8 盒子模型

组成：内容区（width height）、内边距（padding）、边框（border）、外边距（margin）

**原则：从外到内。宽高背景色->调节内容位置->文字细节**


### border

* 边框bd：`border:10px solid red`
实线solid-虚线dashed

* 单方向边框：bd-方向

尺寸计算：盒子尺寸=宽/高+边框大小

原则：从外到内。宽高背景色->调节内容位置->文字细节

### padding

内边距padding可以当复合属性使用,分别代表 上-右-下-左

`padding: 10px 10px 20px 20px`

border和padding都会撑大盒子模型，所以要进行相应的计算

### margin

同padding差不多

### 自动内减

设置的宽高即为目标大小，不再因为边框等因素而变化。即 不用再自己手动计算盒子尺寸大小了，

属性：`box-sizing: border-box`

### 清楚默认内外边距

浏览器有默认的内外边距

```css
*{
	margin:0;
	padding:0;
}
```


## 9.flex

主轴默认横向

侧轴默认竖向

```css
/*开启弹性盒子 */
display: flex;

/* 换行 */
flex-wrap: wrap;  /* - nowrap：不换行（默认） */

/* 调整主轴（水平）对齐方式 */
justify-content: center; /*沿着主轴居中对齐*/

/* 调整侧轴（垂直）对齐方式 */
align-items: center /* 沿侧轴居中对齐 */

/* 上面两个一起用，就是位于盒子的正中心。*/

/* 行内对齐方式*/
align-content: /* 这个属性好像被justify-content覆盖了，都是一样的功能 */
```


## 10.网页布局思路

1. 布局思路：先整体再局部，从外到内，从上到下，从左到右
2. CSS 实现思路
	1. 画盒子，调整盒子范围 → 宽高背景色
	2. 调整盒子位置 → flex 布局、内外边距
	3. 控制图片、文字内容样式
