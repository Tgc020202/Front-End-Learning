# CSS 基本语法
#### 1-0 基本语法
Example:
```
<!DOCTYPE html>
<html>
  <head>
    <style type = "text/css">
        a{
            text-decoration: none;
            color:black;
        }

        /*未访问的链接，和a{}相同且同时存在时会覆盖*/
        a:link{
            color:darkblue;
        }

        /*鼠标移动到超链接上时*/
        a:hover{
            text-decoration: underline;
            color:darkred;
        }
        /*被选定的超链接*/
        a:active{
            text-decoration: underline;
            color: yellow;
        }
        /*已访问的超链接*/
        a:visited{
            color: lightblue;
        }
    </style>
  </head>
  <body>
  </body>
</html>
```

#### CSS 字体属性

| 属性 | 描述 |
|------|------|
| font | 在一个声明中设置所有字体属性 |
| font-family | 规定文本的字体系列 |
| font-size | 规定文本的字体尺寸 |
| font-size-adjust | 为元素规定 aspect 值 |
| font-stretch | 收缩或拉伸当前的字体系列 |
| font-style | 规定文本的字体样式 |
| font-variant | 规定是否以小型大写字母的字体显示文本 |
| font-weight | 规定字体的粗细 |

#### CSS 可能的值

| 值 | 描述 |
|------|------|
| xx-small,x-small,small,medium,large,x-large,xx-large | 把字体的尺寸设置为不同的尺寸，从 xx-small 到 xx-large。默认值为 medium |
| smaller | 把 font-size 设置为比父元素更小的尺寸 |
| larger | 把 font-size 设置为比父元素更大的尺寸 |
| length | 把 font-size 设置为一个固定的值 |
| % | 把 font-size 设置为基于父元素的一个百分比值 |
| inherit | 规定应该从父元素继承字体尺寸 |
+ 改变 p 里面的首字母(比如改变大小，改变颜色等)
Example:
```
<!DOCTYPE html>
<html>
  <head>
    <style>
        p:first-letter{
            font-size: 200%;
            color:blueviolet;
        }
    </style>
  </head>
  <body>
  </body>
</html>
```
