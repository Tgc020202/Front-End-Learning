## JavaScript - Standard Beginning

#### DOM - Insert
###### DOM 生成元素的方法
1. 创造元素
> + 写法: createElement('标签名')
2. 从后方开始添加元素
> + 写法: 父节点.appendChild(创建的子节点)
> + 插入到父级的最下面

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AppendChild</title>
</head>
<body>
    <div id="bigDiv">

    </div>
    <!-- JavaScript -->
    <script>
        var a = document.getElementById('bigDiv');
        var b = document.createElement('div');

        b.id = 'smallDiv';
        b.style.cssText = 'width:200px;height:200px;background:green;margin:10px;';

        a.appendChild(b);
        
        // 这个新的子节点会插入到父级的最下面
        var c = document.createElement('div');

        c.id = 'smallDiv2';
        c.style.cssText = 'width:200px;height:200px;background:black;margin:10px;';

        a.appendChild(c);
    </script>
</body>
</html>
```

3.自定义添加元素
> + 添加到父级的下面的子元素的前面
> + 写法: 父节点.insertBefore(创建的子节点,要设置的位置)
> + 要设置的位置可以使用下标来进行定位

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
</head>
<body>
    <div>123</div>
    <div>321</div>
    <!-- JavaScript -->
    <script>
        var a = document.createElement('div');
        a.innerHTML = 'halo';
        document.body.insertBefore(a,document.body.children[1]);
    </script>
</body>
</html>
```
> + halo 成功插入 123 和 321 之间

4. 创建文本节点
+ document.createTextNode('文本');
Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>创建节点文本</title>
</head>
<body>
    <div id="box">
        你好
    </div>
    <textarea name="" id="content" cols="30" rows="10" placeholder="发布你的心情"></textarea>
    <input type="button" name="" value="发送" id="btn">

    <!-- JavaScript -->
    <script>
        var a = document.createTextNode('小呆呆');
        box.appendChild(a);
    </script>
</body>
</html>
```


#### DOM - Remove
###### 删除子元素
+ 父节点.removeChild(要删除的节点)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>删除元素</title>

    <style>
        #box{
            width: 200px;
            height: 400px;
            border: 1px solid black;
        }

        #content{
            width: 400px;
            height: 400px;
            border: 1px solid black;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div id="box">
        <span id="message">haha</span>
    </div>
    <textarea name="" id="content" cols="30" rows="10" placeholder="发布你的心情"></textarea>
    <input type="button" name="" value="发送" id="btn">

    <!-- JavaScript -->
    <script>
        // document.body.removeChild(message); // 无法删除，因为 span 是 body 的子级的子级

        // 可以通过 span 的父级将其删了
        // box.removeChild(message);

        // 可以通过使用 parentNode 将其删了
        message.parentNode.removeChild(message);
        
        document.body.removeChild(content);
        document.body.removeChild(btn);
    </script>
</body>
</html>
```


#### DOM - Replace
###### 替换元素节点
+ 写法: 父节点.replaceChild(新的，旧的)
+ 也可以使用 outerHTML 来替换元素节点

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>替换</title>
</head>
<body>
    <div id="box">
        <span id="message">haha</span>
    </div>
    <textarea name="" id="content" cols="30" rows="10" placeholder="发布你的心情"></textarea>
    <input type="button" name="" value="发送" id="btn">

    <!-- JavaScript -->
    <script>
        var a = document.createElement('div');
        // box.outerHTML = '<div id="information"></div>';
        
        a.id = 'data';
        document.body.replaceChild(a,box);
    </script>
</body>
</html>
```



#### DOM - Event
+ 事件绑定的特性一旦绑定了就一直会有这个事件了

###### 点击
+ 使用点击触发事件
+ onclick = function(){}

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>鼠标点击</title>
    <style>
        #clickme{
            width: 100px;
            height: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="clickme"></div>

    <!-- JavaScript -->
    <script>
        // 只触发一次
        clickme.onclick = function(){
            alert(1);
        }

        clickme.onclick = function(){
            alert(1);
        }
    </script>
</body>
</html>
```


###### 事件监听
1. 添加事件监听
+ addEventListener('触发方式',function(){},false);

2. 解除事件监听
+ removeEventListener('触发方式',函数名)
+ 必须要有函数名，才可以使用这个命令

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件监听</title>
    <style>
        #clickme{
            width: 100px;
            height: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="clickme"></div>

    <!-- JavaScript -->
    <script>
        /* addEventListener */
        /*
        // 会触发两次
        clickme.addEventListener('click',function(){
            alert(1);
        },false);

        clickme.addEventListener('click',function(){
            alert(1);
        },false);


        addEventListener('load',function(){
            alert('大呆呆');
        },false);

        addEventListener('load',function(){
            alert('小呆呆');
        },false);
        */

        /* removeEventListener */
        function a(){
            alert(1);
            removeEventListener('click',a);
        }

        addEventListener('click',a,false);
    </script>
</body>
</html>
```






