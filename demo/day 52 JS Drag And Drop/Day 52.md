## JavaScript - 拖拽 Drag and Drop
+ 改变(Position)属性的 left 和 top
+ 用到了的事件: onmousedown(鼠标点击), onmousemove(鼠标持续点击并移动), onmouseup(鼠标松开)
+ 用到了事件的属性: clientX, clientY
+ 用到了 offsetTop, offsetLeft
+ ![计算距离的图解](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2052%20JS%20Drag%20And%20Drop/Images/p1.png)
+ 用到了元素的属性: offsetHeight/offsetWidth
+ 用到了屏幕(Window)的属性: innerHeight/innerWidth
+ ![计算极限距离](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2052%20JS%20Drag%20And%20Drop/Images/p2.png)

Example(基本的拖拽):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽</title>
    <style>
        *{margin: 0; padding: 0; list-style-type: none;}

        #div1{
            width: 100px;
            height: 100px;
            position: absolute;
            left: 0;
            top: 0;
            background-color: black;
        }
    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 将 onmousemove 和 onmousemove 事件放入 onmousedown 事件里
        div1.onmousedown = function(e){
            // 避免兼容问题
            var ev = e || event;
            
            // 计算元素内的鼠标与元素的左边框和上边框的距离
            var t = ev.clientY - div1.offsetTop;  // 上边框至鼠标
            var l = ev.clientX - div1.offsetLeft; // 左边框至鼠标

            document.onmousemove = function(e){
                var ev = e || event;

                // 鼠标位置
                var distanceTop = ev.clientY - l;
                var distanceLeft = ev.clientX - t;

                // 设置限制最右边和最下边
                var maxTop = innerHeight - div1.offsetHeight;
                var maxLeft = innerWidth - div1.offsetWidth;

                // 点击 div 元素，div 元素会开始跟着鼠标
                // 设置元素的范围
                distanceTop = distanceTop < 0 ? 0 : distanceTop;
                distanceTop = distanceTop > maxTop ? maxTop : distanceTop;
                distanceLeft = distanceLeft < 0 ? 0 : distanceLeft;
                distanceLeft = distanceLeft > maxLeft ? maxLeft : distanceLeft;

                // 设置鼠标位置
                div1.style.top = distanceTop + 'px';
                div1.style.left = distanceLeft + 'px';
            }
            
            document.onmouseup = function(e){
                // 将 onmousemove 和 onmouseup 事件清空
                document.onmousemove = null;
                document.onmouseup = null;
            }
        }

    </script>
</body>
</html>
```

#### 事件委托与拖拽 - 封装
+ 普通的事件给予方法，只要给予节点事件，那么这个节点就算更换了绑定时的名字，它的事件依旧存在.

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: green;
        }


    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 依旧可以弹出 1，虽然 id 依然显示 div2
        div1.onclick = function(){
            alert(1)
        }
        div1.id = 'div2';
    </script>
</body>
</html>
```
> + div 的 id 从 div1 变为 div2，但是 div1 给予的事件依旧可以触发

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: green;
        }


    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 依旧可以弹出 1，虽然 id 依然显示 div2
        // div1.onclick = function(){
        //     alert(1)
        // }
        // div1.id = 'div2';

        // 这个1就不行了
        div1.onclick = function(){
            div1.id = 'div2';
        }
    </script>
</body>
</html>
```
> + 通过触发事件更改 div 的 id，会使 div1 给予的事件被清空

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: green;
        }


    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 依旧可以弹出 1，虽然 id 依然显示 div2
        // div1.onclick = function(){
        //     alert(1)
        // }
        // div1.id = 'div2';

        // 这个1就不行了
        // div1.onclick = function(){
        //     div1.id = 'div2';
        // }

        // 会报错，因为 div2 还未被定义
        div2.onclick = function(){
            alert(1)
        }
        div1.id = 'div2';
    </script>
</body>
</html>
```
> + 因为 onclick 事件是在定义 div1 的元素的 id 为 div2 之前
> + 因此导致了当 onclikc 事件触发了，却找不到 div2 的情况

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: green;
        }


    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 依旧可以弹出 1，虽然 id 依然显示 div2
        // div1.onclick = function(){
        //     alert(1)
        // }
        // div1.id = 'div2';

        // 这个1就不行了
        // div1.onclick = function(){
        //     div1.id = 'div2';
        // }

        // 会报错，因为 div2 还未被定义
        // div2.onclick = function(){
        //     alert(1)
        // }
        // div1.id = 'div2';

        // 这样就可以触发了
        div1.id = 'div2';
        div2.onclick = function(){
            alert(1)
        }
    </script>
