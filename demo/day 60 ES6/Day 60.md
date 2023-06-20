## ES6
+ ES6 是 ES2015的缩写
+ ES1 至 ES6
+ ES4 不被使用
+ 块作用域 - `{}`


### 声明方式
+ 变量 - 随时可以变化
+ 常量 - 一旦定义了，就不能改变了

1. var
> + 可以覆盖之前定义过的变量

Example:
```
<script>
    // var 是变量
    var a = 10;
    var a = function(){};
</script>
```

2. let
> + 变量不允许重复声明
> + 但是允许重新赋值
> + 可以防止变量泄露

Example:
```
<script>
    // let 不允许重复声明
    let b = 10;
    // let b = function();  // 会报错
    b = function(){};   // 但可以重新赋值
</script>
```

3. const
> + 真正的常量
> + 不允许重复声明
> + 不允许重新赋值

Example:
```
<script>
    // const 真正的常量，不允许重复声明，也不允许重新赋值
    const c = 10;
    // c = 1000;    // 会报错
    console.log(c); // 10
</script>
```

+ let 和 var 对比
Example:
```
<script>
    // var 和 let 例子做对比
    // var
    for(var i = 0; i < 10;i++){}
    console.log(i); // 10
    // let
    for(let j = 0; j < 10;j++){}
    console.log(j); // error, j is not defined
</script>
```

### String 字符串

#### fromCharCode/charCodeAt
+ fromCharCode 获取字符，能让编码转成字符
+ charCodeAt 获取编码
+ 编码的例子: utf-8, utf-16, utf-4, gb2312
+ 用法:
> String.fromCharCode(编码)
> 字符串变量.charCodeAt(要查找的字符的字节);

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>charCodeAt</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        let a = 'asd';
        console.log(a.charCodeAt(0));   // a : 97

        let b = String.fromCharCode(97);
        console.log(b); // a
    </script>
</body>
</html>
```

Example(展示所有的中文字符):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>charCodeAt and fromCharCode</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        // 打印所有中文字
        let mandarin = '';
        for(let i = 0x4e00; i < 0x9fa5 ;i++){
            // console.log(i);
            name += String.fromCharCode(i);
        }
        // console.log(name.length);
        document.body.innerHTML = name;
    </script>
</body>
</html>
```

#### repeat
+ 接受一个参数，参数就是重复字符串的数量

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>repeat</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        let a = 'abc';

        console.log(a.repeat(3));
    </script>
</body>
</html>
```

#### Includes
+ 类似 indexOf
+ 会返回布尔值(Boolean)
+ 第一个参数代表要找的内容
+ 第二个参数代表从第几位开始，可以是负数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Includes</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        let a = "abcdefghijkl";
        console.log(a.includes('a'));   // true

        console.log(a.includes('a',1)); // false
    </script>
</body>
</html>
```

#### startsWith
+ 起始位置
+ 字符串.startsWith('参数1',参数2);
+ 如果字符串的开头与参数1匹配，就会返回 true，不匹配就返回 false
+ 第二个参数代表设置第几个字节为开头，默认值为 0

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>startswith</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        let a = 'abc';
        console.log(a.startsWith('a')); // true
        console.log(a.startsWith('b')); // false


        console.log(a.startsWith('b',1));   // true
    </script>
</body>
</html>
```

#### endsWith
+ 结束位置
+ 字符串.endsWith('参数1',参数2);
+ 如果字符串的结尾与参数1匹配，就会返回 true，不匹配就返回 false
+ 第二个参数代表设置第几个字为末端，默认值为字符串的长度
> + 比如: 字符串 = "abc", 第二个参数 = 3, 代表 c 为末端 

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>endswith</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        let a = 'abc';
        console.log(a.endsWith('c')); // true
        console.log(a.endsWith('b')); // false

        console.log("");

        console.log(a.endsWith('',0));   // true
        console.log(a.endsWith('a',0));   // false
        console.log(a.endsWith('c',0));   // false

        console.log("");

        console.log(a.endsWith('a',1));   // true
        console.log(a.endsWith('c',1));   // false

        console.log("");

        console.log(a.endsWith('b',2));   // true
        console.log(a.endsWith('c',2));   // false

        console.log("");

        console.log(a.endsWith('a',3));   // false
        console.log(a.endsWith('c',3));   // true
    </script>
</body>
</html>
```
