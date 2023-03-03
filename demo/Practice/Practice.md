## Practice

#### Practice 1 - 风筝效果
+ 根据父级不断地缩小大小，并且放置在父级的右下角

Answer:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>风筝效果</title>
    <style>
        *{padding:0;margin: 0;}

        .myDiv{
            width: 200px;height: 200px;
            background-color: red;
            position: absolute;
        }

        .myDiv .childDiv{
            width: 50%;height: 50%;
            background-color: red;
            position: inherit;
            top: 100%;
            left: 100%;
        }
    </style>
</head>
<body>
    <div class="myDiv">
        <div class="childDiv">
            <div class="childDiv">
                <div class="childDiv">
                    <div class="childDiv">
                        <div class="childDiv"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```
> + myDiv 是父级，它的定位是绝对定位，所以 childDiv 子级是 inherit(跟随父级的定位)
> + 子级的宽设置 50% 说明当子级的宽是父级的一半，高度也是一样的意思
> + top 设置成 100% 说明子级与上面的距离(这里所谓的距离是指父级的上边框至我们创建子级的上边框)相等于 100% 的父级的高度，而 left 则是父级的宽度 
> + ![practice1_p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/Practice/practice1_p1.PNG)