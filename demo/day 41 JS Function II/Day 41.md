## JavaScript - Function 函数

#### Function 的含义
+ 它是一条数据
+ function 变量名(){}
+ 如果直接执行这个变量名，那么它就会返回自己的内容

Example: 
```
<script>
    function a (){

    }
    console.log(a);   // 把函数内容打印出来
</script>
```

+ 每个函数都有自己默认的 return 的值，相当于 undefined

Example: 
```
<script>
    function a (){

    }
    console.log(a());   // undefined
</script>
```

+ 设置了 return 的值后，就会返回 return 的值

Example:
```
<script>
    function b (){
        return 18;
    }
    console.log(b());   // 18
</script>
```

#### 函数的用法
+ 方法一: 先设置一个函数，再设置调用函数的变量

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>设计给按钮执行函数的功能</title>
</head>
<body>
    <input type="button" name="" id="ipt1" value="a">
    <!-- JavaScript -->
    <script>
        // 函数的各种写法

        function a (){alert(1)}
        document.getElementById('ipt1').onclick = a;

    </script>
</body>
</html>
```

+ 方法二: 直接设置调用方法，紧接着函数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>设计给按钮执行函数的功能</title>
</head>
<body>
    <input type="button" name="" id="ipt2" value="b">
    <!-- JavaScript -->
    <script>
        // 函数的各种写法
        document.getElementById('ipt2').onclick = function(){alert(2)};
    </script>
</body>
</html>
```

+ 方法三: 在函数里面，设置 return 值为另一个函数，最后调用函数而不是变量
> + 变量没有括号`a`，而函数有括号`a()`

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>设计给按钮执行函数的功能</title>
</head>
<body>
    <input type="button" name="" id="ipt3" value="c">
    <!-- JavaScript -->
    <script>
        // 函数的各种写法
        function c (){
            return function(){
                alert(3);
            }
        }   
        document.getElementById('ipt3').onclick = c();
    </script>
</body>
</html>
```

+ 变量的形式创建函数，var 变量名 = function(){}; 是一个强类型的声明方式
+ function 函数名(){} 是一个弱类型的声明方式
+ 说明其他的类型会比较优先被调用，过后才轮得到它

Example:
```
<script>

    var a = function (){
        alert(1);
    }
    a();    // 弹出 1

    function b (){
        alert(2);   
    }
    b();    // 弹出 2


    var c = 100;
    function c (){
        alert(3); 
    }
    alert(c); // 100
</script>
```

+ 以变量的形式创建函数需注意，只能在赋予函数的变量后，才可以执行调用
+ 否则就无法执行

Example:
```
<script>
    d();    // 弹出 4
    e();    // 无法弹出
    function d(){
        alert(4);
    }

    var e = function(){alert(5);};
</script>
```

#### return
+ return 的默认值 = undefined

Example：
```
<script>

    function a(){
        return;
    }
    console.log(a());   // undefined
    console.log(a);

    function b(){
        return null;
    }
    console.log(b());   // null
</script>
```

+ 函数的 return 值，只要一看到 return，后面的指令就不执行了

Example:
```
<script>
    function c(){
        return;
        alert(100);
    }
    console.log(c());   // undefined，就结束了，100 没被执行
</script>
```

+ 放置 return 在 window 会报错，因为 window 只是环境，而不是函数

Example:
```
<script>
    return;
</script>
```

#### 匿名函数
+ 写法一: (function(){内容})();
+ 写法二: (function(){内容}());
+ 写法三: ~function(){内容}();   -> return 的值会等于 -(x)-1
+ 没有名字，一旦调用就结束了，里面的函数只能执行一次

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>匿名函数</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        (function(){alert(1);})();  // 弹出 1
        (function(){alert(1);}());  // 弹出 1
        ~function(){alert(1);}();   // 弹出 1

        (function(){
            var a = 10;
            alert(a);
        })();   // 弹出 10

        alert(a);   // 没有弹出
    </script>
</body>
</html>
```

+ 可以给予参数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>匿名函数</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        var a = 1,b = 2;
        (function(b,a){alert(a-b);})(a,b);  // 弹出 1
    </script>
</body>
</html>
```


###### 匿名写法三
+ 写法: ~function(){内容}();
+ return 的值跟平时的不太一样，return -(x)-1

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>匿名函数</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        (function(a){
            alert(a);
        })((function(){
            return 10;
        })());  // 弹出 10

        (function(a){
            alert(a);
        })(~function(){
            return 10;
        }());  // 弹出 -11 = -(10) -  1
        
        (function(a){
            alert(a);
        })(~function(){
            return -10;
        }());  // 弹出 9 = -(-10) -  1
    </script>
</body>
</html>
```


#### arguments 不定参
+ 可以使用下标
+ 类似数组，但是它不是数组

Example:
```
<script>
    function show(){
        alert(arguments[0]);
    }
    show(1,2,3);
</script>
```

+ 跟多详情可以看回 [Day 29 的笔记](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2029%20JS%20Function%20&%20Web%20function/Day%2029.md)









