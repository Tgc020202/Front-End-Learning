## JavaScript - 运动框架

#### offsetWidth/Height
+ 宽度/高度
+ 计算包含与不包含
> + width   ✔
> + margin  ❌
> + padding ✔
> + border  ✔

#### clientWidth/Height
+ 宽度/高度
+ 计算包含与不包含
> + width   ✔
> + margin  ❌
> + padding ✔
> + border  ❌

#### getComputedStyle 取元素的属性值
+ 不兼容于所有浏览器
+ 比如，IE 就不支持
+ 写法: getComputedStyle(元素 id,false)['要提取的属性名']

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>运动框架 - 变宽</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
            position: absolute;
            top: 0;
            left: 0;
        }
    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaSript -->
    <script>

        console.log(div1.style.width);    // undefined

        // 获取宽度
        console.log(getComputedStyle(div1,false)['width']);   // 100px

    </script>
    
</body>
</html>
```


#### currentStyle 取元素的属性值
+ 不兼容于所有浏览器
+ 比如，google 就不支持
+ 写法: 元素 id.currentStyle['属性名']

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>运动框架 - 变宽</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
            position: absolute;
            top: 0;
            left: 0;
        }
    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaSript -->
    <script>
        // 获取宽度
        console.log(div1.currentStyle['width']);   // 100px

    </script>
    
</body>
</html>
```

##### 取元素的属性值解决方法
+ 使用封装
+ 混合 getComputedStyle 和 currentStyle

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>运动框架 - 解决方法(封装)</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            list-style: none;
        }

        #div1{
            width: 100px;
            height: 100px;
            background-color: red;
            position: absolute;
            top: 0;
            left: 0;
        }
    </style>
</head>
<body>
    <div id="div1"></div>

    <!-- JavaSript -->
    <script>
        // 使用封装
        function getStyle(obj,name){
            if(obj.currentStyle){
                return obj.currentStyle[name];
            }
            else if(getComputedStyle(obj)){
                return getComputedStyle(obj,false)[name];
            }
        }

        console.log(getStyle(div1,'width'));

    </script>
    
</body>
</html>
```






