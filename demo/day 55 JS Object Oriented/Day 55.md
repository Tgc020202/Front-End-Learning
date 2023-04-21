## JavaScript

### 面向对象 object-oriented
+ 所有的操作都是对对象的操作

#### 对象 object
+ new Object();
+ 万物皆是对象
+ 对象的机制:
> 1. 引用机制
> 2. 可赋予私有属性
> 3. 只要是对象就不相等的

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
> + this 永远指向发生事件的源头

Example：
```
<script>
    /* this 的指向*/
    var a = function(){
        alert(this);
    }

    // Bom
    // 实例化之后 this 就指向实例化对象
    // 没实例化之前 this 永远就指向 window
    new a();    // object Object

    // Dom
    // this 永远指向发生事件的源头
    a();    // object Window


</script>
```


##### 对象的第三个机制
+ 只要是对象就不相等，除非是引用的

Example:
```
<script>
    /*
        只要是对象就不相等
        除非是引用的
    */
    var a = [1,2,3];
    var b = a;
    var c = [1,2,3];
    var d = new Array(1,2,3);

    console.log(a == b);    // True
    console.log(a == c);    // False
    console.log(a == d);    // False
</script>
```

##### Constructor
+ 找到所有东西的原型函数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Constructor</title>
</head>
<body>
    <script>
        // 找到所有东西的原型函数
        alert(alert.constructor);   // function Function() { [native code] }
    </script>
</body>
</html>
```

##### Function 函数
+ 函数是一种 object
+ 它可以引用机制，也可赋予私有属性
+ 任何的函数都可以使用 call


##### call
+ 改变 this 的指向
+ call 的第一个参数就是 call 之前的函数的 this

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>call 改变 this 指向</title>
</head>
<body>
    <script>
        function a(){
            alert(this);
        }
        a.call(1);

        function b(){
            this.style.background = '#000';
        }
        b.call(document.body);
    </script>
</body>
</html>
```

+ 从第二个参数到以后的参数相等于函数的第一个参数到以后的参数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>call 改变 this 指向</title>
</head>
<body>
    <script>
        function a(x,y,z){
            alert(this);    // 1
            alert(x);   // 2
            alert(y);   //3
            alert(z);   // undefined
        }
        a.call(1,2,3);
    </script>
</body>
</html>
```

+ call 可以使函数执行完了

Example:
```
<script>
    function show(){
        this.a = 20;
        this.c = 25;
    }

    function show2(){
        this.a = 25;
        this.c = 30;
        show.call(this);
    }

    function show3(){
        show2.call(this);
    }

    alert(new show3().a + new show3().c);   // 45
</script>
```



