## css 元素介绍

#### 1.1 display 属性

###### 1.1.1 none 隐藏值 
+ display:none;
+ 让原来的元素进行消失
+ 位置不会进行保留

###### 1.1.2 block 以块状元素进行显示的值
+ display:block;
+ 变成块状元素
+ Note: float 也可以把行内元素变成块状元素

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Display 元素</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}

        #myDiv1{
            width: 200px;height: 200px;
            background: red;
            float:left ;
        }
        #myDiv2{
            width: 200px;height: 200px;
            background: green;
            float: left;
        }
        #myspan{
            width: 200px;height: 200px;
            background: pink;
            display: block;
        }
    </style>
</head>
<body>
    <div id="myDiv1"></div>
    <div id="myDiv2"></div>
    <span id="myspan"></span>
</body>
```

###### 1.1.3 inline 以行内元素进行显示的值
+ display:inline
+ 让任何元素变成行内元素

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inline 值的应用</title>
    <style type="text/css">
        .myDiv1 {
            width: 200px;height: 200px;
            background-color: red;
            display: inline;
        }
        .myspan {
            width: 200px;height: 200px;
            background-color: green;
        }
    </style>
</head>
<body>
    <div class="myDiv1">123</div>
    <span class="myspan">123</span>
</body>
```

###### 1.1.4 inline-block 值
+ display:inline-block
+ 拥有行内元素和块状元素的特征
+ 横着码放，同时不独占一行，支持宽高

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inline-Block</title>
    <style type="text/css">
        #myDiv1{
            width: 200px;height: 200px;
            background-color: red;
        }
        #myDiv2{
            width: 200px;height: 200px;
            background-color: green;
        }
        #myspan1{
            width: 200px;height: 200px;
            background-color: yellow;
            display: inline-block;
        }
        #myspan2{
            background-color: grey;
        }
    </style>
</head>
<body>
    <div id="myDiv1"></div>
    <div id="myDiv2"></div>
    <span id="myspan1">我变成行内块元素了</span>
    <span id="myspan2">我是行内元素</span>
</body>
```


#### 总结
+ 行内 inline - 横着码
+ 块状 block - 支持宽高，独占一行
+ 行内块 inline-block - 横着码放，但是不独占一行，支持宽高


#### 单位
###### 绝对单位
+ 不会因为模型大小而改变
+ 像素 px

###### 相对单位
+ 根据父级而随时进行改变
+ 无法判断是多少像素px
+ 百分比 %

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>百分比单位 %</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}

        /* 
        要设置 html 或者 body 的大小否则不能显示使用百分比显示的元素
        可以把下面一行的代码删了 并观察
        */
        html,body{height: 100%;}
        .myDiv1{
            width: 50%;height: 50%;
            background-color: red;
        }
        .myDiv2{
            width: 50%;height:50%;
            background-color: green;
        }
    </style>
</head>
<body>
    <div class="myDiv1">
        <div class="myDiv2"></div>
    </div>
</body>
```
