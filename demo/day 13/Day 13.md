#### css 块状元素与行内元素及属性
+ 所有的 html 元素可以分为三大类
+ 其中比较常用的两类位： 块状元素，行内元素
+ 块状元素
> + 比如 div 最基本的块状元素
> + 它支持宽高 margin，padding
> + width 默认是 100 %，当没有设置宽的数值，且独占一行

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>块状元素与行内元素</title>
    <style type="text/css">
        /* 默认宽(width) 为 100%，当我们没有设置宽的数值*/
        .myDiv {
            height: 100px;background-color: green;
        }
    </style>
</head>
<body>
    <div class="myDiv" style="background-color: blue;">默认宽为 100%</div>

    <div class="myDiv">
        证明每一个元素的宽都是独占一行的
        <p>我的名字是<div>tgc</div></p>
    </div>
</body>
```

+ 行内元素
> + 比如 span 最基本的行内元素
> + 宽高会随着内容变化而变化
> + 不支持宽高，但是支持 margin，padding
> + 不独占一行


Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>块状元素与行内元素</title>
    <style type="text/css">
        /* 默认宽(width) 为 100%，当我们没有设置宽的数值*/
        .myDiv {
            height: 100px;background-color: green;
        }
    </style>
</head>
<body>
    <div class="myDiv">
        与下一个元素做对比
        <p>我的名字是<div>tgc</div></p>
    </div>

    <div class="myDiv" style="background-color: blue;">
        将元素并列在同一行
        <p>我的名字是<span>tgc</span></p>
    </div>
</body>
```
