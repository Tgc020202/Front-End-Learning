## 盒子模型
+ 一个元素在页面中所占位置大小
+ 包含的样式
> + width / height / margin /padding / border / content

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>盒子模型 - content</title>
    <style>
        #div1{
            float: left;
            background-color: black;
        }
        #div2{
            float: left;
            width: 200px;
            height: 200px;
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
> + 盒子模型 - content
> > + 原本 div1(父类) 没有宽高，但是 div2(子类) 有宽高，所有子类把父类撑起来了，这就是所谓的 content


## css 的引用
1. 外链 - ```<link rel="stylesheet" type="text/css" href="css 的文件路径">```
2. 内嵌 - 在文件里使用 ```<style type="text/css">设置属性</style>```
3. 行内 - 在元素的标签里使用 ```<标签 style="设置属性"></标签>```
4. import - ```@import url('css 文件的路径');```
+ 级别: 行内 > 内嵌 > 外链
+ 被选中使用的概率: 位置越下面，被使用的概率最大


## 选择器
1. id
2. 标签
3. class
4. 通配符 - *
+ 级别: id > class > 标签 > 通配符

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selector</title>
    <style>
        /* 通配符 */
        *{
            background-color: white;
        }
        /* class */
        .div1{
            width: 200px;height: 200px;
            background-color: black;
        }
        /* id */
        #div2{
            width: 300px;height: 300px;
            background-color: yellow;
        }
        /* 标签 */
        div{
            width: 400px;height: 400px;
            background-color: green;
        }
    </style>
</head>
<body>
    <div class="div1" id="div2"></div>
</body>
</html>
```


## margin 外边距
+ 四个值:  上 右 下 左
+ 三个值:  上 左右 
+ 两个值:  上下 左右
+ 一个值:  上下左右
+ 其他说明可看回 [Day12.md](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2012%20css%20margin%20and%20padding/Day%2012.md)


## padding 内边距
+ 四个值:  上 右 下 左
+ 三个值:  上 左右 下
+ 两个值:  上下 左右
+ 一个值:  上下左右
+ 其他说明可看回 [Day12.md](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2012%20css%20margin%20and%20padding/Day%2012.md)

## 折行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>折行</title>
    <style>
        .div1{
            width: 200px;height: 200px;
            border: 2px solid black;
        }
        .div2{
            width: 200px;height: 200px;
            border: 2px solid black;
            word-wrap: break-word;  /* 文字折行 */
        }
        .div3{
            width: 200px;height: 200px;
            border: 2px solid black;
            word-wrap: break-word;  /* 文字折行 */
            text-align-last: center;    /* 控制最后一行的文字 */
        }
    </style>
</head>
<body>
    <div class="div1">1234567890abcdefghijklmnopqrstuvwsyz</div>
    <div class="div2">1234567890abcdefghijklmnopqrstuvwsyz</div>
    <div class="div3">1234567890abcdefghijklmnopqrstuvwsyz</div>
</body>
</body>
</html>
```
> + word-wrap:break-word; - 文字折行，使文字不会超出边框
> + text-align-last:center/right/left; - 控制文字的最后一行去排列


## position 定位
1. static 默认的定位，没有定位

2. absolute 绝对定位

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Absolute Position 绝对定位</title>
    <style>
        *{padding: 0;margin: 0;}

        /* 设置绝对定位 */
        .div1{
            width: 50px;height: 50px;
            background-color: black;
            position: absolute;
            left: 50px;top: 50px;
        }

        /* 设置绝对定位后，设置默认定位 */
        .div2{
            width: 50px;height: 50px;
            background-color: red;
            position: absolute;
            left: 50px;top: 50px;
            position: static;
        }

        /* 设置绝对定位，但是上下左右的值都是 0 */
        .div3{
            background-color: yellow;
            position: absolute;
            left: 0;top: 0;right: 0;bottom: 0;
        }

        /* 设置绝对定位，但是上下左右的值都是 0，且外边距为 auto*/
        .div4{
            width: 25px;height: 25px;
            background-color: green;
            position: absolute;
            left: 0;top: 0;right: 0;bottom: 0;
            margin: auto;
        }
    </style>
</head>
<body>
    <div class="div1"></div>
    <div class="div2"></div>
    <!-- <div class="div3"></div> -->
    <div class="div4"></div>
</body>
</html>
```
> + div2: position static 把 absolute 覆盖掉了
> + div3: 覆盖全屏，因为没有定宽高
> + div4: 定了宽高，设置外边距为 auto，元素就会居中 ```margin:auto```

3. relative 相对定位
+ 显示在网页的时候，位置是改变的，但是实际上位置并没有任何变化

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relative Position 相对定位</title>
    <style>
        *{padding: 0;margin: 0;}

        .div1{
            width: 25px;height: 25px;
            background-color: black;
            float: left;
            position: relative;
            left: 25px;
        }

        .div2{
            width: 50px;height: 50px;
            background-color: green;
            float: left;
        }
    </style>
</head>
<body>
    <div class="div1"></div>
    <div class="div2"></div>
</body>
</html>
```

