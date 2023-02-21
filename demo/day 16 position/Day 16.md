## css 定位

#### 1.1 relative position 相对定位
+ position:relative;
+ left/right 只能两个选一个
+ top/bottom 只能两个选一个
+ z-index z轴，可以设定哪个元素最优先出现在顶层
+ z-index 的值可以是负数，数值越高 出现在顶层的概率就越高
+ 相对定位不会影响原来的位置，但是显示的元素会改变位置

Example:
```
<head>
  <title>Position 定位</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link href="css/style.css" rel="stylesheet">
  <style type="text/css">
    *{margin: 0;padding: 0;}
    .myDiv1 {
      width: 200px;
      height: 200px;
      background:red;
      float: left;
      position: relative;
      left: 220px;
      top: 200px;
    }
    .myDiv2 {
      width: 200px;
      height: 200px;
      background:green;
      float: left;
      position: relative;
      left: 20px;
      z-index: 1;
    }
    .myDiv3 {
      width: 100px;
      height: 100px;
      background:blue;
      float: left;
      position: relative;
      right: 180px;
      z-index: 2; /*可自行调节数值 看看差别*/
    }
  </style>
</head>
<body>
  <div class="myDiv1"></div>
  <div class="myDiv2">
       <div class="myDiv3"></div>
  </div>
</body>
```

#### 1.2 absolute position 绝对定位
+ position:absolute;
+ 脱离标准流
+ 原来的位置不会留着
+ 绝对定位是根据有定位的父元素进行定位
+ 如果父元素没有定位，那么就会找到最外层的元素直到html标签
Example 1:
```
<head>
  <title>Absolute Position 绝对定位</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link href="css/style.css" rel="stylesheet">
  <style type="text/css">
    *{padding: 0;margin: 0;}
    .myDiv1 {
      position: absolute;
      width: 200px;
      height: 200px;
      background: red;
      float: left;

      left: 300px;
      top: 0;
    }
    .myDiv2 {
      position: absolute;
      width: 200px;
      height: 200px;
      background: rgb(13, 237, 110);
      float: left;
                
      left: 0;
      top: 0;
    }
    .myDiv3 {
      position: absolute;
      width: 100px;
      height: 100px;
      background: rgb(15, 166, 221);
      float: left;
                
      left: 200px;
      top: 0;
    }
  </style>
</head>
<body>
  <!-- myDiv3 会根据 myDiv1 的位置来进行调位 -->
  <div class="myDiv1">
    <div class="myDiv3"></div>
  </div>
  
  <div class="myDiv2"></div>
</body>
```

+ 绝对定位的特性
Example 2:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Absolute Position 绝对定位的特性</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}

        /* myDiv1 没有定位 */
        .myDiv1{
            width: 200px; height: 200px;
            background: red;
            float: left;
            margin-top: 300px;
            margin-left: 200px;
        }

        /* myDiv2 有定位 */
        .myDiv2{
            position: absolute;
            width: 100px; height: 100px;
            background: rgb(11, 166, 197);
            float: left;
            top: 0;left: 0;
        }

        /* myDiv3 有定位 */
        .myDiv3{
            position: absolute;
            width: 400px; height: 400px;
            background: rgb(38, 216, 62);
            float: left;
            top: 100px;left: 100px;
        }
    </style>
</head>
<body>
    <!--
    myDiv2 没有跟着 myDiv1 的而调位
    却跟着myDiv3 而调位 
    因为 myDiv1 没有绝对定位
    -->
    <div class="myDiv3">
        <div class="myDiv1">
            <div class="myDiv2"></div>
        </div>
    </div>
</body>
```

#### 1.3 fixed position 窗口定位(固定定位)
+ position:fixed;
+ 只会根据窗口进行定位，不看父级定位
+ 就算有滚条的话 会一直跟着窗口走

Exmaple:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fixed Position 窗口定位</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}
        .myDiv1 {
            width: 200px;height: 200px;
            background: rgb(133, 220, 12);
            position: absolute;
            left: 300px;top: 300px;
        }
        .myDiv2 {
            width: 200px;height: 200px;
            background: rgb(6, 160, 183);
            position: fixed;
            left: 300px;top: 300px;
        }
        .myDiv3 {
            width: 200px;height: 200px;
            position: relative;
            margin: 100px;
            background: black;
        }
        .myDiv4{
            width: 200px;height: 500px;
            position: fixed;
            background: red;
            right:0;
            bottom: 200px;
        }
    </style>
</head>
<body>
    <div class="myDiv3">
        <div class="myDiv1"></div>
        <div class="myDiv2"></div>
    </div>

    <div class="myDiv4">我是广告</div>
</body>
```

#### inherit position 继承定位
+ position:inherit;
+ 继承父级的定位，父级是什么定位，他自己就是什么定位

#### static position 默认值
+ position:static;
+ 没有定位

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inherit and Static Positions 继承定位和默认定位</title>
    <style type="text/css">
        *{margin: 0;padding: 0;}

        /* 可以在 myDiv1 里的position进行替换 并理解 */
        .myDiv1{
            width: 200px;height: 200px;background: red;
            position: static;
            left: 0;top: 0;
        }

        .myDiv2{
            width: 100px;height: 100px;
            background: green;
            position: inherit;
            left: 200px;
            top:0;
            float: left;
        }
        .myDiv3{
            width: 100px;height: 100px;
            background: black;
            float: left;
        }
    </style>
</head>
<body style="height: 3000px;">
    <div class="myDiv1">
        <div class="myDiv2"></div>
        <div class="myDiv3"></div>
    </div>
</body>
```

