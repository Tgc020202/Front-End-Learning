## JavaScript - 事件(Event)对象深入

#### addEventListener 添加事件监听
+ addEventListener('放入事件名称<不用加 on>',function,true/false);
+ 第一个参数比如: onclick = click，onmoueover = mouseover
+ 通常不用第三个参数，因为会有兼容问题
+ 做到事件叠加，不会覆盖之前的事件

Example:
```
<body>
    <input type="button" name="" value="add" id="ipt">

    <!-- JavaScript -->
    <script>
        /*
        // 如果重新赋于新事件的话，之前的事件会被覆盖
        ipt.onclick = function(){
            alert(1);
        }

        ipt.onclick = function(){
            alert(2);
        }
        // 弹出 2
        */


        /*
        // 不会被覆盖
        ipt.addEventListener('click',function(){
            alert(3);
        });
        ipt.addEventListener('click',function(){
            alert(4);
        });
        // 3 和 4 都有弹出
        */

        // 鼠标移到 input 标签，就会触发
        ipt.addEventListener('mouseover',function(){
            alert(4);
        });

    </script>
</body>
```


#### removeEventListener 解除事件监听
+ removeEventListener('放入事件名称<不用加 on>',函数名);
+ 精准解除

Example(普通解除事件):
```
<body>
    <input type="button" name="" value="add" id="ipt">

    <!-- JavaScript -->
    <script>

        ipt.onclick = function(){
            alert(1);
        }
        // 如果是 onclick 事件的话，可以通过重新赋值的方式解除
        // ipt.onclick = null;
        // ipt.onclick = function(){}
    </script>
</body>
```

Example(精准解除事件):
```
<body>
    <input type="button" name="" value="add" id="ipt">

    <!-- JavaScript -->
    <script>
        // 创建函数
        function a (){
            alert(1);
        }

        function b (){
            alert(2);
        }

        ipt.addEventListener('click',a);
        ipt.addEventListener('click',b);

        // 移出事件 - 精准解除
        ipt.removeEventListener('click',a); // 把 a 函数移出
    </script>
</body>
```


#### 键盘事件 Keyboard Event

###### onkeyup  
+ 点击按键的时候触发

###### onkeydown
+ 放开按键的时候触发

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>onkeyup and onkeydown 的配合</title>
    <style>
        *{padding: 0;margin: 0;}
        #div1{
            width: 200px;height: 200px;
            background-color: red;
            position: absolute;
            left: 0;top: 0;
        }
    </style>
</head>
<body>
    <div id="div1"></div>
    <!-- JavaScript -->
    <script>

        // 做一个装置，一点击 d 键，方形就会往右移动
        // 一放开 d 键，方形就会停止不动
        // d -> 68  a -> 65

        var l = 0, timer = null;

        // 点击
        document.onkeydown = function(){
            // console.log(event);
            if(event.key == 'd'){
                clearInterval(timer);
                timer = setInterval(function(){
                    l += 3;
                    div1.style.left = l + 'px';
                },30);
            }
        }

        // 放开
        document.onkeyup = function(){
            clearInterval(timer);
        }


    </script>
</body>
```


#### 事件委托/代理 srcElement || target
+ 就是给予父级元素事件
+ 父级元素可以找到子级元素的事件源
+ 通过判断事件源的 classname, nodename, id
+ 找到需要的事件源，并给予 javascript 脚本

+ 好处:
> + 可以控制未来(动态生成)的元素

+ 缺点：
> + 会有兼容问题
> > + ie - target -> undefined
> > + 旧版火狐 - srcElement -> undefined
> > + 新版火狐 - 两个都行
> > + 谷歌 -> 两个都行

+ 解决方法
> + event.target || event.srcElement

Example:
```
<script>
    // IE 只认 srcElement
    // 谷歌认 target 和 srcElement
    // 火狐认 target 和 srcElement(旧版本只认 srcElement)
    document.documentElement.onclick = function(){
        // console.log(event.srcElement);
        var iTarget = event.target || event.srcElement;
        console.log(iTarget);
    }
