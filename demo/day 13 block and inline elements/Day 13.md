#### css 块状元素与行内元素及属性
+ 所有的 html 元素可以分为三大类
+ 其中比较常用的两类位： 块状元素，行内元素
+ 块状元素
> + 比如 div 最基本的块状元素
> + 它支持宽高 margin，padding
> + width 默认是 100 %，当没有设置宽的数值，且独占一行
> + 块元素可以随意嵌套

Example (block.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>block elements 块状元素</title>
    <style type="text/css">
        /* 默认宽(width) 为 100%，当我们没有设置宽的数值*/
        .myDiv {
            height: 100px;background-color: green;
        }
    </style>
</head>
<body>
    <div class="myDiv" style="background-color: lightblue;">默认宽为 100%</div>

    <div class="myDiv">
        证明每一个元素的宽都是独占一行的
        <p>我的名字是<div>tgc</div></p>
    </div>
    
    <ul>
        下面这个是块元素
        <li></li>
        <li></li>
        <li></li>
    </ul>
</body>
```

+ 行内元素
> + 比如 span 最基本的行内元素
> + 宽高会随着内容变化而变化
> + 不支持宽高，但是支持 margin，padding
> + 不独占一行
> + 行内元素只可以嵌套行内元素


Example (inline.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>inline elements 行内元素</title>
    <style type="text/css">
        /* 默认宽(width) 为 100%，当我们没有设置宽的数值*/
        .myDiv {
            height: 100px;background-color: green;
        }
        span {
            height: 100px;width:100px;color: red;
        }
        .color1{
            color:rgb(15, 187, 101);
        }
        .color2{
            color:#bc3c90;
        }
        a {
            background-color: rgb(209, 172, 10);
        }
    </style>
</head>
<body>
    <div class="myDiv">
        与下一个元素做对比
        <p>我的名字是<div>tgc</div></p>
    </div>

    <div class="myDiv" style="background-color: lightblue;">
        将元素并列在同一行
        <p>我的名字是<span>tgc</span></p>
    </div>

    <div class="myDiv" style="background-color: lightblue;">
        证明字体是可以通过 rgb code 换色的
        <p>我的名字是<span class="color1">tgc</span></p>
    </div>

    <div class="myDiv" style="background-color: lightblue;">
        证明字体是可以通过 HEX code 换色的
        <p>我的名字是<span class="color2">tgc</span></p>
    </div>

    <a href="https://github.com/Tgc020202">这个是行内元素</a>

    <input type="button" value="没有东西">
</body>
```

