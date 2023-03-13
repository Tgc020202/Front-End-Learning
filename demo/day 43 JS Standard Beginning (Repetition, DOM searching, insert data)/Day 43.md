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

















