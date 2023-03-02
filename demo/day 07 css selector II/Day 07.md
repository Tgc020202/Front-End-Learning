## 1-3 css 选择器 II (selector II)

#### 1-3-1 使用类选择器
+ 给 HTML 标签增加一个 class 属性，然后给 class 属性填写一个值，这个值叫做类名

Example(Test1.html):
```
<!DOCTYPE html>
<html>
    <head>
        <title>使用类选择器</title>
        <style type = "text/css">
        /*使用类名(nav)将左侧的补白清除掉*/
            .nav{
                padding-left:0;
            }
        </style>
    </head>
    <body>
        <!-- 取一个类名 -->
        <ul class = "nav">
            <li><a href = "home.html">没补白例子一</li>
            <li><a href = "recipes.html">没补白例子二</li>
            <li><a href = "suggest.html">没补白例子三</li>
        </ul>
        <ul>
            <li><a href = "home.html">有补白例子一</li>
            <li><a href = "recipes.html">有补白例子二</li>
            <li><a href = "suggest.html">有补白例子三</li>
        </ul>

    </body>
</html>
```
> + 可以通过添加类名更改它的属性

#### 1-3-2 在派生选择器中使用类
+ 类选择器和派生选择器可以同时使用

Example(Test2.html):
```
<!DOCTYPE html>
<html>
    <head>
        <title>使用类选择器</title>
        <style type = "text/css">
        /*查找 nav 这个类名所在标签的子孙标签，并且这些子孙标签的名字是 a */
            .nav a{
                color:#54a5d4;
                text-decoration: none;
            }

        /*将已经命名为 nav 的类 设置成内联标签*/
            .nav li{
                display:inline;
            }
        </style>
    </head>
    <body>
        <!-- 取一个类名 -->
        <ul class = "nav">
            <li><a href = "home.html">内联标签例子一</li>
            <li><a href = "recipes.html">内联标签例子二</li>
            <li><a href = "suggest.html">内联标签例子三</li>
        </ul>
        <ul>
            <li><a href = "home.html">没内联标签例子一</li>
            <li><a href = "recipes.html">没内联标签例子二</li>
            <li><a href = "suggest.html">没内联标签例子三</li>
        </ul>

    </body>
</html>
```

#### 1-3-3 利用开发者工具
+ 编辑需要跟改的部分
+ 可通过类名将特定的文本变成自己想要设计的样式
+ 开发工具快捷键(ctrl + shift + i)

#### 1-3-4 把 css 放在独立的文件中
+ 创建一个独立的文件，扩展名是 .css ，把所有的 css 规则都放在这个文件里
Example:
```
<html>
    <head>
        <style type = "text/css">
            a{
                color:red;
            }
            /*所有其他样式*/
        </style>
    </head>
    <body>
    </body>
</html>
```
+ 转移去 main.css 并将所有的选择器和 css 样式规则移动到 css 文件中，不包括<style> 标签
Example(main.css):
```
a{
    color:red
}
```

#### 1-3-5 link 标签
+ 在 HTML 文件中使用 link 标签链接独立的 css 文件
+ link 标签是空标签，只写开始标签，不写结束标签
Example(Test4.html):
```
<html>
 <head>
    <link type = "text/css" rel = "stylesheet" href = "main.css">
 </head>
 <body>
 </body>
</html>
```
+ 过后就可以在 main.css 文件里调整 html 里文档的样式了
