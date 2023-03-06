## JavaScript - Datatype 数据类型详解

#### 全局变量
+ 依托于 window 环境下的变量

Example:
```
<!-- JavaScript -->
    <script>
        // 全局变量
        var a = 10;
        window.onload = function(){
            alert(a);
        }
    </script>
```

#### 作用域的变量 function
+ 作用在一个区域下的变量

Example:
```
<!-- JavaScript -->
    <script>
        // 作用域变量
        window.onload = function(){
            var a = 10;   
        }
        alert(a); // 报错
    </script>
```
> + 会报错，因为虽然 a 被 alert 调用了，可是 a 实际上并没有被创造更何况是赋值
> + 虽然说 window.onload 里的 function 有赋值给 a 了，但是那是它的 a，而不是给全局的 a，所以无法调用
> + 如果想要调用函数里的变量，就必须先调用那个变量的函数，然后把函数里的变量设为 window
> + 下面的例子会教怎么设置成 window 变量

#### window 的变量
+ 所有的变量都可以省略 window，直接写变量

Example:
```
<!-- JavaScript -->
    <script>
        // 如果没有写 var 直接写 a 相当于 window.a
        window.a = a = 10;
        onload = function(){
            alert(a);
        }
        
        
        // 另一个例子
        function a(){
            b = 20
        }
        a();    // 调用 a 函数
        alert(b);   // 20 弹出来了
    </script>
```
> + 有两种变成 window 变量的写法:
> + + window.变量 = 值;
> + + 变量 = 值;

#### 变量
+ 可以变化的量
+ 成为变量的条件:
> + 变量名不能以数字为开头
> + 在 JS 中有意义的单词都不能为变量名

Example:
```
<!-- JavaScript -->
    <script>
        // 可接受的变量形式
        // underscore 下划线
        var _____ = 10;
        alert(_____);   // 没问题
        
        // 中文
        var 呆呆 = 18;
        alert(呆呆);

        // 驼峰命名法
        var XiaoXiaoDaiDai = 100;
        alert(XiaoXiaoDaiDai);
    </script>
```

#### 变量的种类
+ typeof 是 JS 中用来判断变量的格式的一个方法
+ typeof 是不会报错的
+ 写法: typeof(变量);
1. 字符串 String
2. 数值 Number
3. 布尔值 Boolean
4. 函数 Function
5. 对象 Object
6. 没格式 Undefined

Example:
```
<script>
    // 六种数据格式
    var a = '1';
    alert(typeof(a));   // String

    var b = 1;
    alert(typeof(b));   // Number

    var c = true;
    alert(typeof(c));   // Boolean

    var d = function(){}
    alert(typeof(d));   // Function

    var e = {};
    alert(typeof(e));   // Object

    var f = undefined;
    alert(typeof(f));   // Undefined

    // 其他的对象
    var g = null;
    alert(typeof(g));   // object

    var h = [];
    alert(typeof(h));   // object
</script>
```

+ 证明
> + 两个等于符号 - equality 等同 -> 两边值类型不同的时候，会先进行类型转换再对比
> + 三个等于符号 - identity 恒等 -> 两边值类型不同的时候，不做类型转换就直接对比
> + 字面量，才有可能相等，比如 var a = 123，a 就是字面量
> + 任何对象 object 都是不相等的

Example 1:
```
<script>
    var a = '123';
    var b = '123';
    var b1 = 123;
    var c =  new String('123');
    var c1 = new String('123');

    alert(a == b);  //true
    alert(a === b); //true
    alert(a == b1);  //true
    alert(a === b1); //false

    alert(a == c);  //true
    alert(b === c); //false, b = string, c = object
    alert(c == c1); //false, 因为所有的对象是不相等的，只有字面量才可能相等
</script>
```

Example 2:
```
<script>
    var a = [1,2,3];
    var b = [1,2,3];
    var c = new Array(1,2,3);

    console.log(a == b);    // false
    console.log(a === b);   // false
    console.log(b == c);    // false

    /*
        array 数组是对象，对象不能相同，所以全都是 false
    */

    // 另外的例子 1
    var e = [1,2,3];
    var f = e;
    e.push(1);
    console.log(f); // 1,2,3,1
    

    // 另外的例子 2
    var g = [1,2,3];
    function h(i){
        i.push(1);
    }
    h(g);
    console.log(g); // 1,2,3,1

    // 另外的例子 3
    var j =[1,2,3]; // 内存地址: 1000
    function k(l){
        l = [4,5,6];  // 内存地址: 1001
    }
    k(j); // 内存地址: 1000
    console.log(j); // 1,2,3  // 内存地址: 1000
</script>
```
> + 数组 array 是对象，对象都是不相等的
> + 数组 array 的内存地址没有改变，所以例子 3 才不会有变化









































