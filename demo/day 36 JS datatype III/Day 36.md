## JavaScript - 基础

#### 三目运算符
+ 用于判断 true or false
+ 就是 if-else 的缩写
+ (条件?成功的执行的语句:失败的的执行的语句)

Example:
```
<script>

    // 三目运算符 
    alert(true?2:3);    // 2

    alert(false?2:3);   // 3

    alert(3 > 2?2:3);   // 2


    
    // 四目运算符
    alert((3 > 2 ? 1 : 0) ? 2 : 3);   // 2
</script>
```


#### 非运算符
+ ```!``` 符号，相当于相反
+ 可理解为 ‘不是’

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>! 符号的运用</title>
</head>
<body>
    <script>
        /*
        // ! 号(不是)的运用
        alert(true);    // true
        alert(!true);   // false
        */
    
        /*
        alert(document.getElementById('myDiv'));    // null，因为 myDiv 的元素还没有完成生成
        alert(!document.getElementById('myDiv'));    // true
        */

        // onload 使其外边的系统运行完成后，再运行自己里面的内容
        onload = function(){
            alert(document.getElementById('myDiv'));    // 显示对象名称，因为已经完成生成
            alert(!document.getElementById('myDiv'));    // false 
        }

    </script>
    <div id="myDiv"></div>
</body>
</html>
```

###### != 不等于
+ 只会返回 true or false

Example:
```
<script>
  alert(1 != 10);     // true
</script>
```


#### 或 ||
+ 条件只要一满足就不会往后看了
+ 条件只要不满足就会一直往后看

Example:
```
<script>

    var a = 10;
    var b = 20;

    /*
    // 前面对了，就不往后看
    if(a == 10 || b == 100){
        alert(1);
    }
    else{
        alert(0);
    }

    // 前面错了，就一直往后看直到对的为止
    if(a == 100 || b == 100 || a == 10){
        alert(1);
    }
    else{
        alert(0);
    }
    */

    alert(true || 100); //true
    alert(false || 100);    // 100
    alert(a = true || 100); // true
    alert(a = false || 100);    // 100
    alert(1?2:3 || 100);    // 2

</script>
```


#### 和 &&
+ 只要满足就一直往后看
+ 不满足就不往后看了

Example:
```
<script>

    var a = 10;
    var b = 20;

    /*
    // 前面满足，还是会继续往后检查
    if(a == 10 && b == 20){
        alert(1);
    }
    else{
        alert(0);
    }

    // 一旦前面不满足就不往后看了
    if(a == 100 && b == 20 && a == 10){
        alert(1);
    }
    else{
        alert(0);
    }
    */


    // if-else 语句的另一种写法
    if(window)alert(1); // 1

    window && alert(1); // 1
</script>
```

#### 和与或 && 与 || 的用法
Example:
```
<script>

    window && 0 || alert(1);    // true
    /*  因为前面的 window 是对的，
        然后继续往后看，0 是错的，但是由于它的后方是 ||
        因此就会往后继续进行判断，然后就把 1 打印出来了 */


    alert(window && false || true? 2:3);    // 2
    alert((window && false || true? 2:3) && (1?4:5));    // 4
</script>
```

#### setInterval
+ 无限执行的定时器
+ 可以跟无限个参数
+ 第一个是函数
+ 第二个是执行的毫秒
+ 第三个是参数

Example:
```
<script>

    var a = 10;
    var b = 20;
    var c = 100;

    setInterval(function (b, a) {
        alert(a);
    }, 1000, a, b);    // 一秒

</script>
```

#### clearInterval
+ 暂停定时器
+ clearInterval(变量);

Example:
```
<script>

    var timer = null;
    timer = setInterval(function(){
        console.log(1);
        onclick = function(){
            clearInterval(timer);
        }

    },1);

</script>
```


#### setTimeout
+ 设置定时器

Example:
```
<script>

    setTimeout(function(){
        console.log(1);
    },2000);    // 两秒后显示

</script>
```

+ 一旦第二个参数给的不正确，在 IE8+ 浏览器中会以 0 毫秒去执行

Example:
```
<script>
    setTimeout(function(){
        console.log(2);
    },'tgc');
</script>
```

+ 定时器会有误差
> + JS 的特性: 会先把非定时器处理结束在进行定时器内的内容

Example:
```
<script>
    var a;
    a = 5;
    setTimeout(function(){
        a = 10;
    },0);
    alert(a);   // 5

    var b;
    b = 5;
    setTimeout(function(){
        b = 10;
    },-1);
    alert(b);   // 5

    var c;
    c = 5;
    setTimeout(function(){
        c = 10;
    },3);
    alert(c);   // 5
</script>
```

#### ScreenLeft
+ 浏览器距离最左边的距离

#### ScreenTop
+ 浏览器距离最上面的距离
