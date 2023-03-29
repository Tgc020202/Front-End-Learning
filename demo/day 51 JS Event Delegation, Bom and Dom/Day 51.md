## JavaScript - 事件委托 Event Delegation
+ 父级把事件给予子级了
+ 事件并不是绑定在元素上面

#### srcElement
+ 不兼容于所有的浏览器
+ IE 浏览器不支持
+ 谷歌和火狐都支持

#### target
+ 不兼容于所有的浏览器
+ 火狐浏览器不支持
+ 谷歌和 IE 浏览器都支持

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }

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
        document.onclick = function(e){
            var ev = e || event;
            // var iTarget = ev.srcElement;
            // var iTarget = ev.target;
            var iTarget = ev.srcElement || ev.target;

            if(iTarget.id == 'div1'){
                alert(1);
            }
        }
    </script>
</body>
</html>
```
> + 可在不同的浏览器 (IE, 火狐, 谷歌) 进行操作，并且观察

###### 解决兼容问题
+ var iTarget = ev.srcElement || ev.target;
+ 使在任何浏览器都不用担心兼容问题

###### 证明 - 事件不是绑定在元素上

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托 - Bom</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
        }

        #div2{
            width: 100px;
            height: 100px;
            background-color: black;
        }
    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        document.onclick = function(e){
            var ev = e || event;
            var iTarget = ev.srcElement || ev.target;

            if(iTarget.id == 'div1'){
                iTarget.id = 'div2';
            }
        }
    </script>
</body>
</html>
```
> + 当点击了红色方块 (div1) 后，div 的 id 变成 div2 了，当前的 div 元素就不会再有之前的功能了



### JavaScript - Bom & Dom
#### Bom
+ 实例化之前 this 就只向实例化的对象
+ 没实例化之前 this 永远就只向 window

Example:
```
<script>
  function a(){
    alert(this);    //   没实例化 : object window, 实例化 : object object
  };
  a();    // 没实例化
  new a();    // 实例化

</script>
```

#### Dom
+ 永远指向发送的事件源

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件委托 - Dom</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }

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
        document.onclick = function(e){
            var ev = e || event;
            var iTarget = ev.srcElement || ev.target;

            function a(){
                alert(this);    // 没有实例化 : object window
            }
            a();

            if(iTarget.id == 'div1'){
                alert(this);    // 事件源 : object HTMLDocument
            }
        }
    </script>
</body>
</html>
```
