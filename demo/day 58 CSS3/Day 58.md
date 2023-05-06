## CSS 的解说
1. CSS1 - width/height
2. CSS2 - fixed
3. CSS3 - transform/transition/...

### CSS3
+ IE 10 不兼容
+ CSS3 有手机上的 GPU 加速，所以比较不会卡

#### transition 过渡
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

Example(小项目: 旋转立方体):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : 3D </title>
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
            margin-top: -100px;
            margin-left: -100px;

            transform: perspective(800px);
            -transition: 1s transform ease;
            /* 需要父级有 3D，其子级才能支持 Z 轴 */
            transform-style: preserve-3d;
        }

        #div1:active{
            transform: perspective(800px) rotateX(270deg) rotateY(270deg);
        }

        #div2{
            width: 100%;
            height: 100%;
            background-color: red;

            position: absolute;
            top: 0;
            left: 0;

            transform: translateZ(100px);
        }

        #div3{
            width: 100%;
            height: 100%;
            background-color: green;

            position: absolute;
            top: 0;
            left: 0;

            transform: translateZ(-100px);
        }

        #div4{
            width: 100%;
            height: 100%;
            background-color: yellow;

            position: absolute;
            top: 0;
            left: 0;

            transform: rotateY(90deg) translateZ(-100px);
        }

        #div5{
            width: 100%;
            height: 100%;
            background-color: blue;

            position: absolute;
            top: 0;
            left: 0;

            transform: rotateY(-90deg) translateZ(-100px);
        }

        #div6{
            width: 100%;
            height: 100%;
            background-color: pink;

            position: absolute;
            top: 0;
            left: 0;

            transform: rotateX(-90deg) translateZ(-100px);
        }

        #div7{
            width: 100%;
            height: 100%;
            background-color: orange;

            position: absolute;
            top: 0;
            left: 0;

            transform: rotateX(90deg) translateZ(-100px);
        }
    </style>
</head>
<body>
    <!-- 从中央进行缩放 -->
    <div id="div1">
        <div id="div2"></div>
        <div id="div3"></div>
        <div id="div4"></div>
        <div id="div5"></div>
        <div id="div6"></div>
        <div id="div7"></div>
    </div>

    <!-- JavaScript -->
    <script>
        var a = 0;

        // 设置定时器，使其循环旋转
        setInterval(function(){
            a++;
            div1.style.transform = 'perspective(800px) rotateX(' + a + 'deg) rotateY(' + a + 'deg)';
        },10);
    </script>
</body>
</html>
```

##### transform-origin
+ 设置中心点(透视点)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 - transform : Origin</title>
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
            transform: perspective(800px);
            transition: 1s transform ease;
            
            /* 设置中心点在左边 */
            transform-origin: left center;

            position: absolute;
            top: 50%;
            left: 50%;
            margin-top: -100px;
        }

        #div1:active{
            transform: rotateY(-180deg);
        }
    </style>
</head>
<body>
    <div id="div1"></div>
</body>
</html>
```

#### 选择器
##### `>`
+ 选择子级的所有第一层
+ 写法: 父级>第一级的子级元素{}

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 ></title>
    <style>
        #div1>div{
            width: 100px;
            height: 100px;
            background-color: black;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div></div>
    </div>
</body>
</html>
```

##### `+`
+ 兄弟选择，相邻的第一个就会被选择，如有就给值，没有就不给
+ 写法: 元素名+元素{}

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 +</title>
    <style>
        #div1+div{
            width: 100px;
            height: 100px;
            background-color: black;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div></div>
    </div>
    <div id="div2"></div>
    <div id="div3"></div>
    <div id="div2"></div>
</body>
</html>
```
> + 只有第一个 div2 变成黑色

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 +</title>
    <style>
        /* 把 div 换成 span */
        #div1+span{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div></div>
    </div>
    <div id="div2"></div>
    <span></span>
    <span></span>
    <div id="div3"></div>
    <div id="div2"></div>
</body>
</html>
```
> + 什么都没有显示，因为 span 不是 div1 之后的第一个元素

##### `~`
+ 下面的所有的要找的元素都会选择
+ 写法: 元素名~元素{}

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 ~</title>
    <style>
        #div1~span{
            width: 100px;
            height: 100px;
            float: left;
            background-color: black;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div></div>
    </div>
    <div id="div2"></div>
    <span></span>
    <span></span>
    <div id="div3"></div>
</body>
</html>
```
> + 所有的 span 都会变黑色

##### `*`
+ 代表全部

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 混合</title>
    <style>
        #div1~.a>*{
            width: 100px;
            height: 100px;
            display: inline-block;
            background-color: black;
        }

        #div1~.a>span{
            width: 100px;
            height: 100px;
            display: inline-block;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div></div>
    </div>
    <div id="div2"></div>
    <span></span>
    <span class="a">
        <div></div>
        <span></span>
        <span></span>
        <div></div>
        <div></div>
    </span>
    <div id="div3"></div>