</script>
```


###### target & srcElement 的操作
+ 测试如果在未来(动态生成)元素也就是说还没完全生成的元素，是否可以调用
+ 假设我未来会生成一个 div 标签，但是我建立一个函数的触发条件是点击这个 div 才可以触发
+ 是否可以触发？

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托或者代理</title>
    <style>
        *{padding: 0;margin: 0;}
        
        #div1{
            width: 200px;height: 200px;background-color: black;
        }
    </style>
</head>
<body>
    <!-- JavaScript -->
    <script>
        /*
        // 先调用 div 标签，再创建 div 标签 -> 出 error
        div.onclick = function(){
            alert(1)
        }

        var oDiv = document.createElement('div');
        oDiv.id = 'div1';
        document.body.appendChild(oDiv);
        */

        // 解决方法
        document.documentElement.onclick = function(){
            // alert(1);
            // console.log(event.target)
            // console.log(event.target.nodeName)

            if(event.target.id == 'div1'){
                alert(1);
            }
        }    
        var oDiv = document.createElement('div');
        oDiv.id = 'div1';
        document.body.appendChild(oDiv);
    </script>
</body>
```

+ 可以查询类名 classname

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托或者代理</title>
    <style>
        .div2{
            width: 200px;height: 200px;background-color: black;
            float: left;margin: 10px;
        }
    </style>
</head>
<body>
    <!-- JavaScript -->
    <script>
        // 当点击 div 就会返回红色
        document.documentElement.onclick = function(){
            if(event.target.className == 'div2'){
                event.target.style.background = 'red';
            }
        }

        for(var i = 0; i < 10; i ++){
            var oDiv = document.createElement('div');
            oDiv.className = 'div2';
            document.body.appendChild(oDiv);
        }
    </script>
</body>
```

+ 证明可以区分类名
+ 当要给予属性的时候，需要使用 event.target 为元素

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托或者代理</title>
    <style>
        *{padding: 0;margin: 0;}
        .div2{
            width: 200px;height: 200px;background-color: black;
            float: left;margin: 10px;
        }

        .div3{
            width: 250px;height: 250px;background-color: black;
            float: left;margin: 10px;
        }
    </style>
</head>
<body>
    <!-- JavaScript -->
    <script>
        // 当点击小的 div 就会返回红色，大的 div 就会返回绿色
        document.documentElement.onclick = function(){
            if(event.target.className == 'div2'){
                event.target.style.background = 'red';
            }
            else{
                event.target.style.background = 'green';
            }
        }

        for(var i = 0; i < 10; i ++){
            var oDiv = document.createElement('div');
            if(i < 5){
                oDiv.className = 'div2';
            }
            else{
                oDiv.className = 'div3';
            }
            document.body.appendChild(oDiv);
        }

    </script>
</body>
```


#### offsetLeft/Top
+ 返回当前元素距离父级元素的偏移的像素值
+ offsetLeft -> 左边距离
+ offsetTop -> 上面距离

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Offset</title>
    <style>
        *{padding: 0;margin: 0;}

        #div1{
            width: 200px;height: 200px;
            background-color: red;position: absolute;
            left: 150px;top: 200px;
        }

        #div2{
            width: 200px;height: 200px;
            background-color: yellow;position: absolute;
            left: 150px;top: 200px;
            margin: 50px;
        }

        #div3{
            width: 200px;height: 200px;
            background-color: blue;position: absolute;
            left: 150px;top: 200px;
            transform: translate(50px,100px);
        }

        #div4{
            width: 100px;height: 100px;
            background-color: green;position: absolute;
            left: 25px;top: 50px;
            margin: 100px;
        }
    </style>
</head>
<body>
    <!-- <div id="div1"></div> -->
    <!-- <div id="div2"></div> -->
    <!-- <div id="div3"></div> -->

    <div id="div2">
        <div id="div4"></div>
    </div>

    <!-- JavaScript -->
    <script>
        // console.log(div1.offsetLeft);   // 150
        // console.log(div1.offsetTop);    // 200

        // offset = left/top + margin
        // console.log(div2.offsetLeft);   // 200
        // console.log(div2.offsetTop);    // 250

        // 平移(translate) 不会影响 offset 的值，但是显示的位置会移动
        // console.log(div3.offsetLeft);   // 150
        // console.log(div3.offsetTop);    // 200

        // 子类
        // 以父类为基础(0,0)重新计算
        // offsetLeft = width + margin
        // offsetTop = height + margin
        console.log(div4.offsetLeft);   // 125
        console.log(div4.offsetTop);    // 150

    </script>
