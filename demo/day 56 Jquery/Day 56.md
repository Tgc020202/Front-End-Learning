## Jquery
+ Jquery 是 JavaScript 的框架，通常都是新手使用。
+ 它所有的东西都脱离不了 JavaScript，它是一个封装的面向对象。
+ JavaScript 做不到的东西，它也做不到。
+ Jquery1.x.x 兼容 IE6 和其他浏览器。
+ Jquery2.x.x 不兼容 IE6，IE7，IE8。
+ Jquery3.x.x 兼容 IE6，IE7，IE8 以及增添了许多 ES6 的东西，也兼容了移动端，容量特别大。

+ ![Jquery 的安装网址](https://jquery.com/download/)
+ ![Jquery 的学习网址](https://jquery.cuishifeng.cn/)
+ ![Jquery 的 CDN 网址](https://releases.jquery.com/jquery/)

+ 本次学习用的是旧的版本 Jquery1.9.1 ![复制代码进去新的文件夹](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2056%20Jquery/jquery-1.9.1.min.js)


#### `$` 符号
+ 

#### extend 添加接口
+ 拓展功能
+ 里边可以传一个 JSON
+ 使用 `$` 符号将其调用

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>第一次使用 Jquery - $ 和 extend</title>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
</head>
<body>
    <!-- JavaScript -->
    <script>
        alert($);   // function(e,t){return new b.fn.init(e,t,r)}


        $.extend({
            'tgc':function(){
                alert("我是 tgc 函数");
            },
            'wxx':function(){
                return Math.random();
            },
            'bodyMax':function(){
                return {w:innerWidth,h:innerHeight};
            }
        });

        $.tgc();    // 我是 tgc 函数
        alert($.wxx()); // 随机数
        alert($.bodyMax().w);   // 返回当前屏幕宽度
    </script>
</body>
</html> 
```

