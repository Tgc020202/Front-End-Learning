## JavaScript js
+ js 依赖于浏览器(打开网站的一个工具)
> + 建议使用 google 浏览器
> + 不建议用 IE 浏览器
> + 编辑器: sublime, webstorm

#### 1.1 js 的标签
+ HTML 上面 所有的内容都是标签
+ 说明也会有 js 的标签
+ 写了 js 的标签就可以使用 js 的代码运行了
Example:
```
<script></script>
```

#### 1.2 js 的变量的简单应用
+ JS 的变量是唯一性，如果有第二个相同的变量，那么之前的内容就会被覆盖
+ 用法: var 变量名称 = 赋值;
+ 弹出警告窗: alert(内容)

Example:
```
<script>
    var 筱筱 = 1;
    var 筱筱 = 2;
    alert(筱筱)
</script>
```

#### 1.3 js 的数据类型
+ js 的核心名为 ECMAScript -> ES
+ ES 里面定义了 5 种简单数据类型和 1 种复杂数据类型:
+ 简单:
> 1. Undefined = 未定义
> 2. Null = 空
> 3. Boolean = 布尔值(true or false)
> 4. Number = 数字
> 5. String = 字符串
+ 复杂:
> 1. Object = 对象

###### 1.3.1 Undefined 未定义
+ 当我们创建一个变量，但是没有定义任何的数据类型

Example:
```
<script>
    var a;
    alert(a);
</script>
```

###### 1.3.2 Null 空
+ 定义变量为 null，代表空

Example:
```
<script>
    var a = null;
    alert(a);
</script>
```

###### 1.3.3 Number 数字
+ 定义变量为数字类型，小数点或负数都接受

Example:
```
<script>
    var a = -1;
    alert(a);
</script>
```

###### 1.3.4 String 字符串
+ 定义变量为字符串类型
+ 切记要添加 '' 或者 "" 符合

Example:
```
<script>
    var a = '大呆呆 小呆呆 你就是呆呆';
    alert(a);
</script>
```

###### 1.3.5 Boolean 布尔值
+ 定义变量为布尔值，真或假
+ 可以放 true 或 false

Example:
```
<script>
    var a = true;
    alert(a);
</script>
```

###### 1.3.6 typeof
+ 可以判断变量的数据类型
+ 使用方法: typeof(检查的变量)

Example:
```
<script>
    var a = true;
    alert(typeof(a));
</script>
```

+ Special Case
Example:
```
<script>
    var a = null;
    alert(typeof(a));
</script>
```
> + output: object
> + 计算机认为这是一个'空'的对象

#### 1.4 报错类型和符号

###### 1.4.0 Symbol 符号
+ ; 符号说明这一句说完了，相当于句号
+ ，符号说明这一句话还没说完，还要继续说，相当于逗号

Example:
```
<script>
    var a = 1, b = 2;
    alert(a),alert(b);
</script>
```

###### 1.4.1 Syntax Error 语法错误
+ 所有代码完全不执行了，写的所有的 js 都失效了

Example:
```
<script>
    adadas#adsa$()
</script>
```
![错误 1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2019%20Javascript%20I/p1.PNG)

###### 1.4.2 Runtime/Reference Error 运行错误
+ 之前的都执行，就是报错的那一句和那一句之后的都不执行了

Example:
```
<script>
    var a = 1;
    alert(a);
    alert(abc);
    alert(1);
</script>
```
![错误 2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2019%20Javascript%20I/p2.PNG)
