## 1-3 css 选择器 II (selector II)

#### 1-3-1 使用类选择器
+ 给 HTML 标签增加一个 class 属性，然后给 class 属性填写一个值，这个值叫做类名
Example:
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

