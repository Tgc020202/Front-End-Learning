## JavaScript - Standard Medium

### 回收变量的方式
+ 设定变量为 null
+ 预解析
+ 对象引用

#### 预解析
+ 就是把 var 的变量在这块作用域下提前
+ 变量虽然提前了，但是没有在 window 上

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
        /* 这个位置有一个隐形的 var = a，所以打印出来的结果是 undefined */
        alert(a);   // undefined
        var a = 10;

        // 证明 b 一开始并就在 window 上
        console.log('b' in window);   // true
        console.log(b);     // undefined
        var b = 10;   // 因为是在 window 创建的变量，所以才会 true

        // 可使用函数将其与 window 隔开
        onload = function(){
            // 证明 c 一开始并不在 window 上
            console.log('c' in window);   // false
            console.log(c);     // undefined
            var c = 10;
        }
    </script>
</body>
</html>
```

1. 只会在当前作用域内的变量进行预解析，不受当前作用域外的变量的影响

Example:
```
<script>
    window.b = 100;

    // 证明预解析会在当前作用域下提前，跟全局没有关系
    function a(){
        alert(b);   // undefined
        var b = 10;
    }
    a();
</script>
```

2. script 也是相当于一个作用域

Example 1:
```
<script>
    alert(a);   // error
</script>

<script>
    var a = 10;
</script>
```

Example 2:
```
<script>
    var b = 10;
</script>

<script>
    alert(b);   // 10
</script>
```

Example 3:
```
<script>
    function a(){
        window.b = 10;
    }
    a();
    alert(b);
</script>
```
> + Example 2 与 Example 3 的概念相同

3. 预解析用在函数上没有问题

Example:
```
<script>
    // 先执行函数，没有问题
    a();
    function a(){
        alert(1);
    }    
</script>
```

4. 如果函数的预解析用在两个不同的 script 里，会报错

Example:
```
<script>
    a();    // error
</script>


<script>
    function a(){
        alert(1);
    }
</script>
```

5. 先在前面的 script 调用函数，再执行函数就没有问题

Example 1:
```
<script>
    function a(){
        alert(1);
    }
</script>

<script>
    a();    // 1
</script>
```

Example 2:
```
<script>
    function Script(){
        function a(){
            alert(1);
        }
        a();
    }
    Script();
</script>
```
> + Example 1 与 Example 2 相当于同一个概念

#### 对象引用
+ 对象两个机制:
1. 引用
2. 可以给予私有属性

Example 1(Array 数组对象):
```
<script>
    var a = [1,2,3];

    var b = a;
    b.push(100);

    console.log(a); // [1,2,3,100]
</script>
```

Example 2(Date 时间对象):
Example:
```
<script>
    var a = new Date();

    var b = a;
    b.setMonth(2);

    console.log(a.getMonth());  // 2
</script>
```


Example 3(String 字符对象):
```
<script>
    var a = new String('123');

    var b = a;
    // 给予私有属性
    b.a = 10;
    alert(a.a); // 10
</script>
```



#### in 的用法
+ 量 in 对象
+ 判断量是否在对象内
+ 如果在 true
+ 如果不在 false

Example:
```
<script>
    /* in 用来判断量是否存在于对象内 */
    var a = 10;
    var x = y = z = 100;

    alert('a' in window);   // true
    alert('b' in window);   // false
    alert('z' in window);   // true
    
</script>
```

+ 可用于 HTML 的元素
+ HTML 的元素的属性 id 和 classname 都会显示 true，但是大部分的属性都会显示 false

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>in 的使用</title>
</head>
<body>

    <div id="haha" class="div1" tgc="wow"></div>
    <!-- JavaScript -->
    <script>
        var a = document.getElementById('haha');
        console.log('id' in document.body); // true
        console.log('className' in document.body); // true
        console.log('class' in a); // false
        console.log('tgc' in a); // false
        console.log('id' in a); // true


        var attr = a.getAttribute('tgc');
        console.log('attr' in a);   // false
    </script>
</body>
</html>
```

+ 使用 in 在 window 对象

Example:
```
<script>
    console.log('alert' in window); // true
    console.log('window' in window);    // true
    console.log('console' in window);   // true
    console.log('log' in console);  // True


    // window 对象的特性
    console.log(window == this);    // true
    console.log(window == self);    // true
    console.log(window == top);     // true
    console.log(window == parent);  // true
</script>
```

