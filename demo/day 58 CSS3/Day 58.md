## CSS 的解说
1. CSS1 - width/height
2. CSS2 - fixed
3. CSS3 - transform/transition/...

#### CSS3
+ IE 10 不兼容
+ CSS3 有手机上的 GPU 加速，所以比较不会卡

##### transition 过渡
+ CSS3 动画

##### transform - 2D 动画
###### scale 缩放
1. scale(x的倍数,y的倍数)
2. scaleX(x的倍数)
3. scaleY(y的倍数)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : Scale</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: black;
            transition: 1s transform ease;

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -50px;
            margin-left: -50px;
        }

        #div1:active{
            /* 可以自行调试 */
            /* transform: scale(2,2); */
            /* transform: scaleX(2); */
            transform: scaleY(2);
        }
    </style>
</head>
<body>
    <!-- 从中央进行缩放 -->
    <div id="div1"></div>
</body>
</html>
```

+ 如果倍数为负数，就会翻面

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : Scale 负数</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background: url(Images/p0.png) no-repeat;
            background-size: cover;
            transition: 1s transform ease;

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -50px;
            margin-left: -50px;
        }

        #div1:active{
            /* transform: scale(2,2); */
            /* transform: scaleX(2); */
            /* transform: scaleY(2); */

            transform: scaleX(-1);
        }
    </style>
</head>
<body>
    <!-- 从中央进行缩放 -->
    <div id="div1"></div>
</body>
</html>
```

###### rotate 旋转
1. rotate(度数deg)
2. rotateX(度数deg)
3. rotateY(度数deg)

+ 可使其变为 3D 模式
> + 添加: transform: perspective(800px);

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : Rotate</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: black;
            transition: 1s transform ease;

            /* 使其变为3D模式 */
            /* transform: perspective(800px); */
            transform: perspective(100px);

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -50px;
            margin-left: -50px;
        }

        #div1:active{
            /* 顺时针 */
            /* transform: rotate(90deg); */

            /* 逆时针 */
            /* transform: rotate(-90deg); */

            /* transform: rotateY(180deg); */
            transform: rotateX(180deg);
        }
    </style>
</head>
<body>
    <!-- 从中央进行缩放 -->
    <div id="div1"></div>
</body>
</html>
```

###### skew 扭曲
1. skew(度数deg,度数deg)
2. skewX(度数deg)
3. skewY(度数deg)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : Skew</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: black;
            transition: 1s transform ease;

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -50px;
            margin-left: -50px;
        }

        #div1:active{
            /* 扭曲 */
            /* transform: skew(180deg,180deg); */
            transform: skewX(180deg);
            /* transform: skewY(180deg); */
        }
    </style>
</head>
<body>
    <!-- 从中央进行缩放 -->
    <div id="div1"></div>
</body>
</html>
```

###### translate 移动
1. translate(x的距离,y的距离)
2. translateX(x的距离)
3. translateY(y的距离)
4. translateZ(z的距离)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : Translate</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: black;
            transition: 1s transform ease;

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -50px;
            margin-left: -50px;
        }

        #div1:active{
            /* transform: Translate(200px,200px); */
            /* 横轴平移 */
            /* transform: TranslateX(200px); */
            /* 竖轴平移 */
            transform: TranslateY(-200px);
        }
    </style>
</head>
<body>
    <!-- 从中央进行缩放 -->
    <div id="div1"></div>
</body>
</html>
```

+ translateZ 的用法
> + 需要父级有 3D，其子级才能支持 Z 轴
> + 添加 `transform-style: preserve-3d;` 在父级

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : TranslateZ Z轴</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 200px;
            height: 200px;
            background-color: black;

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -50px;
            margin-left: -50px;

            transform: perspective(800px) rotateY(60deg);
            transition: 1s transform ease;
            /* 需要父级有 3D，其子级才能支持 Z 轴 */
            transform-style: preserve-3d;
        }

        #div2{
            width: 100%;
            height: 100%;
            background-color: red;

            position: absolute;
            top: 0;
            left: 0;

            z-index: 999;
            /* 3D 平移 */
            transform: translateZ(30px);
        }
    </style>
</head>
<body>
    <div id="div1">
        <div id="div2"></div>
    </div>
</body>
</html>
```

















