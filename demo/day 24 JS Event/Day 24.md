## JS Event 事件对象
+ 和当前事件有关系的对象

Example:
```
<script>
        onclick = function(){
            alert(1);
        }
</script>
```
> + 当点击任意地区都可以打印 1 的弹窗
> + onclick = function() 相等于 window.onclick = function()

###### 鼠标事件 mouse event 
+ onmousemove
> + 鼠标在内容上滑动时触发的事件

Example:
```
<script>
        onmousemove = function(){
            console.log('1');
        }
</script>
```

+ onmousedown
> + 鼠标按下的时候触发的事件

+ onmouseup
> + 鼠标抬起的时候触发的事件

Example:
```
<script>
        onmousedown = function(){
            console.log('鼠标按下');
        }
        onmouseup = function(){
            console.log('鼠标抬起');
        }
</script>
```

+ oncontextmenu
> + 右键的事件

Example:
```
<script>
        oncontextmenu = function(){
            alert('1');
        }
</script>
```

#### Events 的用法
+ 事件对象可以找到和这个事件有关系的内容

Example(放 event):
```
<script>
        onmousedown = function(event){
            console.log(event);
        }
</script>
```
> + 显示触发的按键的相关信息

###### client-x, client-y
+ x 轴，y 轴

Example:
```
<script>
        var oS = document.getElementById('mySpan');
        onmousemove = function(event){
            oS.innerHTML = event.clientX+','+event.clientY;
        }
</script>
```
> + 可以知道鼠标的坐标

###### 取消默认事件
+ 取消默认事件

Example(onmousedown):
```
<body>

    <div id="myDiv">12345567763453634535</div>

    <!-- JavaScript -->
    <script>
     var myDiv = document.getElementById('myDiv');

        myDiv.onmousedown = function(){
            return false;
        }
    </script>
</body>
```
> + 使我们在网页上无法选取那串数组

Example(oncontextmenu):
```
<body>

    <div id="myDiv">12345567763453634535</div>

    <!-- JavaScript -->
    <script>
     var myDiv = document.getElementById('myDiv');

        myDiv.oncontextmenu = function(){
            return false;
        }
    </script>
</body>
```
> + 使我们在网页上的那串数组上，点击右键时没有效果/功能

+ 也可以与其他的标签搭配

Example(input):
```
<body>
    <input id="ipt" type="password">

    <!-- JavaScript -->
    <script>
     var ipt = document.getElementById('ipt');

        ipt.onmousedown = function(){
            return false;
        }
    </script>
</body>
```
> + 点击没有效果

###### 键盘事件 keyboard event
+ onkeydown
> + 点击按键时触发事件

+ onkeyup
> + 放开按键时触发事件

Example:
```
<script>
        onkeydown = function(){
            console.log('1');
        }
</script>
```

Example(放 event):
```
<script>
        onkeydown = function(event){
            console.log(event);
        }
</script>
```
> + 显示触发的按键的相关信息

Example(1_keyboard_event.html):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KeyBoard Event</title>
    <style type="text/css">
        body,html{height: 100%;}

        #myDiv{
            width: 100px;height: 100px;
            background: red;
            position: absolute;
            left: 300px;
            top: 300px;
        }
    </style>
</head>
<body>
<div id="myDiv"></div>

    <!-- JavaScript -->
    <script>
        var l = 300,t = 300,
        myDiv = document.getElementById("myDiv");

        onkeydown = function(event){
            if(event.key == 'a'){
                l = l - 10;
            }
            if(event.key == 'w'){
                t = t - 10;
            }
            if(event.key == 's'){
                t = t + 10;
            }
            if(event.key == 'd'){
                l = l + 10;
            }
            myDiv.style.left = l + 'px';
            myDiv. style.top = t + 'px';
        }
    </script>
</body>
```
> + wsad 控制上下左右的移动




Example(2_keyboard_evnet.html):
```
<script>

        var ipt = document.getElementById("ipt");

        ipt.onkeydown = function(event){
            // ASCII code a:65,z=90
            if(event.keyCode >= 65 && event.keyCode <= 90){
                return false;
            }
        }
    </script>
```


#### 阻止事件冒泡
+ 用来避免子类用到父类的函数
+ cancelBubble

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>阻止事件冒泡</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}

        #div1{
            width: 100px;height: 100px;
            background-color: red;
            position: absolute;
        }
        #div2{
            width: 100px;height: 100px;
            background-color: black;
            position: absolute;
            left: 300px; top: 300px;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div id="div2"></div>
    </div>

    <!-- JavaScript -->
    <script>
        var div1 = document.getElementById('div1'),
        div2 = document.getElementById('div2');

        div1.onclick = function(){
            alert(1);
        }

        // 添加 cancelBubble
        div2.onclick = function(event){
            event.cancelBubble = true;
        }

    </script>
</body>
```

#### for 循环
+ 写法:

```
for(初始化条件;判断条件;迭代语句){
  脚本
}
```




