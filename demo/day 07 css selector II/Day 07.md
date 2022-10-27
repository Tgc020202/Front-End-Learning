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
