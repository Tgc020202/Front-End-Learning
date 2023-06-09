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








