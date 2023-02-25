## 1.1 JS 闭包

#### 1.1.1 定义
+ 子函数使用父函数变量的行为
+ 在 js 中，函数内部的局部变量只允许其子函数使用

Example:
```
<script>
    // 闭包
    function a(){
        // c 是在 a 里的局部变量 所以外面拿不到 c 数据
        var c = 10;

        function b(){
            console.log(c);
        }
    }
    a();
</script>
```
> 图文解析:
![解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2023%20JS%20random/p1.PNG)

> 这就是闭包

+ 父函数 不能使用 子函数的局部变量
+ 子函数 可以使用 父函数的局部变量
+ 闭包可以拓展父函数的空间，函数(变多)会越来越大

Example:
```
<script>
    // 闭包
    function a(){
        // c 是在 a 里的局部变量 所以外面拿不到 c 数据
        var c = 10;

        function b(){
            // f 是 b 函数的局部变量
            var f = 20;
            console.log(c);

            function d(){
                console.log(c);
            }
            d();    // d 函数是 b 的子函数，所以可以调用父函数继承下来的局部变量
        }
        b();    // a 函数可以启用自己的子函数

        console.log(f); // a 是父函数 不能使用子函数的局部变量
    }
    a();
</script>
```



## 1.2 JS 生命周期

#### 1.2.1 概念
+ 有生就有死
+ 当 js 检测不到该变量 该变量就会杀死该变量

Example:
```
<script>
    // 生命周期
    // a 出生了
    var a = 10; // 如果没有人用到它，这个变量就死了

    // 当 a 被使用完后，js 就又把它回收了
    alert(a);
    // 这里就会收了
</script>
```

+ 生命周期是可以延长的
+ 可以通过重新声明一个新的变量，并给予之前的变量的值

Example:
```
<script>
    function a(){
        var b = 20; // 这里 b 会被死掉

        function c(){
            var f = b;  // 但是 f 需要 b，所以 b 的生命周期被延长了
            console.log(f);
        }
        c();
    }
    a();
</script>
```

+ 可以使生命周期变成永恒
+ 可以把变量指向 window 就可以了
+ 因为 window 永远死不了

Example:
```
<script>
    function a(){
        var b = 20;

        function c(){
            window.f = b;   // window 是永远存在的，所以 b 就被永恒了
            console.log(f);
        }
        c();
    }   
    a();
</script>
```


## 1.3 JS 回收机制

#### 回收机制的解说
+ 变量相等于 null 就是被回收了

```
<script>
    var a = 10;

    a = null;   // 被回收了
</script>
```

#### 拓展
+ if-else statement 条件语句可以放无限个 else if

Example:
```
<script>
    var a = 10;
    if(a == 9){
        alert(1);
    }
    // 可以放无限个 else if
    else if(a == 10){
        alert(2);
    }
    else if(a == 2){
        alert(2);
    }
    else if(a == 1){
        alert(2);
    }
    else{
        alert(3);
    }
</script>
```

+ Numbers 里的 '不等于'
> 符号: !=

+ 返回函数的所有内容

Example:
```
<script>
    function a(){
        alert(1);
    }
    console.log(a);

    // 简单操作
    setTimeout(a,1000);
</script>
```

+ 随机数 random number
> + 随机出现 0 至 1 的数值
> + Math.random()

Example:
```
<script>
    console.log(Math.random());
</script>
```

+ parseInt(要转换的数据) 可以把小数或字符串变为整数
```
<script>
    console.log(parseInt(Math.random()));
</script>
```







