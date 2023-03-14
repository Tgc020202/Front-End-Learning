## JavaScript - Standard Beginning

#### Repetition
###### for each
+ 可用于调用数组里的内容
+ 数组.forEach(function(e){内容});

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Repetition - for each</title>
</head>
<body>
    <input type="text" name="" id="">
    <input type="text" name="" id="">
    <input type="text" name="" id="">


    <!-- JavaScript -->
    <script>
        /*
        [1,2,3].forEach(function(e){
            alert(e);
        });
        */
        
        // 证明: 变量使用 getElementByTagname 得到的 input 数据，不是一个数组
        /*
        var ipt = document.getElementsByTagName('input');

        ipt.forEach(function(e){
            alert(e);
        });                         // TypeError 发生
        


        var ipt = document.getElementsByTagName('input');
        var arr = [ipt[0],ipt[1],ipt[2]];
        arr.forEach(function(e){
            alert(e);
        });                         // 返回对象名称
        */
    </script>
</body>
</html>
```
> + ipt 不是数组，所以不能直接调用
> + 需要创建变量，使其变为数组，才可以使用 for each

###### for in
+ for(var i in 数组){内容}

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Repetition - for in</title>
</head>
<body>
    <input type="text" name="" id="">
    <input type="text" name="" id="">
    <input type="text" name="" id="">

    <!-- JavaScript -->
    <script>
        var ipt = document.getElementsByTagName('input');
        var arr = [ipt[0],ipt[1],ipt[2]];

        /*
        for(var i in ipt){  
            alert(i);
        }                   // 返回: 0,1,2,length,item,namedItem

        for(var i in arr){  
            alert(i);
        }                   // 返回: 0,1,2
        */

        for(var i in ipt){
            if(i == 'length' || i == 'item' || i == 'namedItem'){
                continue;
            }
            else{
                alert(i);
            }
        }                   // 返回: 0,1,2
    </script>
</body>
</html>
```
> + 由于 ipt 不是数组，所以一旦直接调用就会出现，length，item，namedItem

###### break
+ 所有的循环都可以使用，但是一旦跳出循环就会立即结束

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Break - 终止循环</title>
</head>
<body>
    <input><input><input>

    <!-- JavaScript -->
    <script>
        for(var i = 0;i < 5;i ++){
            if(i == 2)break;
            alert(i);
        }
        // 只打印 0, 1而已
    </script>
</body>
</html>
```

###### continue
+ 跳过当前回合，但是循环还是可以持续进行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Continue - 跳过</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        for(var i = 0;i < 5; i ++){
            if(i == 2)continue;
            alert(i);
        }
        // 除了 2，其他的数字都打印出来了
    </script>
</body>
</html>
```


#### DOM
###### document.getElementById
+ 通过 id 取得元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>通过 id 取得元素</title>
</head>
<body>
    <div id="small">你好</div>

    <!-- JavaScript -->
    <script>
        var a = document.getElementById('small');
        alert(a);

        document.getElementById('small').innerHTML = '大呆呆';
    </script>
</body>
</html>
```

###### document.getElementByTagName
+ 通过元素名取得元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>通过元素名取得元素</title>
</head>
<body>
    <div></div>
    <p></p>
    <div></div>
    <!-- JavaScript -->
    <script>
        var a = document.getElementsByTagName('div');
        for(var i = 0; i < a.length ;i++){
            a[i].style.background ='green';
            a[i].style.height ='100px';
            a[i].style.width ='100px';
        }
    </script>
</body>
</html>
```

###### document.getElementByClassName
+ 通过类名取得元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>通过类名取得元素</title>
    <style>
        div{
            width: 50px;
            height: 50px;
            background-color: yellow;
        }
    </style>
</head>
<body>
    <div class="small"></div>
    <div class="big"></div>
    <div class="small"></div>
    <!-- JavaScript -->
    <script>
        var a = document.getElementsByClassName('small');
        for(var i = 0; i < a.length ;i++){
            a[i].style.background ='green';
            a[i].style.height ='100px';
            a[i].style.width ='100px';
        }

        document.getElementsByClassName('small')[1].innerHTML = '大呆瓜';
    </script>
</body>
</html>
```

###### document.getElementsByName
+ 通过属性名字取得元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>通过名字取得元素</title>
</head>
<body>
    <div name="small">大呆瓜一号</div>
    <div name="small">大呆瓜二号</div>

    <!-- JavaScript -->
    <script>
        var a = document.getElementsByName('small');
        alert(a[0].innerHTML);

        document.getElementsByName('small')[1].innerHTML = '你好聪明';
    </script>
</body>
</html>
```

###### innerHTML 
+ 返回 DOM 的内容
+ 放 = 符号相当于赋予内容
+ 也可以直接使用 id 来调用 innerHTML

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM - InnerHTML</title>
</head>
<body>
    <div id="div1"></div>
    <!-- JavaScript -->
    <script>
        document.getElementById('div1').innerHTML = '<div></div>';    // 赋予内容
        alert(document.getElementById('div1').innerHTML);     // 返回内容

        div1.innerHTML = '呆呆';
    </script>
</body>
</html>
```

###### outerHTML
+ 返回 DOM 的内容和自己的内容
+ 放 = 符号相当于把自己给替换了

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dom - outerHTML</title>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaScript -->
    <script>
        document.getElementById('div1').outerHTML = '<div id="haha"></div>';    // 赋予内容
        alert(document.getElementById('div1').outerHTML);     // 返回空，因为 div1 被替换成 haha
    </script>
</body>
</html>
```

###### 在 JS 里转换成 CSS 语句
+ style.cssText
+ 可以以给 DOM 元素，让 CSS 的形式去赋值

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>cssText 的使用</title>
</head>
<body>
    <div></div>
    <!-- JavaScript -->
    <script>
        var a = document.getElementsByTagName('div');
        a[0].style.cssText = 'width:100px;height:100px;background:black;';
    </script>
</body>
</html>
```

###### children
+ 获取 DOM 元素的子级

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Children 子类</title>
</head>
<body>
    <div id="a">
        <div id="b">
            <div id="b1"></div>
            <p id="b2"></p>
            <div id="b3"></div>
        </div>
        <div id="c"></div>
    </div>

    <!-- JavaScript -->
    <script>
        alert(a.children[0].id);    // b
        alert(a.children[1].id);    // c

        alert(a.children[0].children[2].id);    // b3
    </script>
</body>
</html>
```

###### parentNode
+ 获取 DOM 元素的父级

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>parentNode 父级</title>
</head>
<body>
    <div id="a">
        <div id="b">
            <div id="c"></div>
        </div>
    </div>

    <!-- JavaScript -->
    <script>
        alert(c.parentNode.id);    // b
        alert(c.parentNode.parentNode.id);    // a
    </script>
</body>
</html>
```

#### 小技巧
+ id 元素可以直接拿 id 作为变量使用

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>id 元素的小技巧</title>
</head>
<body>
    <div id="div1"></div>
    <!-- JavaScript -->
    <script>
        // 直接使用 id 元素执行调用
        div1.innerHTML = '你好大呆呆';
    </script>
</body>
</html>
```








