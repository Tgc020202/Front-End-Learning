## 1-4 div 布局入门(Getting started with div)

#### 1-4-1 div 标签
+ div: division 分区
+ 他是一个块标签
+ 要想区分每个 div, 常用的做法是给每个 div 添加一个 class 属性

Example(Test1.html):
```
<!DOCTYPE html>
<html>
    <head>
        <style type = "text/css">
            /*可以通过类名来改变内容的样式*/
            .header p{
                color:lightblue;
                text-decoration: underline;
            }

            .main-content p{
                color:red;
                text-decoration: solid;
                padding:0 20px;
                border:0 15px;
                margin:10px 0 15px 0;
            }
        </style>
    </head>
    <body>
        <div class = "header">
            <p>这是一个头的部分</p>
        </div>
        
        <div class = "main-content">
            <p>这是内容的部分</p>
        </div>
    </body>
</html>
```

+ div 的快捷键输入: div.(类名一) + div.(类名二) 以此类推

#### 1-4-2 内容居中
1. 将块标签中的内容居中
+ 设置块标签 text-align 的值为 center

Example(css):
```
h1{
    text-align:center;
}
```

2. 将块标签本身居中，并且这个块标签有固定的宽度
+ 设置块标签左右 margin 的值为 auto

Example(css):
```
.main-content{
    width:500px;
    margin 30px auto 0 auto;
}
```

