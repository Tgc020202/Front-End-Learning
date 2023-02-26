## JavaScript 的逻辑判断语句

### 1.0 for 循环
+ for(var i = 0;i<allDiv.length;i++){}

##### 1.0.1 continue
+ 跳过当前循环，但是接下去的循环照常进行

Example:
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>

    <!-- JavaScript -->
    <script>
        var allDiv = document.getElementsByTagName('div');

        for(var i = 0;i<allDiv.length;i++){
            if(i == 2){
                continue;   // 跳过当前循环
            }
            allDiv[i].style.background = 'red';
        }

    </script>

</body>
```
> + continue - 跳过当前循环
> + 条件语句(if-else) - 可以在 for 循环里面使用


##### 1.0.2 mod
+ 符号: %
+ 通常用来做检测偶数与奇数的条件语句
> + if(i % 2 == 0){}  // 偶数 even
> + if(i % 2 != 0){}  // 奇数 odd

Example:
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>10</div>

    <!-- JavaScript -->
    <script>
        var allDiv = document.getElementsByTagName('div');

        for(var i = 0;i<allDiv.length;i++){
            // 使偶数的 i 的颜色保持不变
            if(i % 2 == 0){
                continue;   // 跳过当前循环
            }
            allDiv[i].style.background = 'red';
        }

    </script>

</body>
```

##### 1.0.3 break
+ 可以设立一些条件，并中断循环，且强制使其循环结束/中断运行
+ 不会影响到之前运行过的代码的结果
+ 只会阻止代码原本过后要运行的行动，使其没有运行成功
+ 比如，要从 a 去到 e，但是设立在 c 的时候中断了，所以系统只运行到 a，b 和 c，但是c 过后的也就是 d 和 e 并不会实行

Example:
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>10</div>

    <!-- JavaScript -->
    <script>
        var allDiv = document.getElementsByTagName('div');

        for(var i = 0;i<allDiv.length;i++){
            // 当 i 相等于 2 的时候，循环中断
            if(i == 2){
                break;
            }
            allDiv[i].style.background = 'red';
        }

    </script>

</body>
```


### 1.1 while 循环
+ while(条件){脚本}

Example：
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>While 循环</title>
    <style>
        *{padding: 0;margin: 0;}

        div{
            width: 200px; height: 200px;
            background-color: red;
            float: left;    margin: 20px;
        }
    </style>
</head>
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>

    <!-- JavaScript -->
    <script>
        var i = 0,
        allDiv = document.getElementsByTagName('div');

        document.onclick = a;

        function a (){
            while(i < 3){
                if(i == 2){
                    break;
                }
                else{
                    console.log(i);
                    allDiv[i].style.background = 'yellow';
                }
                i++;
            }
        }
    </script>
</body>
```
> + 一点击鼠标 while 循环 就会被启动
> + 一旦 i 等于 2， while 循环就会被中断
> + 所以只有两个 div 标签会被改变颜色


### 1.3 do-while 循环
+ do{脚本}while(条件);
+ 至少会执行一次

Example:
```
    <script>
        // do-while
        var i = 0;
        do{
            console.log('do-while 循环: ' + i)
            i ++;
        }while(i < 0);

        // while
        var j = 0;
        while(j < 0){
            console.log('while 循环: ' + j)
            j ++;
        }
    </script>
```

### 1.4 switch
+ 用法:

```
switch(变量){
    case 变量的值:
    脚本
    break;
    case 变量的值:
    脚本
    break;
    case 变量的值:
    脚本
    break;
    case 变量的值:
    脚本
    break;
    default:
    脚本
    break;
}
```

Example:
```
<script>
    /*
    var i = 10;

    switch(i){
        case 0:
            alert(1);
            break;
        
        case 1:
            alert(2);
            break;
        
        case 2:
            alert(2);
            break;
        
        default:
            alert('呆呆');
            break;
    }
</script>
```

