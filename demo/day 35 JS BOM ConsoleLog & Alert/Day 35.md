## JavaScript 基础

#### alert 弹窗
+ 弹出警告窗
+ 它是一种函数
+ 有些对象无法弹窗

Example:
```
<script>

    // 显示出 alert 的函数
    alert(alert);

    var json = {'a':10,'b':20};
    alert(json);    // 只会显示这是对象

    var arr = [1,2,3];
    alert(arr);     // 数组的会显示内容

</script>
```


#### console 打印
+ console.log 打印
+ console.error 错误
+ console.warn 警告
+ console.info 提示

Example:
```
<script>

    var json = {'a':10,'b':20};
    console.log(json);

    console.error(1);

    console.warn(1);

    console.info(1);

    console.log(console);
</script>
```


#### screen 屏幕(JS 跨界)
+ screen.height - 屏幕的高
+ screen.width  - 屏幕的宽

Example:
```
<script>

    console.log(screen);    // screen 里的属性与函数

    console.log(screen.height);

    console.log(screen.width);
    console.log(window.screen.width);
</script>
```


#### window.open('页面地址'); 
+ 可以打开新的页面

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>open 打开新的页面</title>
</head>
<body>

    <input type="button" name="" value='Youtube' id="ipt">
    <!-- JavaScript -->
    <script>
        document.getElementById('ipt').onclick = function(){
            open('https://www.youtube.com/');
        };
    </script>
</body>
</html>
```

#### window.close();
+ 可以关闭当前的页面

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>close 关闭页面</title>
</head>
<body>

    <input type="button" name="" value='close' id="ipt">
    <!-- JavaScript -->
    <script>
        document.getElementById('ipt').onclick = function(){
            close();
        };
    </script>
</body>
</html>
```

#### Location
###### location.href = '页面地址';
+ 可以让当前页面进行页面跳转

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Location</title>
</head>
<body>

    <input type="button" name="" value='Youtube' id="ipt">
    <!-- JavaScript -->
    <script>
        document.getElementById('ipt').onclick = function(){
            location.href = 'https://www.youtube.com/'; // 可以使当前页面直接进入此网址
        };
    </script>
</body>
</html>
```
+ 点击按钮的前后对比
+ 之前
> > + ![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2035%20JS%20BOM%20ConsoleLog%20%26%20Alert/p1.PNG)
+ 之后
> > + ![p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2035%20JS%20BOM%20ConsoleLog%20%26%20Alert/p2.PNG)

###### location.reload()
+ 刷新当前页面

###### history
+ history.back()    - 返回上一级
+ history.forward() - 返回下一级


#### JavaScript 的运算符
##### 一个等号 = 
+ 赋值

##### 两个等号 == 
+ 等同/等于
+ 两边值类型不同的时候，要先进行类型转换，再比较。
+ 返回 true or false

##### 三个等号
+ 恒等/全等
+ 数据格式必须都一样才会返回 true，不然就是 false

Example:
```
<script>
    // 等于符号
    var a = 10, b = 15, c = 20;

    alert(a = b);   // 15
    alert(a == b);  // true
    alert(a = c);   // 20
</script>
```

##### ```++ or --``` 符号
+ ```++ / --``` 放前面就会数值先发生变化
+ ```++ / --``` 放后面就会相反

Example:
```
<script>    
    // ++ 符号
    var a = 10,b = 10;

    alert(a++); // 先打印，再加一
    alert(a)    // 变成 11 了

    alert(++b); // 先加一，再打印出来

    // -- 符号
    var a = 10,b = 10;

    alert(a--); // 先打印，再加一
    alert(a)    // 变成 11 了

    alert(--b); // 先加一，再打印出来
</script>
```

##### ```+= or -= or *= or /= or %=``` 符号
+ ```a += 10``` 相当于 a = a + 10
+ 其他的种类也与 上述例子相同

Example:
```
<script>    
    // +=
    var a = 10;
    a += 1;
    alert(a);   // 11

    // -=
    var a = 10;
    a -= 1;
    alert(a);   // 9

    // *=
    var a = 10;
    a *= 10;
    alert(a);   // 100

    // /=
    var a = 10;
    a /= 2;
    alert(a);   // 5

    // %=
    var a = 10;
    a %= 2;
    alert(a);   // 0
</script>
```

##### 字符串与运算符的关系

Example:
```
<script>
    // 用 + 来连接字符串和数值
    alert(1+'2');   // 12

    // 用 * 来连接字符串和数值
    alert(1*'2');   // 2

    // 用 - 来连接字符串和数值
    alert(1-'2');   // -1

    // 用 / 来连接字符串和数值
    alert(1/'2');   // 0.5

    /* 总结: 除了加法，其他的都可以给字符串和数值进行算法 */

</script>
```

+ 字符串拼接，用 + 号来进行拼接

Example:
```
<script>
    alert(1+'2');   // 12
    alert('1'+1+'1');   // 111
    alert('大'+'呆呆');    // 大呆呆
</script>
```

+ 可将字符串使用 + 法以外的算法，使其变为数值类型

Example:
```
<script>
    alert(1+'2'*3); // 7
    alert(typeof(1+'2'*3)); // number
</script>
```

##### 比较 ```> or < or >= or <=```
+ 返回 true or false

##### JS 的计算
+ 不是特别的精准
+ 有 bug

Example:
```
<script>
    alert(0.2 + 0.2);   // 0.4
    alert(0.1 + 0.2);   // 0.30000000000000004
</script>
```

##### 计算会从左到右进行

Example:
```
<script>
    alert(1 > 2 == false);  // true
    alert(false === true);  // false

    //   1 > 2 == false -> true
    //   true === true -> true
    alert(1 > 2 == false === true); // true

    //   1 > 2 == false -> true
    //   true (boolean) === true - 1 (number)-> false
    alert(1 > 2 == false === true - 1); // false
</script>
```

##### () 算法
+ 先算小括号里面的，再算外面的

##### 优先级
+ 先算 * / % 才开始计算 + -
