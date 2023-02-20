# css - float 的应用
+ 可以把元素变为左横排或右横排

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Float 的用法</title>
    <style type="text/css">
        /*设置属性*/
        div {
            width: 200px;height: 200px;background-color: blue;
        }

        /*float:right 倾向左边*/
        .same_row_left {
            float:left;
        }
        
        /*float:right 倾向右边*/
        .same_row_right {
            float:right;
        }
        
    </style>
</head>
<body>
    <!-- default 的话是直排的 -->
    <div>
        <p>哈哈哈 我是default蓝色</p>
    </div>
    <div style="width: 200px;height: 200px;background-color: yellow;">我是default黄色</div>

    <!-- 使用 float:right 就是靠右横排 -->
    <div class="same_row_right">
        <p>哈哈哈 我是right蓝色</p>
    </div>
    <div class="same_row_right" style="width: 200px;height: 200px;background-color: yellow;">我是right黄色</div>

    <div style="background-color: white;">
        我是空格
    </div>
    <!-- 使用 float:left 就是靠左横排 -->
    <div class="same_row_left">
        <p>哈哈哈 我是left蓝色</p>
    </div>
    <div class="same_row_left" style="width: 200px;height: 200px;background-color: yellow;">我是left黄色</div>

</body>
</html>
```

#### css - margin (外边距)
+ day 06 有说过一些
+ 当前元素距离外面的边距
+ 有四个方向 (top,right,bottom,left)
+ 调用方法: margin-left/margin-right/margin-top/margin-bottom

Example：
```
/*四个值缩写法*/
margin:top,right,bottom,left;

/*
三个值缩写法
条件是左右的数值要一样
*/
margin:top,leftright,bottom;

/*
二个值缩写法
条件是左右的数值要一样，同时上下的数值要一样
*/
margin:topbottom,leftright;

/*
一个值缩写法
条件是全部的数值都要一样
*/
margin:topleftrightbottom;

/*左*/
margin-left:数值;

/*右*/
margin-right:数值;

/*上*/
margin-top:数值;

/*下*/
margin-bottom:数值;
```

#### css padding 内边距
+ 就是从元素内的边距进行调整

Example:
```
/*四个值缩写法*/
padding:top,right,bottom,left;

/*
三个值缩写法
条件是左右的数值要一样
*/
padding:top,leftright,bottom;

/*
二个值缩写法
条件是左右的数值要一样，同时上下的数值要一样
*/
padding:topbottom,leftright;

/*
一个值缩写法
条件是全部的数值都要一样
*/
padding:topleftrightbottom;

/*左*/
padding-left:数值;

/*右*/
padding-right:数值;

/*上*/
padding-top:数值;

/*下*/
padding-bottom:数值;
```

+ 可以利用 margin.html 和 padding.html 进行比较
+ margin 和 padding 的差别是 
+ margin 原来的元素的大小不变，而 padding 的元素会改变
### 可以使用这个指令将其他的空间清空: 
```
html,body{padding: 0;margin: 0;}
```
