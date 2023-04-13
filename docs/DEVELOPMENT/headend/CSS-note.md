# CSS学习笔记

## HTML引入CSS

外联式:.css

在HTML的head标签里面引入link标签

`<link rel="stylesheet" href="./my.css">`

## 「1」选择器

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

## 「2」字体-文本样式

**字体：**
1. 文字大小：`font-size:数字+px`
2. 文字粗细：`font-weight:400正常700加粗`
3. 文字倾斜
4. 字体：`font-family:`

* font的复合属性`font:style weight font family` 

多个值之间用空格隔开

> 最多只能省略前俩个属性，后面必须写

---
**文本样式：**
1. 文本缩进：`text-indent:数字2+em;` 2表示首行缩进2个字的大小
2. 文本对齐：`text-align:center/left/right;`

>这个对齐不仅适用于文本，还有p、img、span、a

1. 行高：`line-height:数字+px`

## 标签

1. 标签居中：`margin:0 auto` （第一个参数表示上下间距，第二个参数表示左右间距自适应）