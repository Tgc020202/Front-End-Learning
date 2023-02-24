## JavaScript & DOM

#### DOM(Document Object Model) 文档对象模型
+ 它就是 HTML 的标签
+ 简单说明: JS 可以控制 HTML 的标签

+ JavaScript 的方法: onload
> onload 整个页面加载完过后

+ JS 与 CSS 与 html 之间的配合例子
> 1. JS -> 选取 html 的元素
> 2. JS -> 改动 css 样式
> + 如果要在 ```<head>``` 标签里头写 JS 代码，一定要使用 onload 函数
> + 不然的话，还是安安稳稳的在 ```<body>``` 标签里面写 JS 代码吧
> + 但是切记要放 <script> 标签

Example (1_rectangle.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>正方形因时间变长方形</title>

    <!-- CSS -->
    <style type="text/css">
        #myDiv{
            width: 100px;height: 100px;
            background-color: black;
        }
    </style>

    <!-- JavaScript -->
    <script>
        window.onload = function(){
            setTimeout(function(){
                document.getElementById('myDiv').style.width='200px';
            },2000);

        }
    </script>

</head>
<body>
    <div id="myDiv"></div>
</body>
```
> 原本黑色的正方形，两秒后变成长方形


###### JS 条件
+ if-else

Example:
```
<script>
    /*
    if(条件成功== true){
        执行内容
    }
    else{
        如果没成功，执行的内容
    }
    */
    
    if(5 > 1){
        console.log('yes');
    }
    else{
        console.log('no');
    }
    // true
</script>
```


###### 事件
+ 事件是交互的一种，比如键盘或者鼠标
+ 交互事件 
> 鼠标点击: onclick
> JS 其实跟中文一样 . 代表'的'，函数就是要做的事

Example (2_color.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>换颜色的教程</title>

    <!-- CSS -->
    <style type="text/css">
        #myDiv{
            width: 100px;height: 100px;
            background-color: black;
        }
    </style>

    <!-- JavaScript -->
    <script>
        window.onload = function(){
            var myDiv = document.getElementById('myDiv');
            myDiv.onclick = function(){
                myDiv.style.backgroundColor='red';
            };

        }
    </script>

</head>
<body>
    <div id="myDiv"></div>
</body>
```
> 一开始是黑色的正方形，一旦点击正方形，正方形就会变成红色


+ 添加按钮元素
> <button> 标签

Example (3_disappear.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>方形消失术</title>

    <!-- CSS -->
    <style type="text/css">
        #myDiv{
            width: 100px;height: 100px;
            background-color: black;
        }
    </style>

    <!-- JavaScript -->
    <script>
        window.onload = function(){
            var btn = document.getElementById('btn'),
            myDiv = document.getElementById('myDiv');

            btn.onclick = function(){
                myDiv.style.display = "none";
            }

        }
    </script>

</head>
<body>
    <div id="myDiv"></div>
    <button id="btn">按钮</button>
</body>
```
> 当一点击按钮，黑色正方形就会直接消失

+ 可以使用计算数值的方式，添加一些操作

Example (4_count.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>添加计算方式</title>

    <!-- CSS -->
    <style type="text/css">
        #myDiv{
            width: 100px;height: 100px;
            background-color: black;
        }
    </style>

    <!-- JavaScript -->
    <script>
        window.onload = function(){
            var btn = document.getElementById('btn'),
            myDiv = document.getElementById('myDiv'),
            num = 0;

            btn.onclick = function(){
                num = num + 1;
                console.log(num);

                // num 是单数就消失
                if(num %  2 == 1){
                    myDiv.style.display = 'none';
                }
                // num 是双数就出现
                else{
                    myDiv.style.display = 'block';
                }
            }

        }
    </script>

</head>
<body>
    <div id="myDiv"></div>
    <button id="btn">按钮</button>
</body>
```
> 使用条件语句，使正方形可以消失，又可以出现

#### JS 选取的方式
##### 1. id
+ document.getElementById('id');

Example:
```
<body>
    <div id='myDiv1'>1</div>

    <!-- JavaScript -->
    <script>
        var myDiv = document.getElementById('myDiv1');
        myDiv.style.color = 'red';
    </script>
</body>
```
##### 2. tagName
+ 标签名是复数，要记得放下标
+ document.getElementsByTagName('tagname');