</body>
</html>
```
> + 先定义 div2 就可以触发事件了

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: green;
        }


    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 依旧可以弹出 1，虽然 id 依然显示 div2
        // div1.onclick = function(){
        //     alert(1)
        // }
        // div1.id = 'div2';

        // 这个1就不行了
        // div1.onclick = function(){
        //     div1.id = 'div2';
        // }

        // 会报错，因为 div2 还未被定义
        // div2.onclick = function(){
        //     alert(1)
        // }
        // div1.id = 'div2';

        // 这样就可以触发了
        // div1.id = 'div2';
        // div2.onclick = function(){
        //     alert(1)
        // }

        // 给予没有声明的变量的时间，就会报错
        div3.onclick = function(){
            alert(1)
        }
        div1.id = 'div3';
    </script>
</body>
</html>
```
> + 如果给予没有声明的变量的事件，就会报错

+ 事件委托 - target || srcElement

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: green;
        }


    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        window.onclick = function(e){
            var ev = e || event;
            var oSrc = ev.target || ev.srcElement;

            console.log(oSrc);  //   显示所有子级内容

            // 查找到 window 里的子级的 id 为 div1 的
            if(oSrc.id == 'div1'){
                alert(1);
            }
        }
    </script>
</body>
</html>
```

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽与事件委托 - 封装</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style-type: none;
        }
        
        div,span{
            width: 100px;
            height: 100px;
            float: left;
            background-color: red;
            margin: 50px;
        }


    </style>
</head>
<body>
    <div></div>
    <span></span>
    <span></span>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>

    <!-- JavaScript -->
    <script>
        // 点击到 span 元素，就会变绿
        window.onclick = function(e){
            var ev = e || event;
            var oSrc = ev.target || ev.srcElement;

            console.log(oSrc);  //   显示所有子级内容

            // nodeName - 元素标签的名称
            if(oSrc.nodeName == 'SPAN'){
                oSrc.style.background = 'green';
            }
        }
    </script>
</body>
</html>
```
> + 当点击到 span 元素，就会变绿色
> + nameNode 用于获取元素标签的名称


#### 事件委托和拖拽 - 回放效果

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托与拖拽 - 回放效果</title>
    <style>
        *{
            margin: 0;padding: 0;list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            position: absolute;
            background-color: #ccc;
        }

        #bto{
            width: 100px;
            height: 50px;
            float: right;
        }
    </style>
</head>
<body>
    <div id="div1"></div>
    <input type="button" name="" value="回放" id="bto">

    <!-- JavaScript -->
    <script>

        var arrX = [] , arrY = [];

        div1.onmousedown = function(e){
            var ev = e || event;
            var oSrc = ev.target || ev.srcElement;
            var l = ev.clientX - this.offsetLeft;
            var t = ev.clientY - this.offsetTop;

            arrX.push(0);
            arrY.push(0);

            document.onmousemove = function(e){
                var ev = e || event;
                var oSrc = ev.target || ev.srcElement;
                var distanceTop = ev.clientY - l;
                var distanceLeft = ev.clientX - t;


                arrX.push(distanceLeft);
                arrY.push(distanceTop);
                console.log('X:' + distanceLeft + '\nY:' + distanceTop);


                div1.style.left = distanceLeft + 'px';
                div1.style.top = distanceTop + 'px';
            }

            document.onmouseup = function(){
                document.onmousemove = document.onmouseup = null;
            }
            return false;
        }



        var timer = null;

        bto.onclick = function(){
            clearInterval(timer);

            timer = setInterval(function(){
                if(arrX.length == 0 && arrY.length == 0){
                    clearInterval(timer);
                }

                div1.style.left = arrX.pop() + 'px';
                div1.style.top = arrY.pop() + 'px';
            },50);
        }
    </script>
</body>
</html>
```