</body>
</html>
```

##### `:not`
+ 代表除了

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 :not</title>
    <style>
        body>:not(div){
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div></div>
    <div></div>
    <span></span>
    <span></span>
    <span></span>
    <div></div>
</body>
</html>
```
> + 除了 div 元素，其他的元素都变成黑色

##### `[]`
+ 写法: [iTarget]
+ 代表属性选择器
+ 通过属性进行选择

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 []</title>
    <style>
        /* [tgc]{
            width: 100px;
            height: 100px;
            background-color: black;
        } */

        div[tgc],span[tgc]{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div tgc></div>
    <div wxx></div>
    <span xxx></span>
    <span tgc></span>
    <span></span>
    <div></div>
</body>
</html>
```
> + div 元素有 tgc 属性的会变成黑色
> + span 元素有 tgc 属性的会变成黑色

##### `$=`
+ 写法: [iTarget$='name']
+ 代表末尾必须是name值的属性的元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 $=</title>
    <style>
        [xxx$='aaa']{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div tgc></div>
    <div wxx></div>
    <span xxx="bbb ccc aaa"></span>
    <span tgc></span>
    <span></span>
    <div></div>
</body>
</html>
```
> + 在所有元素里，拥有 xxx 属性的，而且有末尾的属性值为 aaa 的元素变成黑色

##### `^=`
+ 写法: [iTarget^='name']
+ 代表开头必须是name值的属性的元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 ^=</title>
    <style>
        [xxx^='bbb']{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div tgc></div>
    <div wxx></div>
    <span xxx="bbb ccc aaa"></span>
    <span tgc></span>
    <span></span>
    <div></div>
</body>
</html>
```
> + 在所有元素里，拥有 xxx 属性的，而且有开头的属性值为 bbb 的元素变成黑色

##### `=`
+ 写法: [iTarget='name']
+ 代表必须是name值的属性的元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 =</title>
    <style>
        [xxx='bbb']{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div tgc></div>
    <div wxx></div>
    <span xxx="bbb ccc aaa"></span>
    <span tgc></span>
    <span></span>
    <div></div>
    <div xxx="bbb"></div>
    <div xxx></div>
</body>
</html>
```
> + 在所有元素里，拥有 xxx 属性的，而且只有 bbb 一个属性值的元素变成黑色

##### `*=`
+ 写法: [iTarget*='name']
+ 代表只要内容有这个属性的值就会被选择

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 *=</title>
    <style>
        [xxx*='bbb']{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div tgc></div>
    <div wxx></div>
    <span xxx="asdasdbbb ccc aaa"></span>
    <span tgc></span>
    <span></span>
    <div></div>
</body>
</html>
```
> + 在所有元素里，拥有 xxx 属性的，而且只要有 bbb 的属性值的出现，元素变成黑色

##### `first-child`
+ 写法: 元素:first-child
+ 选第一个
+ 代表只要是当前元素且在第一位的，就会被选择

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 first-child</title>
    <style>
        div:first-child{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div id="div1">
        <span></span>
    </div>
    <div id="div2">
        <div></div>
        <span></span>
    </div>
</body>
</html>
```
> + div2 元素里的第一个 div 元素变成黑色

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 first-child</title>
    <style>
        /* div:first-child{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        } */

        body div:first-child{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <div id="div1">
    </div>
    <div id="div2">
        <div></div>
        <span></span>
    </div>
</body>
</html>
```
> + body 下的 div1 的 div 元素变为黑色
> + body 下个 div2 的第一个子级 div 元素变为黑色

##### `last-child`
+ 写法: 元素:last-child
+ 选最后一个
+ 代表只要是当前元素且在最后一位的，就会被选择

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 last-child</title>
    <style>
        div:last-child{
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <span></span>
    <div id="div1">
        <span></span>
        <div></div>
    </div>
    <div id="div2">
        <span></span>
    </div>
    <div id="div3">
        <div></div>
        <span></span>
    </div>
</body>
</html>
```
> + div1 元素里的最后一个 div 元素变成黑色
> + div3 元素里的子级元素没有变色，因为它的 div 元素不是最后一个元素

##### `nth-child`
+ 写法: 父级>元素:nth-child()
+ 选第几个
+ 代表当前 n 位置的元素是想要获取的元素，就会被选择

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器 nth-child</title>
    <style>
        body>span:nth-child(2){
            width: 100px;
            height: 100px;
            background-color: black;
            float: left;
        }
    </style>
</head>
<body>
    <div id="div1"></div>
    <span id="span1"></span>
    <div id="div2">
        <div></div>
        <span></span>
    </div>
    <span id="span2"></span>
</body>
</html>
```
> + span1 元素变成黑色
> + 因为 span1 是 body 元素的第二个子级