</body>
```
> + div1 是以 body 为父类，并计算距离
> > + offsetLeft = left
> > + offsetTop = top
> + div2 也是以 body 为父类，并计算距离
> > + offsetLeft = left + margin
> > + offsetTop = top + margin
> + div3 也是以 body 为父类，并计算距离
> > + 平移(translate) 不会影响 offset 的值，但是显示的位置会移动
> > + offsetLeft = left + margin
> > + offsetTop = top + margin
> + div4 是以 div2 为父类，并计算距离
> > + offsetLeft = left + margin
> > + offsetTop = top + margin


#### offsetWidth/Height 宽度/高度
+ 返回元素的宽高
+ offsetWidth
+ offsetHeight

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Offset</title>
    <style>
        *{padding: 0;margin: 0;}

        #div1{
            width: 100px;height: 100px;
            background-color: #ccc;
        }

        #div2{
            width: 100px;height: 100px;
            background-color: #ccc;
            padding: 50px 50px;
        }

        #div3{
            width: 100px;height: 100px;
            background-color: #ccc;
            padding: 50px 50px;
            margin: 50px 50px;
        }

        #div4{
            width: 100px;height: 100px;
            background-color: #ccc;
            padding: 50px 50px;
            margin: 50px 50px;
            border: 25px solid black;
        }

        #div5{
            width: 100px;height: 100px;
            background-color: #ccc;
            padding: 50px 50px;
            margin: 50px 50px;
            border: 25px solid black;
        }

        #div6{
            width: 500px;height: 500px;
            background-color: #ccc;
            padding: 50px 50px;
            margin: 50px 50px;
            border: 25px solid black;
        }
    </style>
</head>
<body>
    <!-- <div id="div1"></div> -->
    <!-- <div id="div2"></div> -->
    <!-- <div id="div3"></div> -->
    <!-- <div id="div4"></div> -->
    <!-- <div id="div5">11111111111111111111111111111111111111111111111111111111111111111111111</div> -->
    <div id="div5">
        <div id="div6"></div>
    </div>
    
    <!-- JavaScript -->
    <script>
        // offset = width/height
        // console.log(div1.offsetWidth);  // 100
        // console.log(div1.offsetHeight); // 100

        // 加 padding
        // 会乘 2，因为宽度左边和右边，高度上面和下面
        // // offset = width/height + padding * 2
        // console.log(div2.offsetWidth);  // 200
        // console.log(div2.offsetHeight); // 200

        // 加 margin
        // offset = width/height + padding * 2
        // console.log(div3.offsetWidth);  // 200
        // console.log(div3.offsetHeight); // 200

        // 加 border
        // 会乘 2，因为宽度左边和右边，高度上面和下面
        // offset = width/height + padding * 2 + border * 2
        // console.log(div4.offsetWidth);  // 250
        // console.log(div4.offsetHeight); // 250

        // 文字
        // 文字的长度不会影响
        // offset = width/height + padding * 2 + border * 2
        // console.log(div5.offsetWidth);  // 250
        // console.log(div5.offsetHeight); // 250

        // 超大型子类
        // 不会影响
        // offset = width/height + padding * 2 + border * 2
        console.log(div5.offsetWidth);  // 250
        console.log(div5.offsetHeight); // 250
    </script>
</body>
```
> + div1 普通的 div
> > + offsetWidth/Height = width/height
> + div2 是加上 padding 内边框
> > + 加上 padding 会有影响
> > + 所以 offsetWidth/Height 会乘 2，因为宽度左边和右边，高度上面和下面
> > + offsetWidth/Height = width/height + padding * 2
> + div3 是加上 margin 外边框
> > + 加上 margin 不会影响
> > + offsetWidth/Height = width/height + padding * 2
> + div4 是加上 border 边框
> > + 加上 border 会有影响
> > + 所以 offsetWidth/Height 会乘 2，因为宽度左边和右边，高度上面和下面
> > + offsetWidth/Height = width/height + padding * 2 + border * 2
> + div5 加上很长的文字
> > + 不会影响
> > + offsetWidth/Height = width/height + padding * 2 + border * 2
> + div6 是子类，div5 是 div6 的父类
> > + div5 不会受影响
> > + offsetWidth/Height = width/height + padding * 2 + border * 2

