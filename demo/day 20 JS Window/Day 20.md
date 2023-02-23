## JavaScript Window

#### 1.1 js window 对象(object) 的详解
+ 如果 js 是地球，window 就是空气，谁离开 window 都活不下去
+ window 是可以省略的，比如:
> + ``` window.alert(); -> alert(); ```
> + ``` window.函数(); -> a(); ```
+ 总结: window 是全局的，所以谁都可以使用

+ 可以通过 window 从另一个函数提取另一个函数的变量
> + 比如我有一个 function b，然后我要从 function a 拿出 c 的值
> + Example:
> ```
> <script>
>     function a(){
>         window.c = 10;
>     };
>     function b(){
>         console.log(window.c);
>     };
>     a();
>     b();
> </script>
> ```

#### 1.2 js 检测浏览器的属性
+ 检测浏览器的可视宽度
Example:
```
<script>
    console.log(window.innerWidth);
</script>
```

+ 检测浏览器的可视高度
Example:
```
<script>
    console.log(window.innerHeight);
</script>
```

+ 检测浏览器的左边框与屏幕的左边框的距离
Example:
```
<script>
    console.log(window.screenLeft);
</script>
```

+ 检测浏览器的上边框与屏幕的上边框的距离
Example:
```
<script>
    console.log(window.screenTop);
</script>
```

#### 1.3 window 定时器
+ window 有两种定时器

###### 1.3.1 延时定时器
+ 只执行一次
+ window.setTimeout(函数,多少时间后使用) -> 1000 毫秒 = 1 秒
Example 1(一秒后):
```
<script>
    window.setTimeout(
        function(){
            console.log('我在一秒后执行')
        },1000)
</script>
```

+ 阻止延时定时器的方法: window.clearTimeout(变量)
Example:
```
<script>
    var timer = window.setTimeout(
        function(){
            console.log('我在一秒后执行')
        },1000)

        window.setTimeout(function(){
            window.clearTimeout(timer);
        },500);
</script>
```
+ 上面的代码说明:
> + 原本字符串内容将在一秒(1000)后打印，但是被指令在半秒(500)前就直接暂停了


###### 1.3.2 轮询定时器
+ 不会停的
+ window.setInterval(函数,多少时间后使用)
Example 1(一秒后重新执行):
```
<script>
    window.setInterval(
        function(){
            console.log('我在一秒后执行')
        },1000)
</script>
```

+ 暂停循环的方法: window.clearInterval(变量)
+ 通过添加变量，以及搭配延时定时器来阻止循环
Example
```
<script>
    var timer = window.setInterval(
        function(){
            console.log('我在半秒后执行')
        },500)

        window.setTimeout(function(){
            window.clearInterval(timer);
        },1200);
</script>
```
+ 上面的代码说明:
> + 原本字符串内容将在每个半秒(500)后打印一次，但是被指令在 1.2 秒(1200)后直接暂停了整个循环


#### 1.4 window 中打开和关闭页面的方法

###### 1.4.1 open 打开
+ 打开一个新的页面
+ 打开的方法: window.open('网址');
Example:
```
<script>
// 打开youtube
    window.open('https://www.youtube.com/')
</script>
```

Example(恶作剧):
```
<script>
// 会一直打开新的页面
    window.open('open.html')
</script>
```

###### 1.4.2 close 关闭
+ 关闭当前页面
+ 关闭的方法: window.close('网址');
Example:
```
<script>
    window.close('close.html')
</script>
```

#### 1.5 window 的特征

###### 1.5.1 window 里的 window
+ window 里面还有 window，且可以无限的去嵌套，也不影响结果
Example:
```
<script>
    window.window.window.alert(1);
</script>
```

###### 1.5.2 js 的 this/self/top 的用法
+ 在 <script> 的作用域里 this = self = top = window
Example:
```
<script>
    console.log(this == window);
    console.log(self == window);
    console.log(top == window);
    // output 显示 true
</script>
```













