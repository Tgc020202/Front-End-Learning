## JavaScript

### 面向对象 object-oriented
+ 所有的操作都是对对象的操作

#### 对象 object
+ new Object();
+ 万物皆是对象
+ 对象的机制:
> 1. 引用机制
> 2. 可赋予私有属性

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Object 对象的机制</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        var a = document.body;

        // 引用机制
        var b = a;
        b.style.background = 'black';   // body 变黑

        // 可赋予私有属性
        b.index = 1;
        alert(a.index); // 弹出 1
    </script>
</body>
</html>
```

##### 分辨对象
+ 除了 dom 元素，bom 元素(string,boolean,...) 里面需要添加 new(实例化) 才可以定义为对象.

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>new 实例化</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        var a = String(123);

        var b = a;
        b.c = 10;
        console.log(a.c);   // undefined


        // 使用 new 实例化
        var a = new String(123);

        var b = a;
        b.c = 10;
        console.log(a.c);   // 10
    </script>
</body>
</html>
```

##### 对象 this 的指向
+ Bom
> + 实例化之后 this 就指向实例化对象
> + 没实例化之前 this 永远就指向 window
+ Dom
