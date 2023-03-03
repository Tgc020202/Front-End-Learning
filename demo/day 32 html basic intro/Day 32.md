## 基础介绍
+ html = 超文本标记语言
+ css = 层叠样式表
+ js = 脚本语言
+ http = 超文本传输协议
+ https = 经过 ssl 加密的超文本传输协议


## html & css & js 之间的联系
+ 结构表现和行为
> + html - 结构层
> + css - 表现层
> + js - 行为层


## <!DOCTYPE html>
+ 文档头，用于浏览器解析文档的种类
+ xhtml 是 html5 之前的东西


## 编辑器 ide
+ sublime，webstorm，vscode
+ 用于写代码的工具


## html 标签
+ ```<html>```
+ 让计算机开始知道我们要开始写 html 了


## head 标签
+ ```<head>```
+ 写在头部的东西，页面里不会出现
+ 通常用于设计元素或是标签的属性


## meta 标签
+ ```<meta charset="UTF-8">```
+ 它会告诉浏览器，我们的页面的一些资讯(seo 优化)
> + charset="UTF-8"
> > + 通常都会用 utf-8 编码去解析


## title 标签
+ ```<title></title>```
+ 页面的主题，会显示在网页的最顶层
+ 默认为文件的名字


## body 标签
+ ```<body>```
+ 主体


## html 的三个元素种类
1. 块状元素
> + 以矩形的形式独占一行，并支持宽高
> + 默认的宽度并不是 100%，只是独占一行而已
> + 例子: div / p / hx / ul / li / ol / body / dl / dd / dt / html / table ...

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Html 的基础</title>
    <style>

        /* 清除默认值 */
        *{padding: 0;margin: 0;}

        div{
            background-color: black;
            height: 200px;
            width: 100%;      /* 可自行注释尝试*/
            margin-left: 100px;
        }
    </style>
</head>
<body>
    <div></div>
</body>
```

2. 行内元素/内联元素
> + 不支持宽高，大小会随着内容变大
> + 例子: span / a / b / i / img / br / meta / style / title / input / button / select ...

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Html 的基础</title>
    <style>

        /* 清除默认值 */
        *{padding: 0;margin: 0;}
        span{
            background-color: red;
            height: 200px;
            width: 100%;
            width: 100%;
        }
    </style>
</head>
<body>
    <span>span</span>
</body>
```

3. 可变元素
> + 例子: iframe - 镜像别页面

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iframe 的使用</title>
    <style>

        /* 清除默认值 */
        *{padding: 0;margin: 0;}
        iframe{
            height: 100%;
            width: 50%;
            position: absolute;
        }

        #next{left: 50%;}
    </style>
</head>
<body>
    <iframe src = "http://www.jd.com"></iframe>
    <iframe src = "http://www.jd.com" id="next"></iframe>
</body>
```

## xmp 标签
+ 可以让 html 里的所有标签都在页面中显示出来


## 让 style 的内容显示在页面里
+ 把 style 标签移动到 body 标签里
+ 再在 style 标签里添加 style="display:block"

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>显示 style 的内容在页面</title>
</head>
<body>
    <style type="text/css" style="display:block">
        *{padding: 0;margin: 0;}

        div{
            background-color: black;
            height: 200px;
            width: 100%;    /* 可自行注释尝试*/
            margin-left: 100px;
        }
    </style>
</body>
</html>
```

## 编辑属性 contenteditable
+ 写法: contenteditable="true"
![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2032%20html%20basic%20intro/p1.PNG)

+ 也可以搭配 style，实行在页面编辑其他元素的属性

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>编辑属性 contenteditable</title>
</head>
<body>

    <style style="display:block" contenteditable="true">

        /* 清除默认值 */
        *{padding: 0;margin: 0;}

        /* 可在页面编辑属性 */
        div{
            background-color: green;
            height: 200px;
            width: 100%;
            margin-left: 100px;
        }
    </style>

    <div></div>
    
</body>
</html>
```















