## JavaScript - Error 报错

#### 编写型错误
+ 自己的原因，而导致报错
+ 但是报错之前的指令都会执行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>编写型错误</title>
</head>
<body>
    <!-- JavaScript -->
    <script>

        alert(1);   // 1
        a;          // error
        alert(2);   // 没有执行
    </script>
</body>
</html>
```


#### 编译型错误
+ 因为一个错误导致全部指令都不会执行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>编译型错误</title>
</head>
<body>
    <!-- JavaScript -->
    <script>

        alert(1);   // 1
        null.....          // error
        alert(2);   // 没有执行
    </script>
</body>
</html>
```