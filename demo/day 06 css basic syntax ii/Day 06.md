## 1-2 CSS 盒模式
+ 在 body 中的每个 HTML 标签实际上都被包围在一个看不见的矩形中，这个矩形就叫做 "盒"

#### 页面中的标签
#### 块级别的标签(Block-level Tag)
+ 块标签占据了容器的整个宽度
+ 容器指的是 <body> 标签
+ 每个块标签所在的盒都尽可能的占据页面的整个宽度
+ 例如: hx p ul ol li

#### 内联级别的标签(Inline-level Tag)
+ 如果一个标签不是块标签，它就是内联标签
+ 例如: img input label

#### 将块标签转换成内联标签
+ 有时候，你想把块标签转换成内联标签，需要设置 CSS 的 display 属性
+ 例如: 把导航栏现在的垂直显示修改为水平显示
```
<!DOCTYPE html>
<html>
    <head>
        <title></title>
        <style type = "text/css">
            ul li{
                display:inline;
            }
        </style>
    </head>
    <body>
        <ul>
            <li>hello</li>
            <li>hi</li>
            <li>heyoo</li>
        </ul>
    </body>
</html>
```

