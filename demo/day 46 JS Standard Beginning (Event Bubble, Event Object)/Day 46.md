## JavaScript - Standard Beginning

#### 事件 e
+ e = MouseEvent(鼠标事件)
+ 参数传进来的 e，IE 不兼容
+ 参数传进来的 event，Firefox 不兼容
+ Google 两方都接受
+ 所以平时都会使用 `var ev = e || event`; 避免 error

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>e = 鼠标事件</title>
    <style>
        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="div1"></div>
    <!-- JavaScript -->
    <script>
        div1.onclick = function(e){
            var ev = e || event;
            console.log(ev);
        }
    </script>
</body>
</html>
```

+ 鼠标事件的属性
![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2046%20JS%20Standard%20Beginning%20(Event%20Bubble%2C%20Event%20Object)/Images/p1.PNG)

#### 事件冒泡
+ 父级的事件会被子级继承下去

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件冒泡</title>

    <style>
        #big{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
        #small{
            width: 100px;
            height: 100px;
            background-color: green;
            position: absolute;
            left: 50%;
            top: 50%;
        }
    </style>
</head>
<body>
    <div id="big">
        <div id="small"></div>
    </div>
    <!-- JavaScript -->
    <script>
        // 父级的事件子级也会继承
        big.onclick = function(){
            alert('haha');
        }
    </script>
</body>
</html>
```
> + 当我点击绿色方形(子级)也会触发弹窗，虽然那是父级的事件


###### 取消冒泡: 方法一 (cancelBubble)
+ 写法:

```
子级.onclick = function(e){
  var ev = e || event;
  ev.cancelBubble = true;
}
```

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>取消事件冒泡</title>

    <style>
        #big{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
        #small{
            width: 100px;
            height: 100px;
            background-color: green;
            position: absolute;
            left: 50%;
            top: 50%;
        }
    </style>
</head>
<body>
    <div id="big">
        <div id="small"></div>
    </div>
    <!-- JavaScript -->
    <script>
        // 父级的事件子级也会继承
        big.onclick = function(){
            alert('haha');
        }

        // 取消事件冒泡
        small.onclick = function(e){
            var ev = e || event;
            ev.cancelBubble = true;
        }
    </script>
</body>
</html>
```


###### 取消冒泡: 方法二 (stopPropagation())
+ 它属于高级浏览器的一种
+ 过低等级的浏览器会报错
+ 写法:

```
子级.onclick = function(e){
  var ev = e || event;
  ev.stopPropagation();
}
```

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>取消事件冒泡方法二</title>

    <style>
        #big{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
        #small{
            width: 100px;
            height: 100px;
            background-color: green;
            position: absolute;
            left: 50%;
            top: 50%;
        }
    </style>
</head>
<body>
    <div id="big">
        <div id="small"></div>
    </div>
    <!-- JavaScript -->
    <script>
        // 父级的事件子级也会继承
        big.onclick = function(){
            alert('haha');
        }

        // 取消事件冒泡
        small.onclick = function(e){
            var ev = e || event;
            ev.stopPropagation();
        }
    </script>
</body>
</html>
```


