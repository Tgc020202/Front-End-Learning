## JavaScript - Standard Beginning

#### Attributes 属性

###### 属性的种类
+ 有两种:
> 1. 隐式属性 
> > + JS 直接赋予，但是在页面看不到
> > + 只有特殊的显示属性，才能用隐式属性的方法去拿
> > + 例子: id, class
> 2. 显式属性
> > + 需要通过 setAttribute/getAttribute 来运行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>显式属性和隐式属性</title>
</head>
<body>
    <div id="div1"></div>
    <div id="div2"></div>

    <!-- JavaScript -->
    <script>

        // 隐式属性
        div1.tgc = 'haha';

        // 显式属性
        div2.setAttribute('tgc','haha');
    </script>
    
</body>
</html>
```

+ ![p3](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2045%20JS%20Standard%20Beginning%20(Attributes%2C%20Bag%20And%20Life%20Cycle)/Images/p3.PNG)


###### 设置属性
+ 元素名.setAttribute('属性名','属性值');

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>给予属性</title>
</head>
<body>
    <div id="div1"></div>

    <div id="div2"></div>


    <!-- JavaScript -->
    <script>
        // div2.setAttribute('tgc','heyoo');
    </script>
</body>
</html>
```

之前
> ![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2045%20JS%20Standard%20Beginning%20(Attributes%2C%20Bag%20And%20Life%20Cycle)/Images/p1.PNG)

之后
> ![p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2045%20JS%20Standard%20Beginning%20(Attributes%2C%20Bag%20And%20Life%20Cycle)/Images/p2.PNG)



###### 提取属性值
+ getAttribute('属性名');
+ 返回属性值

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>取出属性</title>
</head>
<body>
    <div id="div1" panda="cute"></div>

    <div id="div2"></div>


    <!-- JavaScript -->
    <script>
        div2.setAttribute('tgc','heyoo');


        // getAttribute
        alert(div1.panda);  // undefined
        alert(div1.getAttribute("panda"));  // cute
        alert(div2.getAttribute("tgc"));  // heyoo

        alert(div2.getAttribute('id')); // div2
    </script>
</body>
</html>
```

###### 判断属性名是否存在
+ hasAttribute('属性名');
+ 会返回 true/false

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>判断属性名是否存在</title>
</head>
<body>
    <div id="div1" panda="cute"></div>

    <!-- JavaScript -->
    <script>
        div1.setAttribute('tgc','heyoo');

        alert(div1.hasAttribute('panda'));  // true
        alert(div1.hasAttribute('small'));  // false

        if(div1.hasAttribute('tgc')){
            alert('yes');   // yes
        }

    </script>
</body>
</html>
```


###### 返回节点名称
+ 节点.nodeName;

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>节点名称</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        alert(document.body.nodeName);  // BODY
        alert(document.body.nodeName.toLowerCase());  // body
    </script>
</body>
</html>
```

#### 生命周期
+ 当有使用的时候就还活着(可以使用)
+ 一旦没有使用了就死了(不能使用)

Example:
`<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>生命周期</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        /*
        // a 在作用域外，无法使用里面的 a
        onload = function(){
            var a = 10;
            alert(a);   // 10
        }
        alert(a);   // 没有显示东西
        */


        /*
        // 使用 setTimeout 延长 a 存活的时间
        var a = 10;
        function show(){
            alert(a);
        }

        setTimeout(function(){
            show();
        },500000000);
        */

        /*
        // window 可以让变量变为永远存在
        window.c = 100;

        setTimeout(function test(){
            alert(c);   // 100
        }, 100);
        */

        // 就算在不同的作用域也可以调用
        function infinity(){
            window.d = 100;
        }
        function run(){
            alert(d);
        }
        run();
    </script>
</body>
</html>``

```


#### 闭包
+ 子函数访问父函数的变量
+ 所以子函数能延长父函数的生命周期
+ 子函数也可以扩充父函数的空间

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>闭包</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        // 子函数可以使用父函数的变量
        function show(){
            var a = 10;
            function show2(){
                alert(a);
            }
            show2();
        }
        show(); // 10
    </script>
</body>
</html>
```