#### Date 对象
+ 时间对象
+ 取得当前的时间与日期

Example:
```
<script>
    var a = new Date();

    alert(a);   // 取得当前的时间日期
</script>
```

+ 在 JS 里，1000 = 1000 毫秒 = 1 秒

Example:
```
<script>
    var a = 999999;

    // 1000 毫秒 = 1 秒
    var second = parseInt(a/1000);
    var minute = parseInt(second/60);
    var hour = parseInt(minute/60);

    console.log(second);
    console.log(minute);
    console.log(hour);

    console.log('时间 : ' + minute + '分钟' + a % 1000 % 60 + '秒')
</script>
```

###### getTime()
+ getTime() 是从 1970 年 1 月 1 日 00:00:00 到现在经过的毫秒，相当于时间戳

Example:
```
<script>
    var a = new Date().getTime();

    console.log(a);
    // 计算最大的值先，例如: 年
    var second = parseInt(a/1000);
    var minute = parseInt(second/60);
    var hour = parseInt(minute/60);
    var day = parseInt(hour/24);
    var month = parseInt(day/30);
    var year = parseInt(month/12);

    // 重新赋值给最大值以外的
    var second = a % 1000 % 60;
    var minute = a % 1000 % 60 % 60;
    var hour = a % 1000 % 60 % 60 % 24;
    var day = a % 1000 % 60 % 60 % 24 % 30;
    var month = a % 1000 % 60 % 60 % 24 % 30 % 12;


    console.log('时间 : ' + year + '年' + day + '天' + hour + '时' + minute + '分钟' + second + '秒');
    // 1970.1.1 00:00:00 全世界统一的时间的开始
</script>
```

###### getFullYear()
+ 返回当前的年数

Example:
```
<script>
    var a = new Date();

    console.log(a.getFullYear());   
</script>
```

###### getMonth()
+ 返回当前月份
+ 从 0 开始计算
+ 例如，一月就会显示 0

Example:
```
<script>
    var a = new Date();

    console.log(a.getMonth());      
</script>
```


###### getDate()
+ 返回当前日数

Example:
```
<script>
    var a = new Date();

    console.log(a.getDate());      
</script>
```


###### getHours()
+ 返回当前的小时数
+ 24 小时计算

Example:
```
<script>
    var a = new Date();

    console.log(a.getHours());      
</script>
```

###### getMinutes()
+ 返回当前的分钟

Example:
```
<script>
    var a = new Date();

    console.log(a.getMinutes());      
</script>
```

###### getSeconds()
+ 返回当前的秒数

Example:
```
<script>
    var a = new Date();

    console.log(a.getMinutes());      
</script>
```

###### getDay()
+ 返回星期几
+ 0 相当于星期日
+ 1 ~ 6 相当于星期一至六

Example:
```
<script>
    var a = new Date();

    console.log(a.getDay());      
</script>
```

###### setMonth()
+ 改变月份成当前的 + 或者 - 的多少个月
+ setMonth(月份的数量)
+ 比如，setMonth(0); 
> + 设置为0，相当于一月份

Example:
```
<script>
    var a = new Date();
    // 设置月份
    a.setMonth(5);
    console.log(a.getMonth());  // 5

    var a = new Date();
    a.setMonth(24); // 相当于两年
    // 当前年份为 2023，但是加了24个月，就变成了2025
    console.log(a.getFullYear());    // 2025


    var a = new Date();
    a.setMonth(-24); // 相当于倒退两年
    // 当前年份为 2023，但是减去24个月，就变成了2021
    console.log(a.getFullYear());    // 2023


</script>
```

###### set所有的都有
+ set 结束后，get 就会获取刚刚 set的东西
+ setDate()
> + 改变日数
+ setTime()
> + 改变毫秒
+ setFullYear()
> + 改变年数
+ setHours()
> + 改变时数
+ setMinutes()
> + 改变分
+ setSeconds()
> + 改变秒数

Example:
```
<script>
    var a = new Date();
    a.setTime(2);
    a.setFullYear(520);
    a.setHours(9);
    a.setMinutes(2);
    a.setSeconds(3);
    a.setDate(1314);
    
    console.log(a.getTime());
    console.log(a.getFullYear());
    console.log(a.getHours());
    console.log(a.getMinutes());
    console.log(a.getSeconds());
    console.log(a.getDate());
</script>
```



