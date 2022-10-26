## 1-2 CSS 盒模式
+ 在 body 中的每个 HTML 标签实际上都被包围在一个看不见的矩形中，这个矩形就叫做 "盒"

#### 1-2-1 页面中的标签
#### 块级别的标签(Block-level Tag)
+ 块标签占据了容器的整个宽度
+ 容器指的是 <body> 标签
+ 每个块标签所在的盒都尽可能的占据页面的整个宽度
+ 例如: hx p ul ol li

#### 1-2-2 内联级别的标签(Inline-level Tag)
+ 如果一个标签不是块标签，它就是内联标签
+ 例如: img input label

#### 1-2-3 将块标签转换成内联标签
+ 有时候，你想把块标签转换成内联标签，需要设置 CSS 的 display 属性
+ 例如: 把导航栏现在的垂直显示修改为水平显示
Example(Test1.html):
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

#### 1-2-4 进入盒模式
+ 盒模式是描述标签的边框和间距的一种方式
+ 盒模式分为四种

| 内容区域 | content area | 内容区域中包含的是盒子中真正的内容(文本 图片等) |
| 补白或内边距| padding | padding 包围在内容区域的边缘，分为上 右 下 左四个区域 |
| 边框 | border | border 包围在 padding 的边缘，也分为上 右 下 左四个区域 |
| 边距 | margin | margin 包围在 border 的上 右 下 左四个边缘 |

##### 1-2-4-1 padding
Example(Test2.html):
```
h1{
    padding-top:6px;
    padding-right:3px;
    padding-bottom:0;
    padding-left:0;
}
```

Example(Shortcut):
```
h2{
padding:2px 2px 0 0;
}
/*padding:上 右 下 左*/
```

##### 1-2-4-2 border
Example(Test3.html):
```
h1{
    border-width:6px;
    border-style:solid;
    border-color:#030923;
}
```

Example(Shortcut):
```
h1{
    border:20px solid #030923;
}
···

##### 1-2-4-3 margin
Example(Test4.html):
```
h1{
    margin-top:6px;
    margin-right:6px;
    margin-bottom:0;
    margin-left:0;
}
```

Example(Shortcut):
```
h2{
margin:10px 10px 0 0;
}
/*margin:上 右 下 左*/
```

##### 1-2-4-4 浏览器的样式
+ 每个浏览器都有自己的默认浏览器样式
+ 重置浏览器样式方法:
Example(Test5.html):
```
html,body,h1,h2,h3,p,ol,ul,li,a{
    padding:0;
    border:0;
    margin:0;
}
```