Example (5_tagnames.html):
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByTagName('div');
        aDiv[0].style.color = 'red';
        aDiv[1].style.color = 'blue';
        aDiv[2].style.color = '#ccc'
    </script>
</body>
```

##### 3. class 类
+ 使用类名
+ document.getElementsByClassName('className');

Example (6_class.html):
```
<body>
    <div class="a1">1</div>
    <div class="a1">2</div>
    <div class="a1">3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByClassName('a1');
        aDiv[0].style.color='pink';
        aDiv[1].style.color='green';
    </script>
</body>
```

###### cssText 
+ 可以像 css 的样式写在 JS

Example (7_css_in_js.html):
```
<body>
    <div class="a1">1</div>
    <div class="a1">2</div>
    <div class="a1">3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByClassName('a1');
        aDiv[0].style.cssText = 'width:300px;height:200px;color:red;background:black'
    </script>
</body>
```

###### innerHTML 
+ 可以用来改变 html 里面的内容

Example (7_css_in_js.html):
```
<body>
    <div class="a1">1</div>
    <div class="a1">2</div>
    <div class="a1">3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByClassName('a1');
        aDiv[0].style.cssText = 'width:300px;height:200px;color:red;background:black'
        
        aDiv[1].innerHTML = '大呆呆';
        
        setTimeout(function(){
            aDiv[2].innerHTML = 'small small is big 呆呆';
        },5000);
    </script>
</body>
```

###### className 类名
+ 可以返回元素标签上的 class 的内容

Example:
```
<body>
    <div class="a1">1</div>
    <div class="a1">2</div>
    <div class="a1">3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByClassName('a1');
        
        console.log(aDiv[0].className);
    </script>
</body>
```
> output 会显示 className: a1

+ 可以使用 className 改变 class 的名字
> 变量.className = '另一个类名';

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>className</title>
    <style>
        .a2{
            width: 200px;height: 200px;background-color: red;color: green;
        }
    </style>
</head>
<body>
    <div class="a1">1</div>
    <div class="a1">2</div>
    <div class="a1">3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByClassName('a1');
        
        aDiv[0].className = 'a2';
    </script>
</body>
```

+ 一个变量可以同时拥有很多个 className
> + 但是变量会优先选择离自己最近的 className
> + 变量.className = 'className1 className2';

Example (8_search_class.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>className</title>
    <style>
        .a2{
            width: 200px;height: 200px;background-color: red;color: green;
        }
        .a1{
            width: 200px;height: 200px;background-color: yellow;color: green;
        }
        .a3{
            width: 200px;height: 200px;background-color: green;color: green;
        }
    </style>
</head>
<body>
    <div class="a1">1</div>
    <div class="a1">2</div>
    <div class="a1">3</div>

    <!-- JavaScript -->
    <script>
        var aDiv = document.getElementsByClassName('a1');
        
        aDiv[0].className = 'a1 a3';
    </script>
</body>
```
> aDiv[0] 会优先持有 a1 的属性值，因为 a1 离它最近

###### onmouse
+ 鼠标移动就会触发
1. onmouseover 鼠标移入
2. onmouseout 鼠标移出

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>On mouse</title>
    <style>
        *{margin: 0;padding: 0;}

        #myDiv{
            width: 100px;height: 100px;background-color: black;color: white;
        }
    </style>
</head>
<body>
    <div id="myDiv">1</div>

    <!-- JavaScript -->
    <script>
        var myDiv = document.getElementById('myDiv');
        myDiv.onmouseover = function(){
            myDiv.style.background = 'blue';
            myDiv.innerHTML = '鼠标移入';
        };
        myDiv.onmouseout = function(){
            myDiv.style.background = 'black';
            myDiv.innerHTML = '鼠标移出';
        }
    </script>
</body>
```
> 当鼠标在方形里就会变蓝色，相反的就会变黑色


###### window.onresize
+ 浏览器大小发生了改变，就会触发

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>on resize</title>
</head>
<body>
    <script>
        window.onresize = function(){
            console.log('懒惰虫移动了');
        }
    </script>
</body>
</html>
```
> 当浏览器的大小发生了改变，console 就会打印 '懒惰虫移动了' 
