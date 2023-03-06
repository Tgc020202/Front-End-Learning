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
> > + ![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2035%20JS%20BOM%20Print/p1.PNG)
+ 之后
> > + ![p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2035%20JS%20BOM%20Print/p2.PNG)

###### location.reload()
+ 刷新当前页面

###### history
+ history.back()    - 返回上一级
+ history.forward() - 返回下一级


#### JavaScript 的运算符








