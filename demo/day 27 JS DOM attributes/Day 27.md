## JavaScript - DOM 的属性

#### setAttribute   设置属性
+ dom 元素
> + 一些普通常见的属性是可以直接获取或者设置的
> + 比如: id class type href src

Example:
```
<body>
    <div  id="div1" class="div2" tgc="div3"></div>

    <!-- JavaScript -->
    <script>
        // 检测 id 和 classname 属性
        console.log(div1.id,div1.className);

        // 检测自定义属性
        console.log(div1.tgc);  // 不可行
    </script>
</body>
```
> + 自定义的属性如果有值，不可以直接添加进 div 标签里


+ 自定义的属性
> + 必须使用 attribute
> + 写法: setAttribute('属性','属性值');
> + 不要属性值的写法: setAttribute('属性','');

Example:
```
<body>
    <div  id="div1" class="div2" tgc="div3"></div>

    <!-- JavaScript -->
    <script>
        // 自定义元素
        div1.setAttribute('wxx',10);    // 有给予数值
        console.log(div1);

        // 不赋予数值 - 错误
        div1.setAttribute('wxx');   // 会出 bug
        console.log(div1);

        // 不赋予数值 - 正确
        div1.setAttribute('wxx','');   // 可以放置 '' 符号
        console.log(div1);
    </script>
</body>
```


#### getAttribute 获取元素上的属性
+ DOM 的基本属性和自定义属性都可以使用
+ getAttribute('属性');

Example:
```
<body>
    <a href="" id="myA">连接</a>
    <!-- JavaScript -->
    <script>
        // 基本属性的获取
        myA.href = 'https://www.youtube.com/';
        console.log(myA.href);

        // 自定义属性的获取
        myA.setAttribute('tgc',10);
        console.log(myA.tgc);   // 会获取不到(undefined)

        // getAttribute 可获取自定义属性和基本属性
        console.log(myA.getAttribute('tgc'));
        console.log(myA.getAttribute('href'));

    </script>
</body>
```


#### removeAttribute 删除元素上的属性
+ DOM 的基本属性和自定义属性都可以使用
+ removeAttribute('属性');

Example:
```
<body>
    <a href="" id="myA">连接</a>
    <a href="https://www.youtube.com/" id="myB">连接</a>
    <div id="div1" tgc></div>

    <!-- JavaScript -->
    <script>
        // 把自己的 id 删了
        myB.removeAttribute('id');
        
        // 把自定义的属性删了
        div1.removeAttribute('tgc');


    </script>
</body>
```


#### hasAttribute 判断包元素可见属性
+ DOM 的基本属性和自定义属性都可以使用
+ 判断元素有没有该属性
+ hasAttribute('属性');
+ 返回值是:true(属性存在的话) false(属性不存在的话)

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>hasAttribute 判断有无属性</title>
    <style>
        #div1{
            width: 100px;height: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="div1" class="div2" tgc="10"></div>
    <a href="https://www.youtube.com/" id="myA">链接</a>
    <!-- JavaScript -->
    <script>
        // 检测是否有基本属性
        console.log(div1.hasAttribute('class'));

        // 检测是否有自定义属性(有)
        console.log(div1.hasAttribute('tgc'));

        // 检测是否有自定义属性(无)
        console.log(div1.hasAttribute('wxx'));

        
        // 一点击 div 就会判断有没有 tgc 属性
        // 如果没有就会创建一个 tgc = 18
        // 如果有就修改 tgc = 20
        div1.onclick = function(){
            if(div1.hasAttribute('tgc')){
                div1.setAttribute('tgc',20);
            }
            else{
                div1.setAttribute('tgc',18);
            }
            console.log(div1);
        }
    
    </script>