4. fixed 窗口定位 - IE 6 不兼容
5. inherit 追随父级的定位

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inherit Position 追随父级的定位</title>
    <style>
        *{padding: 0;margin: 0;}

        body{
            position: absolute;
        }

        .div1{
            width: 25px;height: 25px;
            background-color: black;
            float: left;
            position: inherit;  /*相等于 absolute*/
            left: 25px;
        }

        .div2{
            width: 50px;height: 50px;
            background-color: green;
            float: left;
            position: relative;
            left: 25px;
        }
    </style>
</head>
<body>
    <div class="div1"></div>
    <div class="div2"></div>
</body>
</html>
```


## % 单位
+ 根据父级去计算
|单位 %|根据父级的...|
|-----|-----------|
|width|width|
|height|height|
|margin-left|width|
|inherit 的 left|width|

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Percentage % 单位</title>
    <style>
        *{padding: 0;margin: 0;}

        #div1{
            width: 200px;height: 200px;
            background-color: yellow;
        }

        #div2{
            width: 50%;height: 50%;
            background-color: green;
        }
    </style>
</head>
<body>
    <div id="div1">
        我是父级
        <div id="div2">我是子级</div>
    </div>
</body>
</html>
```

>> ![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p1.PNG)


## 如果父级没有定位
+ 子级会去找上一层的父级，直到 window
+ 直到找到有定位的父级，并以它为基础使用 % 单位

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>没有定位</title>
    <style>
        *{padding: 0;margin: 0;}

        /* 没有定位的父级 */
        /* #div1{
            width: 100px;height: 100px;
            background-color: yellow;
        } */

        /* 有定位的父级 */
        #div1{
            width: 100px;height: 100px;
            background-color: yellow;
            margin-left: 100px;
            position: relative;
        }

        #div2{
            width: 100%;height: 100%;
            background-color: green;
            position: absolute;
            left: 100px;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div id="div2">我是子级</div>
    </div>
</body>
</html>
```


## float 浮动
+ 使多个行内元素外的元素可以放置在同一行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>float & overflow:hidden</title>
    <style>
        *{padding: 0;margin: 0;}


        #l{
            width: 50%;
            height: 200px;
            background-color: black;
            float: left;
        }

        #b{
            /* width 超过父级的宽度就会自动移动去下一行 */
            /* width: 50.1%; */ 
            width: 50%;
            height: 200px;
            background-color: green;
            float: left;
        }
    </style>
</head>
<body>
    <div id="l"></div>
    <div id="b"></div>
</body>
</html>
```
> + 一个父级的满宽度为 100%，div1 + div2 的宽度 等于 100.1%，那么 div2 就会被移动去下一行
> + 这就是 float 的功能，可以把块标签放在同一行，当父类的宽度足以容纳元素的时候
> + 当我们把 div2 的宽度设置为 50%，div1 + div2 的宽度为 100%，所有可以容纳，并放置同一行

+ 如果 float 有给予高度，内容一旦超过此高度就会被剪切

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>float & overflow:hidden</title>
    
    <!-- 一旦给高度了，就会把多余的部分剪切 -->
    <style>
        *{padding: 0;margin: 0;}

        #l{
            width: 500px;
            border: 5px solid black;
            margin: 0 auto;
            overflow: hidden;
            height: 100px;
        }

        .title{
            width: 100%;
            height: 200px;
            float: left;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="l">
        <div class="title"></div>
    </div>
</body>
</html>
```

## overflow:hidden
+ 不给高度，且自己不给浮动，它会随着内容的浮动撑开

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>float & overflow:hidden</title>
   
    <!-- overflow:hidden -->
    <style>
        *{padding: 0;margin: 0;}

        /* 不给高度 */
        #l{
            width: 500px;
            border: 5px solid black;
            margin: 0 auto;

            /* 可自行注释下面这个部分，观察边框的差异 */
            /* float: left;    */
            
            /* 会随着内容的浮动撑开 */
            overflow: hidden;
        }

        .title{
            width: 100%;
            height: 200px;
            float: left;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="l">
        <div class="title"></div>
    </div>
</body>
</html>
```

## overflow:auto/scroll
+ 把多余的剪切，变成滚动条显示

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>float & overflow:hidden</title>
    
        <!-- overflow:auto + 高度 -->
        <style>
            *{padding: 0;margin: 0;}
    
            #l{
                width: 500px;
                border: 5px solid black;
                margin: 0 auto;
                overflow: auto; 
                height: 200px;
            }
    
            .title{
                width: 100%;
                height: 200px;
                float: left;
                background-color: red;
            }
    
            .title2{
                height: 300px;background-color: green;
            }
    
        </style>
