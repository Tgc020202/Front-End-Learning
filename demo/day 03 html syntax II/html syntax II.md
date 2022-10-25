## 1-4 单双标记

#### 1-4-1 单标记
+ 单标记指的是有一个标签组成

+ 例子如下：
+ 换行符：<br/>
+ 水平线：<hr/>
+ 图片标签：<img/>
+ 文本标签：<input/>
+ link 标签：<link/>
+ 元信息标签：<meta/>

#### 1-4-2 双标记
+ 双标记由 “开始标签” 和 “结束标签” 两个部分而构成，必须成对使用。
+ p /p 段落标签，其中 <p> 是开始标签表示一个段落的开始，而 </p> 是结束标签，表示一个段落的结束。
+ 常见的双标记标签有：html head title body table span div p hx 等等


## 1-5 实体转义
+ 在 HTML 中，内容编辑时，如果是通过空格键编辑的多个空格，网页只会显示成一个，而小于号(<)和大于号(>），网站则会认为是标签而无法直接显示在页面中。这些都可以通过实体字符来解决。

| 符号 | 实体名称 | 实体编号 |
|------|-----------------|------------------|
| < | `&lt;` | `&#60;` |
| > | `&gt;` | `&#62;` |
| & | `&amp;` | `&#38;` |
| " | `&quot;` | `&#34;` |
| © | `&copy;` | `&#169;` |
| ® | `&reg;` | `&#174;` |
| x | `&times;` | `&#215;` |
| ÷ | `&divide;` | `&#247;` |


## 1-6 块状元素和行内元素
#### 1-6-1 块状元素
+ 块状元素：块级元素会独占一行，其宽度自动填满其父元素宽度
+ 一般情况下，块级元素可以设置 width，height 属性一般用来搭建网站架构，布局，承载内容.....
+ 比如：address,div,dl,dt,dd,fieldset,form,hx,hr,ol,p,pre,table,ul 等等

#### 1-6-2 行内元素
+ 行内元素：行内元素不会独占一行，相邻的行内元素会排列在同一行里，直到一行排不了才会换行，其宽度随元素的内容而变化
+ 行内元素设置 width，height 属性无效
+ 一般用在网站内容中的某些细节或部位
+ 用以强调，区分样式，上标，下标，描点等等。
+ 比如：a,b,big,small,br,em,i,img,input,label,select,span,strong,sub,sup,textarea 等等


## 1-7 World Wide Web (W3C) 标准
+ 块元素可以包含行内元素或某些块元素，但行内元素却不能包含块元素，它只能包含其他的行内元素
+ 过后再继续
+ 。。。


## 1-8 企业命名规范

## 2-0 HTML 标签属性
+ 通用属性标签：所有标签都拥有的属性例如：
> + id：整个 HTML 文档当中唯一的 标识 不可重复 相当于身份证
> + class：用户指定元素类别的名称 可以通过使用 class 元素给同一个文档中的多个元素进行归类
> + style：用于给元素设定样式【内部样式或者行内样式】
> + title：显示省略的内容，当光标移动到此元素区域上面的时候 才显示

Example:
```
<!DOCTYPE html>
<html>
<head>
    <meta charset = "utf-8">
    <meta name = "viewpoint" content = "width=device-width,initial-scale=1">
    <tilte> HTML 通用属性代码展示 </title>
</head>
<body>
    <div id = "maindiv" style = "background:red;width: 300px;height: 100px;" title = "鼠标悬停可以显示">
        这是一个div通用属性的展示      
    </div>
    <img src = "image 9.jpg" id = "img" style = "width: 400px; height: 400px;">
</body>
</html>
```


