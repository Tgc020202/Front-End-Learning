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

