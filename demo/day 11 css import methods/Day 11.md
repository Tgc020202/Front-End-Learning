# css 选择器 III (selector III)

#### 1.1 内嵌式选择器
+ 就是直接在 html 文件里写条件

Example 1(test.html):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style type="text/css">
        div{
            width: 200px;height: 200px;background-color: black;
        }

    </style>
</head>
<body>
    <div>

    </div>
</body>
</html>
```

#### 1.2 外链式选择器
+ 就是在 css 文件里写条件
+ 连接的方式跟之前学的 link 标签一样，也就是在 html 文件里添加 link 标签连接独立的 css 文件

Example 2(test.css & testcss.html):
test.css
```
div{
    width: 200px;height: 200px;background-color: red;
}
```

testcss.html
```
<!DOCTYPE html>
<html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>

      <link type = "text/css" rel = "stylesheet" href = "test.css">
  </head>
  <body>
      <div>

      </div>
  </body>
</html>
```

#### 1.3 行内式选择器
+ 直接写在 html 的标签的属性值里

Example 3(test_one_line.html):
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <div style="width: 200px;height: 200px;background-color: blue;">
        </div>
        >
    </body>
</html>
```

## 这三种方式的级别不同
+ 外链式 一般来说优先使用这个
+ 层级: 行内式 > 内嵌式 or 外链式

Example 4(Test_Stage.html):
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <style type="text/css">
            div{
                width: 200px;height: 200px;background-color: black;
            }
        </style>
        <link type = "text/css" rel = "stylesheet" href = "test.css">
    </head>
    <body>
        <div style="width: 200px;height: 200px;background-color: blue;">
        </div>
    </body>
</html>
```
+ 一开始出现的颜色是蓝色，当我们删了 
```
<div style="width: 200px;height: 200px;background-color: blue;">
</div>
```
+ 就变成红色或者变成黑色，取决于哪一个 code 更加靠近 <div>

Example (外链式比较靠近 <div>)
+ 呈现红色因为 text.css 里面设定红色
+ 代码:
```
<link type = "text/css" rel = "stylesheet" href = "test.css">
```
```
<head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <style type="text/css">
            div{
                width: 200px;height: 200px;background-color: black;
            }
        </style>
        <link type = "text/css" rel = "stylesheet" href = "test.css">
    </head>
    <body>
        <div>
        </div>
    </body>
```

Example (内链式比较靠近 <div>)
+ 呈现黑色
+ 代码:
```
<style type="text/css">
    div{
        width: 200px;height: 200px;background-color: black;
    }
</style>
```
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link type = "text/css" rel = "stylesheet" href = "test.css">
    <style type="text/css">
    div{
         width: 200px;height: 200px;background-color: black;
    }
    </style>
</head>
<body>
    <div>
    </div>
</body>
```
## 代码永远都是从上往下执行，可以理解为上面的代码已经运行过了，如何就接下去运行下面的代码，所以上面的代码的颜色被刷掉了。


#### 2.1 id 选择器
+ 跟之前学的 <div class=""> 大同小异
+ id 选择器是唯一(unique)的，id 的权重最高
+ 相对来说类(class)比较常用
+ #id{设置属性}
+ .class{设置属性}
+ 权重等级: id > class > 其他标签

Example
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style type="text/css">
        div{
            width: 200px;height: 200px;background-color: yellow;
        }
        #abc{
            width: 200px;height:200px;background-color: black;
        }
    </style>
</head>
<body>
    <div id="abc"></div>
    <div></div>
    <div></div>
    <div></div>
</body>
</html>
```

#### 2.2 后代选择器
+ 在 day 08 的时候有示范过了
```
div p{设置属性}
```
+ 设置 div 里面的 p 的属性
+ 也可以用类来使用后代选择器

Example
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 后代选择器 */
        div p{
            background-color: yellow;
        }
        /* 类别 */
        .mydiv p {
            background-color: aqua;
        }
    </style>
</head>
<body>
    <p>这是没有经过后代选择器的</p>
    <p>这是没有经过后代选择器的</p>
    <p>这是没有经过后代选择器的</p>

    <div>
        <p>这是经过后代选择器的</p>
        <p>这是经过后代选择器的</p>
        <p>这是经过后代选择器的</p>
    </div>

    <div class="mydiv">
        <p>这是经过后代选择器的,且有类别的</p>
        <p>这是经过后代选择器的,且有类别的</p>
        <p>这是经过后代选择器的,且有类别的</p>
    </div>
</body>
</html>
```
+ 更精准的选择需要的元素
+ 越精准的指定，权重越高
Example:
```
div p{
    background-color: yellow;
}
div {
    background-color: green;
}
```
+ div p 会被使用，因为它更精准

+ 如果里面有很多不同的 类(class)名，然后想要把全部都设置一样的属性
```
.类名1,.类名2,.类名3{设置属性}
```
+ 甚至可以不同的种类一起用
Example:
```
.类名1,#id1,#id2,.类名2,div p,div p{设置属性}
```
