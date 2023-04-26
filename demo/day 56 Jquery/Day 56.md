## Jquery
+ Jquery 是 JavaScript 的框架，通常都是新手使用。
+ 它所有的东西都脱离不了 JavaScript，它是一个封装的面向对象。
+ JavaScript 做不到的东西，它也做不到。
+ Jquery1.x.x 兼容 IE6 和其他浏览器。
+ Jquery2.x.x 不兼容 IE6，IE7，IE8。
+ Jquery3.x.x 兼容 IE6，IE7，IE8 以及增添了许多 ES6 的东西，也兼容了移动端，容量特别大。

+ [Jquery 的安装网址](https://jquery.com/download/)
+ [Jquery 的学习网址](https://jquery.cuishifeng.cn/)
+ [Jquery 的 CDN 网址](https://releases.jquery.com/jquery/)
+ [Jquery Color 的 CDN 网址](https://releases.jquery.com/color/)

+ 本次学习用的是旧的版本 Jquery1.9.1 [复制代码进去新的文件夹](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2056%20Jquery/jquery-1.9.1.min.js)
+ Jquery Color [复制代码进去新的文件夹](https://github.com/jquery/jquery-color/blob/main/jquery.color.js)


#### `$` 符号
+ function(e,t){return new b.fn.init(e,t,r)}

#### extend 添加接口
+ 拓展功能
+ 里边可以传一个 JSON
+ 写法: $.extend(JSON);
+ 调用: $.自定义函数名();

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

#### $.fn.extend 添加一个方法接口
+ 与 extend 的差别在于，它可以放置参数
+ 写法: $.fn.extend(JSON);
+ 调用: $(参数).自定义函数名();
> + 参数可以是元素名，元素 id 或者元素的类名

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jquery - fn.extend 的用途</title>

    <style>
        .m{
            width: 100px;
            height: 100px;
            background-color: black;
        }
    </style>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
</head>
<body>
    <div></div>
    <!-- JavaScript -->
    <script>
        // $('div').addClass('m');

        $.fn.extend({
            'tgc' : function(){
                console.log(this);  // 这个 this 是一个数组
                // this[0].className = 'm';

                // 也可以使用 Jquery 的方法
                $(this).addClass('m');
            }
        });
        
        // 可放置参数 'div'
        $('div').tgc(); // this 指向 div 了
    </script>
</body>
</html> 
```

#### error 报错
+ Jquery 不可以用原生的接口
+ 原生不可以用 Jquery 的接口

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jquery - fn.extend 的用途</title>

    <style>
        .m{
            width: 100px;
            height: 100px;
            background-color: black;
        }
    </style>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
</head>
<body>
    <div></div>
    <!-- JavaScript -->
    <script>
        // Jquery 不能用原生的接口
        $('div').className('m');    // 报错

        // 原生不可以用 Jquery 的接口
        document.getElementById('div')[0].addClass('m');    // 报错
    </script>
</body>
</html> 
```

#### 用原生方法写 Jquery

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS 封装 Jquery 的原理</title>
    <style>
        .m{
            width: 100px;
            height: 100px;
            background-color: black;

            margin: 10px;
        }
    </style>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
</head>
<body>
    <div class="div"></div>
    <div class="div"></div>
    <div class="div"></div>
    <div id="div"></div>

    <!-- JavaScript -->
    <script>
        function Jquery(obj){
            this.ele = obj.charAt(0);
            this.arr = [];
            switch(this.ele){
                case '.':
                    var all = document.getElementsByTagName('*');
                    for(var i = 0; i < all.length ;i++){
                        if(all[i].className.indexOf(obj.substring(1)) != -1){
                            this.arr.push(all[i]);
                        }
                    }
                    break;
                case '#':
                    this.arr.push(document.getElementById(obj.substring(1)));
                    break;
                default:
                    var all = document.getElementsByTagName(obj);
                    for(var i = 0; i < all.length ;i++){
                        this.arr.push(all[i]);
                    }
                    break;
            }
        };

        Jquery.prototype = {
            'addClass':function(s){
                for(var i = 0; i < this.arr.length ;i++){
                    this.arr[i].className = s;
                }
            },
            'width':function(s){
                for(var i = 0; i < this.arr.length ;i++){
                    // 检测有没有 px 在 s 里边
                    this.arr[i].style.width = /px$/.test(s) ? s : s += 'px';
                }
            },
            'css':function(){
                // width , 200
                if(arguments.length == 2){
                    for(var i = 0 ; i < this.arr.length; i++){
                        this.arr[i]['style'][arguments[0]]  = /px$/.test(arguments[1]) ? arguments[1] : arguments[1] += 'px';
                    }
                }
                // JSON
                if(arguments.length == 1){
                    // console.log(arguments[0]);
                    for(var i in arguments[0]){
                        for(var j = 0; j < this.arr.length ;j++){
                            this.arr[j]['style'][i] = /px$/.test(arguments[0][i]) ? arguments[0][i] : arguments[0][i] += 'px';
                        }
                    }
                }
            }
        }

        function $(string){
            return new Jquery(string);
        }

        // $('#div').addClass('m');
        // $('.div').addClass('m');
        // $('div').addClass('m');
        // $('#div').width("100");
        // $('.div').width("100");
        // $('div').width("100");
        // $('div').css('width',400);
        
        $('div').css({
            'width':200,
            'height':300
        })
    </script>
</body>
</html>
```

#### Jquery - Animate
+ 变色插件 Jquery Color
1. 需要安装 Jquery Color 插件
> + Jquery Color [复制代码进去新的文件夹](https://github.com/jquery/jquery-color/blob/main/jquery.color.js)
2. 也可以通过 CDN 使用插件
> + [Jquery Color 的 CDN 网址](https://releases.jquery.com/color/)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animate 运动方法的方式拓展</title>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
    <script type="text/javascript" src="jquery.color.js"></script>
    <style>
        *{
            margin: 0;
            padding: 0;
        }

        body,html{
            height: 100%;
            background-color: yellow;
        }
    </style>
</head>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        $('body').animate({
            'backgroundColor':'green'
        },3000);
    </script>
</body>
</html>
```

+ Animate 运动的核心是定时器
+ 默认运动形式
> + swing - 线性运动
> + linear - 匀速运动

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animate 运动方法的方式拓展</title>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
    <script type="text/javascript" src="jquery.color.js"></script>
    <style>
        *{
            margin: 0;
            padding: 0;
        }

        body,html{
            height: 100%;
            background-color: yellow;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: black;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
    </style>
</head>
</head>
<body>
    <div id="div1"></div>
    <div id="div2"></div>

    <!-- JavaScript -->
    <script>
        $('body').animate({
            'backgroundColor':'green'
        },3000);

        $('#div1').animate({
            'width':'400px'
        },3000,'swing');

        $('#div2').animate({
            'width':'400px'
        },3000,'linear');
    </script>
</body>
</html>
```

+ 其他运动形式的插件 Jquery.easing.js
> + [复制代码进去新的文件夹](https://github.com/gdsmith/jquery.easing/blob/master/jquery.easing.js)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animate 运动方法的方式拓展</title>
    <script type="text/javascript" src="jquery-1.9.1.min.js"></script>
    <script type="text/javascript" src="jquery.color.js"></script>
    <script type="text/javascript" src="jquery.easing.js"></script>
    <style>
        *{
            margin: 0;
            padding: 0;
        }

        body,html{
            height: 100%;
            background-color: yellow;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: black;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: blue;
        }

        #div3{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div4{
            width: 100px;
            height: 100px;
            background-color: lightblue;
        }
    </style>
</head>
</head>
<body>
    <div id="div1"></div>
    <div id="div2"></div>
    <div id="div3"></div>
    <div id="div4"></div>

    <!-- JavaScript -->
    <script>
        $('body').animate({
            'backgroundColor':'green'
        },3000);

        $('#div1').animate({
            'width':'400px'
        },3000,'swing');

        $('#div2').animate({
            'width':'400px'
        },3000,'linear');

        $('#div3').animate({
            'width':'400px'
        },3000,'easeInOutElastic');

        $('#div4').animate({
            'width':'400px'
        },3000,'easeInBounce');
    </script>
</body>
</html>
```