Example(不加 break):
```
<script>
    /*
    var i = 10;

    switch(i){
        case 0:
            alert(1);
        
        case 1:
            alert(2);
        
        case 2:
            alert(2);
        
        default:
            alert('呆呆');
    }
</script>
```
> + 不加 break，就会穿透到有 break 的停止



### 逻辑判断 - AND 和
+ 符号: &&
+ 条件1 && 条件2  -> 需要双方都是正确的才能判断为正确

Example:
```
    <script>
        var i = 0,j = 1;

        if(i == 0 && j == 1){
            alert('True');
        }
    </script>
```

Example(if-else 与 && 的搭配):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>And && 符号</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}

        div{
            width: 200px;height: 200px;
            background-color: black;
            float: left;
            margin: 30px;
        }

        #btn{
            width: 100px;height: 50px;
            margin: 30px;
        }
    </style>
</head>
<body>
    <div id="div1">1</div>
    <div id="div2">2</div>

    <button id="btn">判断按钮</button>
    <!-- JavaScript -->
    <script>
        var div1 = document.getElementById('div1'),
        div2 = document.getElementById('div2'),
        btn = document.getElementById('btn');

        btn.onclick = a;
        div1.onclick = b;
        div2.onclick = b;

        function a(){
            if(div1.style.background == 'red' && div2.style.background == 'red'){
                alert('他们都是红色');
            }
            else{
                alert('至少有一个不是红色');
            }
        }

        function b(){
            this.style.background = 'red';
        }
    </script>
</body>
```
> + 一开始会出现两个四方形
> + 点击判断按钮 就会判断两个四方形是不是红色的
> + 点击四方形可以改变四方形的颜色
> + 一定要两个方形都是红色，才会显示正确


### 逻辑判断 - 或
+ 符号: || 
+ 条件1 || 条件2  -> 至少需要一个是正确的就能判断为正确

Example:
```
    <script>
        var i = 0,j = 0;

        if(i == 0 || j == 1){
            alert('True');
        }
    </script>
```

Example(if-else 与 || 的搭配):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Or || 符号</title>
    <style type="text/css">
        *{padding: 0;margin: 0;}

        div{
            width: 200px;height: 200px;
            background-color: black;
            float: left;
            margin: 30px;
        }

        #btn{
            width: 100px;height: 50px;
            margin: 30px;
        }
    </style>
</head>
<body>
    <div id="div1">1</div>
    <div id="div2">2</div>

    <button id="btn">判断按钮</button>
    <!-- JavaScript -->
    <script>
        /*
        var i = 0,j = 0;

        if(i == 0 || j == 1){
            alert('True');
        }
        */

        var div1 = document.getElementById('div1'),
        div2 = document.getElementById('div2'),
        btn = document.getElementById('btn');

        btn.onclick = a;
        div1.onclick = b;
        div2.onclick = b;

        function a(){
            if(div1.style.background == 'red' || div2.style.background == 'red'){
                alert('至少有一个是红色');
            }
            else{
                alert('他们都不是红色');
            }
        }

        function b(){
            this.style.background = 'red';
        }
    </script>
</body>
```
> + 一开始会出现两个四方形
> + 点击判断按钮 就会判断两个四方形是不是红色的
> + 点击四方形可以改变四方形的颜色
> + 只要其中一个方形是红色，就会显示正确


#### 逻辑判断 - 和与或的原理
+ 和 && 多个判断条件是否符合，如果全都符合，就是正确
> + 只要条件不满足 就不往后看了
> + 但是条件满足 就会一直往后看 直到全部条件都满足

+ 或 || 只要满足其中一个条件，就是正确
> + 只要满足一个条件 就不往后看了
> + 条件不满足就会一直往后看 直到全部都不满足为止

Example:
```
<script>
    var i = 0,j = 0,k = 0;
    
    if(i == 0 || j == 1 || k == 2){
        alert(true);
    }
    else{
        alert(false);
    }
</script>
```


