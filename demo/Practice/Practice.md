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
> + ![practice1_p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/Practice/Practice%201%20-%20KiteEffect/practice1_p1.PNG)


#### Practice 2 - 色块布局
+ ![practice2_p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/Practice/Practice%202%20-%20ColorBlockDesign/practice2_p1.PNG)
+ 根据图文使用 photoshop 计算像素和色号，做出一模一样的，图文

Answer:
+ ![practice2_p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/Practice/Practice%202%20-%20ColorBlockDesign/practice2_p2.PNG)
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>色块布局</title>
    <style>


        *{padding: 0;margin: 0;}

        .myDiv{
            width: 599px;height: 297px;
            background-color: black;
            position: absolute;
            left: 50%;top: 50%;
            margin-left: -299.5px;
            margin-top: -148.5px;
        }

        .header{
            float: left;width: 100%;
            height: 60px;background-color: red;

            /* 字体 */
            text-align: center;
            font-size: 22px;
            color: black;
        }

        .leftside{
            width: 121px;height: 180px;
            float: left;
            background-color: #808080;

            /* 字体 */
            text-align: center;
            font-size: 22px;
            color: black;
        }

        .rightside{
            width: 478px;
            height: 180px;
            float: left;
            background-color: green;
        }

        .rightside .righttop{
            width: 100%;
            height: 55px;
            background-color: #cdcc00;

            /* 字体 */
            text-align: center;
            font-size: 22px;
            color: black;
        }

        .rightside .left{
            width: 240px;
            height: 125px;
            float: left;
            background-color: #cccdec;

            /* 字体 */
            text-align: center;
            font-size: 22px;
            color: black;
        }

        .rightside .right{
            width: 238px;
            height: 125px;
            float: left;
            background-color: #ccee03;

            /* 字体 */
            text-align: center;
            font-size: 22px;
            color: black;
        }

        .foot{
            width: 100%;
            height: 57px;
            float: left;
            background-color: #d4cfc9;

            /* 字体 */
            text-align: center;
            font-size: 22px;
            color: black;
        }

    </style>
</head>
<body>
    <div class="myDiv">
        <div class="header">Header</div>
        <div>
            <div class="leftside">LeftSide</div>
            <div class="rightside">
                <div class="righttop">RightTop</div>
                <div>
                    <div class="left">Left</div>
                    <div class="right">Right</div>
                </div>
            </div>
        </div>
        <div class="foot">Foot</div>
    </div>
</body>
</html>
```
> + CSS 部分就算设置属性而已，任何下面 body 的部分就算排列 div 的分成，区分父级子级
