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

























