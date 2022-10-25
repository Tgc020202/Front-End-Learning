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
