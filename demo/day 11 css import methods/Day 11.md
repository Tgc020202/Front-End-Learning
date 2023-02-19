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
