## JavaScript - Standard Medium

#### 回收变量的方式
+ 设定变量为 null
+ 预解析
+ 对象引用

###### 预解析
+ 就是把 var 的变量在这块作用域下提前

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=5
    , initial-scale=1.0">
    <title>预解析</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        /* 这个位置有一个隐形的 var = a;，所以打印出来的结果是 undefined */
        alert(a);   // undefined
        var a = 10;
    </script>
</body>
</html>
```


#### in 的用法
+ 量 in 对象
+ 判断量是否在对象内
+ 如果在 true
+ 如果不在 false

Example:
```

```