</body>
```


#### classname & classlist

###### classname 类名
+ className 可以返回或者设置元素的 class

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ClassName 和 ClassList</title>
    <style>

        #div1{
            width: 100px;height: 100px;
            background-color: red;
        }
        .div2{
            width: 100px;height: 100px;
            background-color: red;
        }
        #div1.div3{
            background-color: yellow;
        }
    </style>
</head>
<body>

    <!-- <div id="div1" class="div2" tgc="10"></div> -->
    <div id="div1" class='' tgc="10"></div>

    <!-- JavaScript -->
    <script>
        // 调用 classname
        console.log(div1.className);

        // 点击 div 的话，div3 的特性(变黄色)会被触发
        div1.onclick = function(){
            // div1.className = 'div2 div3';

            // 当不知道里面 div1 里面的classname是什么
            div1.className += ' div3'; 
            console.log(div1);  // 会在classname 里面添加' div3'
        }
    </script>
</body>
```
> + 点击 div 的话，div1 的 classname 就会等于 div3，div3 的特性(变黄色)会被触发

Example(弊端):
```
<body>

    <!-- <div id="div1" class="div2" tgc="10"></div> -->
    <div id="div1" class='' tgc="10"></div>

    <!-- JavaScript -->
    <script>
        // 如果 div1 没有classname 
        // classname 会添加' div3'，因为 div3 前面有个空格
        // 这是一个弊端
        div1.onclick = function(){
            // 当不知道里面 div1 里面的classname是什么
            div1.className += ' div3'; 
            console.log(div1);
        }
    </script>
</body>
```
> + div1 的 classname 显示有一个空格在前面

Example:
```
<body>

    <!-- <div id="div1" class="div2" tgc="10"></div> -->
    <div id="div1" class='' tgc="10"></div>

    <!-- JavaScript -->
    <script>
        // 解决方案
        div1.onclick = function(){
            if(div1.className == ''){
                div1.className = 'div3';
            }
            else{
                div1.className += ' div3';
            }
            console.log(div1);
        }
    </script>
</body>
```
> + 添加条件语句这样就没有空格了


##### classList
###### classList.add
+ 添加一个类

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ClassList</title>
    <style>
        .box1{
            width: 200px;height: 200px;
            background-color: black;
            transition: .3s;
        }
        .box2{
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="div1" class="box1"></div>

    <!-- JavaScript -->
    <script>

        // 添加类
        div1.onclick = function(){
            div1.classList.add('box2');
        }
    </script>
</body>
```

###### classList.remove
+ 删除一个类

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ClassList</title>
    <style>
        .box1{
            width: 200px;height: 200px;
            background-color: black;
            transition: .3s;
        }
        .box2{
            background-color: red;
        }
    </style>
</head>
<body>
    <!-- div 里的 classname : box1 box2 -->
    <div id="div1" class="box1 box2"></div>

    <!-- JavaScript -->
    <script>

        // 删除类
        div1.onclick = function(){
            div1.classList.remove('box2');
        }
    </script>
</body>
```

###### classList.contain
+ 判断有没有该类
+ 如果有返回 true
+ 如果没有返回 false

Example:
```
<body>
    <!-- div 里的 classname : box1 box2 -->
    <div id="div1" class="box1 box2"></div>

    <!-- JavaScript -->
    <script>
        // 放一个(true)
        console.log(div1.classList.contains('box1'));
        
        // 放两个(false)
        console.log(div1.classList.contains('box1 box2'));  // 无法同时放两个

        // 放虚假的(false)
        console.log(div1.classList.contains('box3'));
    </script>
</body>
```

###### classList.toggle
+ 可以切换类
+ 有该类就删除
+ 没有该类就添加

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ClassList</title>
    <style>
        .box1{
            width: 200px;height: 200px;
            background-color: black;
            transition: .3s;
        }
        .box2{
            background-color: red;
        }
        .box3{
            box-shadow: 0 0 10px black;
        }
    </style>
</head>
<body>
    <!-- div 里的 classname : box1 box2 box3-->
    <div id="div1" class="box1 box2 box3"></div>

    <!-- JavaScript -->
    <script>
        /*
        // 条件语句创建 toggle
        div1.onclick = function(){
            if(div1.classList.contains('box3')){
                div1.classList.remove('box3');
            }
            else{
                div1.classList.add('box3');
            }
        }
        */

        // 使用 classList.toggle
        div1.onclick = function(){
            div1.classList.toggle('box3');
        }
        
    </script>
</body>
```