+ 总结:
> + 会受影响: padding, border

#### 元素的拖拽和原理

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>拖拽</title>
    <style>
        *{
            padding: 0;margin: 0;list-style: none;
        }

        #div1{
            width: 100px;height: 100px;
            background-color: red;
            position: absolute;
            left: 0;top: 0;
        }
    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        // 拖拽的封装

        // 点击鼠标，启动函数
        div1.onmousedown = function(){
            /*
                event.clientX -> 鼠标的 X 坐标
                div1.offsetLeft -> div1 与浏览器左边的距离
                event.clientY -> 鼠标的 Y 坐标
                div1.offsetTop -> div1 与浏览器上面的距离
            */
            // 指定鼠标在 div1 上面的位置
            var l = event.clientX - div1.offsetLeft;    // 指定 div1 的 X 轴，鼠标至 div1 的左边的距离
            var t = event.clientY - div1.offsetTop;     // 指定 div1 的 Y 轴，鼠标至 div1 的上面的距离

            // 鼠标移动
            document.onmousemove = function(){
                // 指定鼠标移动时，div1 以刚刚指定鼠标在 div1 上面的位置为准，跟随鼠标移动的
                var needX = event.clientX - l;  // div1 往左靠 l 值
                var needY = event.clientY - t;  // div1 往上靠 t 值
                
                // 避免 div1 出浏览器
                if(needX < 0) needX = 0;
                if(needX > innerWidth - div1.offsetWidth) needX = innerWidth - div1.offsetWidth;
                if(needY < 0) needY = 0;
                if(needY > innerHeight - div1.offsetHeight) needY = innerHeight - div1.offsetHeight;
                
                div1.style.left = needX + 'px';
                div1.style.top = needY + 'px';
            }
            
            // 鼠标放开时
            document.onmouseup = function(){
                document.onmousemove = null;
                document.onmouseup = null;
            }
            
            return false;   // 避免鼠标自动选中文字 
        }
    </script>
</body>
</html>
```


#### 事件的委托与拖拽

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件的委托 - 拖拽</title>
    <style>
        *{padding: 0;margin: 0;}

        .drag{
            width: 100px;height: 100px;
            background-color: red;
            position: absolute;
            left: 0;
            top: 0;
        }
    </style>
</head>
<body>
    <div class="drag"></div>
    <div class="drag"></div>
    <div class="drag"></div>
    <div class="drag"></div>
    <div class="drag"></div>
    
    <!-- JavaScript -->
    <script>

        document.documentElement.onmousedown = function(e){
            var ev = e || event;
            var iTarget = event.target || event.srcElement;

            if(iTarget.className == 'drag'){
                iTarget.style.background = 'green';
                var l = ev.clientX - iTarget.offsetLeft;
                var t = ev.clientY - iTarget.offsetTop;
            
                document.onmousemove = function(e){
                    var ev = e|| event;
                    var needX = ev.clientX - l;
                    var needY = ev.clientY - t;

                    if(needX < 0) needX = 0;
                    if(needX > innerWidth - iTarget.offsetWidth) needX = innerWidth - iTarget.offsetWidth;
                    if(needY < 0) needY = 0;
                    if(needY > innerHeight - iTarget.offsetHeight) needY = innerHeight - iTarget.offsetHeight;

                    iTarget.style.left = needX + 'px';
                    iTarget.style.top = needY + 'px';
                }

                document.onmouseup = function(e){
                    this.onmousemove =
                    this.onmouseup = null;
                }
                return false;
            }
        }
    </script>
</body>
</html>
```










