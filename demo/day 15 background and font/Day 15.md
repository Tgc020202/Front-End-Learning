## css background 背景
+ 缩写样式: background
+ 非缩写样式
> + 背景颜色: background-color:颜色;
> + 背景图片: background-image:url(放图片的源头); 
> + 背景大小: background-size:宽度 长度; 设置一张图片的大小
> + 不重复图片: background-repeat:no-repeat;
> + 横坐标重复图片: background-repeat:repeat-x;
> + 列坐标重复图片: background-repeat:repeat-y;
> + 背景坐标: background-position
> > + 放两个参数 第二个参数默认为 center
> > + 第一个参数是 x 轴
> > + 第二个参数是 y 轴
> > + 可以放 right, left, top, bottom

Example :
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Background 背景</title>
    <style>
        .color1{
            width: 200px;height:200px;
            background-color: #14dbad;
            background-size: 200px 200px;
        }
        .myDiv1{
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 200px 200px;
        }
        .myDiv2{
            background-color: #0f75ea;
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 100px 100px;
            background-repeat: no-repeat;
        }
        .myDiv3{
            background-color: #0f75ea;
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 100px 100px;
            background-repeat: repeat-x;
        }
        .myDiv4{
            background-color: #0f75ea;
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 100px 100px;
            background-repeat: repeat-y;
        }
        .myDiv5{
            background-color: #0f75ea;
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 100px 100px;
            background-repeat: no-repeat;
            background-position: 50px;
        }
        .myDiv6{
            background-color: #0f75ea;
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 100px 100px;
            background-repeat: no-repeat;
            background-position: right bottom;
        }
        .myDiv7{
            background-color: #0f75ea;
            width: 200px;height:200px;
            background-image: url(panda.jpg);
            background-size: 100px 100px;
            background-repeat: no-repeat;
            background-position: center;
        }
    </style>
</head>
<body>
    <div class="color1">这个是颜色</div>
    <div class="myDiv1">这个是大熊猫</div>
    <div class="myDiv2">这个是大熊猫与黑背景</div>
    <div class="myDiv3">这个是大熊猫与黑背景 横向重复</div>
    <div class="myDiv4">这个是大熊猫与黑背景 列向重复</div>
    <div class="myDiv5">这个是大熊猫与黑背景 往右移 50px</div>
    <div class="myDiv6">这个是大熊猫与黑背景 右下角</div>
    <div class="myDiv7">这个是大熊猫与黑背景 正中间</div>
</body>
```

## css font 字体
#### color 颜色: 
> + color:rgb()
> + color:#HEX
> + color:颜色名称

#### font size 字体大小 
> + 控制字体的大小
> + font-size 数值px
> + 除了数值 也可以放:
> > + xx-small, x-small, small, medium, large, x-large, xx-large

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font 的应用</title>
    <style type="text/css">
        .myp1 {
            color: RED;
        }
        .myp2 {
            color: green;
            font-size: 18px;
        }
        .myp3 {
            color: pink;
            font-size: 25px;
        }
        .myp4 {
            color: pink;
            font-size: large;
        }
        .myp5 {
            color: pink;
            font-size: x-large;
        }
    </style>
</head>
<body>
    <p class="myp1">文字 1</p>
    <p class="myp2">文字 2</p>
    <p class="myp3">文字 3</p>
    <p class="myp4">文字 4</p>
    <p class="myp5">文字 5</p>
</body>
```

#### font weight 字体粗细
+ font-weight:数值
> + 数值的 range 100 至 1000
> 也可以使用文字
> + bold
> + bolder
> + lighter

Example :
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font weight 的应用</title>
    <style type="text/css">
        .p1 {font-weight: bold;}
        .p2 {font-weight: bolder;}
        .p3 {font-weight: lighter;}
        .p4 {font-weight: 100;}
        .p5 {font-weight: 1000;}
    </style>
    
</head>
<body>
    <p>我是大聪明</p>
    <p class="p1">我是大聪明</p>
    <p class="p2">我是大聪明</p>
    <p class="p3">我是大聪明</p>
    <p class="p4">我是大聪明</p>
    <p class="p5">我是大聪明</p>
</body>
```

#### font family 给予元素字体
###### 开发人员的字体，如果使用者没有此字体的种类的话，就不会显示
###### 字体的种类
+ SimSun 宋体
+ Microsoft Yahei 微软雅黑
+ Arial
+ Tahoma
+ Verdana
+ STHeiti 华文黑体
+ STXihei 华文细体
+ Heiti SC 黑体-简
+ Hiragino Sans GB冬青黑体
+ Times New Roman

###### 往后移动
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font Family</title>
    <style type="text/css">
        .p1{font-family: SimSun,Times New Roman;}
    </style>
</head>
<body>
    <p class="p1">字体一一一一</p>
</body>
```
+ 如果使用者的电脑没有 SimSun 字体，就会自动走Times New Roman

###### Note 
+ html,body{padding: 0;margin: 0;} 可以将其他的元素的空隙变为 0
+ *{padding: 0;margin: 0;} 可以将全部的元素的空隙变为 0


#### line-height 
+ 可以设定内容在自己的内部的高度位置
+ line-height 数值
+ 如果 line-height的数值与元素大小的数值一样时，内容就会出现在中心
+ 可以控制行内元素，但是控制不了块状元素
+ 数值支持正数，不支持负数

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Line Height</title>
    <style type="text/css">
        html,body{padding: 0;margin: 0;}
        div {
            height: 200px;
            border-top: 1px solid black;
            border-bottom: 1px solid black;
            margin-top: 30px;
            line-height: 200px;
            background-color: orange;
        }
        .myDiv{
            height: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <div>啦啦啦啦啦啦</div>
    <div><span>啦啦啦啦啦啦</span></div>
    <div><div class="myDiv">啦啦啦啦啦啦</div></div>
</body>
```


#### font style 文字的斜体
+ font-style:种类
> + italic 
> > + 是使用的字体倾斜
> + oblique
> > + 是让字体倾斜
 
Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font Style 文字的斜体</title>
    <style type="text/css">
        .p1{font-style:italic;}
        .p2{font-style:oblique;}
        .mySpan{color: red;font-style: italic;}
    </style>
</head>
<body>
    <p class="p1">啦啦啦啦啦</p>
    <p class="p2">啦啦啦啦啦</p>
    <p class="p3">啦啦<span class="mySpan">啦啦啦</span></p>
</body>
```

#### font variant 
+ font-variant:small-caps;
> + 把段落变成小型大写字体

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Font Variant</title>
    <style type="text/css">
        .p1{
            font-variant: small-caps;
        }
    </style>
</head>
<body>
    <p class="p1">AFSADsdfsdfsdfDfsaf</p>
    <p class="p1">asafasdfsafafafafas</p>
    <p>asafasdfsafafafafas</p>
</body>
```

#### font 的缩减
+ font: 所有属性；
+ 所以属性 随意位子

Example:
```
<head>
    <title>Font 的缩减</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="css/style.css" rel="stylesheet">

    <style>
        .p1{
            font-size: 15px;
            line-height: 30px;
            font-family: fantasy;
            font-weight: bold;
            font-style: italic;
            font-variant: small-caps;
        }
        
        .p2{
            font: italic bold small-caps 15px/30px fantasy; 
        }
    </style>
</head>
<body>
    <p class="p1">我不是缩减</p>
    <p class="p2">我是缩减</p>
</body>
```