</head>
<body>
    <div id="l">
        <div class="title"></div>
        <div class="title2"></div>
    </div>
</body>
</html>
```
> + 会生成滚动条，用来显示多余的部分
> > + ![p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p2.PNG)


## 行内元素 -> 块元素
+ -display: block;
+ -display: inline-block;
+ -float: left;
+ -position: absolute;
+ -position: fixed;
+ -display: table;

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clear</title>

    <style>
        *{padding: 0;margin: 0;}

        span{
            width: 100px; height: 100px;
            background-color: black;
            -display: block;
            -display: inline-block;
            -float: left;
            -position: absolute;
            -position: fixed;
            -display: table;
        }
    </style>
</head>
<body>
    <span></span>
</body>
</html>
```
> + 可以把 css 代码里的 span 标签里，有 - 符号的属性，一旦删了 - 符号，就会激活相对的属性值
> + span 标签是属于行内元素，所以宽高对它没有效果，因此它并不会显示出来
> + 但是一旦使用上面这些属性，就可以让它以块元素的形式显现出来


## 块状元素 -> 行内元素
+ -display: inline;

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>块状元素转行内元素</title>

    <style>
        *{padding: 0;margin: 0;}

        div{
            width: 100px;height: 100px;
            background-color: pink;
            -display: inline;
            

        }
    </style>
</head>
<body>
    <div>大呆呆</div>
</body>
</html>
```

## clear:both
+ 清除浮动(float)
+ 分为四种

1. clear: none;
+ 默认值，允许左右两边的元素都有浮动对象
+ 左浮动
> + ![p3](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p3.PNG)
+ 右浮动
> + ![p4](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p4.PNG)

2. clear: left;
+ 不允许左边的元素有浮动对象
+ 左浮动发生变化
> + ![p5](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p5.PNG)
+ 右浮动保持不变，不受影响

3. clear: right;
+ 不允许右边的元素有浮动对象
+ 左浮动保持不变，不受影响
+ 有浮动发生变化
> + ![p6](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p6.PNG)

4. clear: both;
+ 不允许任何一边的元素有浮动对象
+ 左浮动发生变化，跟 clear:left 一模一样
+ 右浮动发生变化，跟 clear:right 一模一样

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>clear</title>
    
        <style>
            *{padding: 0;margin: 0;}

            body{
                padding: 10px;
            }
            
            /* 控制浮动的方向 */
            -div{float: right;}
            -div{float: left;}


            #div1{
                width: 100px;height: 100px;
                background-color: pink;
                border: 2px solid black;
            }
            
            /* div2 用于控制 clear 的方向 */
            #div2{
                width: 100px;height: 100px;
                background-color: rgb(217, 66, 92);
                border: 2px solid black;

                -clear: none;
                -clear: left;
                -clear: right;
                -clear: both;
            }
    
        </style>
</head>
<body>
    <div id="div1">1</div>
    <div id="div2">2</div>
    <div id="div1">3</div>
    <div id="div2">4</div>
    <div id="div1">5</div>
    <div id="div2">6</div>
    <div id="div1">7</div>
</body>
</html>
```

## css 伪类
+ link - 未访问
+ hover - 触碰
+ active - 点击
+ visited - 已访问

+ 通常用来与 a 标签 - 链接搭配

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>伪类</title>

    <style>

        /* 通常使用在 a 标签 */
        a:link{
            color: red;
        }
        a:hover{
            color: blue;
        }
        a:active{
            color: green;
        }
        a:visited{
            background-color: lightblue;
        }
    </style>
</head>
<body>
    <a href="https://www.youtube.com/watch?v=clU8c2fpk2s" target="_blank">【Female Sings】Lemon/Kenshi Yonezu (Full Covered by KOBASOLO & Harutya)</a>
</body>
</html>
```
> + link(还未访问过此链接，如果已经访问过了，就需要删除历史浏览记录，才可以重新触发): 红
> > + ![p7](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p7.PNG)
> + hover(鼠标放置在链接上): 蓝
> > + ![p9](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p9.PNG)
> + active(鼠标点击链接的时候): 青
> > + ![p10](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p10.PNG)
> + visited(已经访问过此链接): 浅蓝
> > + ![p8](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2033%20css%20basic%20intro/p8.PNG)

+ 想要更加了解更多可以去看 [Day 5 CSS 基础语法](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2005%20css%20basic%20syntax/Day%2005.md) 的第一个部分
