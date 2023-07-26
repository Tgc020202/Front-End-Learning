## ECMA 历史
+ ECMAscript -> ECMA / ES
+ Actionscript -> Flash
+ ES1 于 1996 被提出，诞生了网景浏览器支持 JavaScript
+ ES2 于 1997 被提出，诞生了 IE6 和网景支持也支持，浏览器大战发生
+ ES3 于 1998 被提出，IE6 支持 windows 系统，网景逐渐衰退变为火狐
+ ES4 于 2007 被提出，太过于激进，全部浏览器不支持
+ ES3.1 于 2008 被提出，ES4 的退化版，html5 也出来了，ES Harmonious = ES3.1
+ ES5 于 2009 草案
+ ES5 于 2010 通过
+ ES6 于 2011 草案
+ ES6 于 2013 通过
+ ES6 于 2014 chrome 少量(30%)支持，html5 已经获得全面支持了，移动端也没问题
+ ES6 于 2015 chrome 过半量(60%)支持，火狐少量(30%)支持
+ ES6 于 2016 chrome 过半量(90%)支持

## ES6
+ ES6 是 ES2015 的缩写
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
+ 第二个参数代表从第几位开始查找，可以是负数

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

### 模板
+  ES6 的字符串变成了 `` 作为引用，再也不是 "" 和 '' 了
+  ${}

Example:
```
<script>
    let c = `2`;
    let a = `abcdefg${c+c}`;

    console.log(a); // abcdefg22
</script>
```

+ 可以利用模板创建元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>模板与元素的应用</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        let json = {
            'div':`<div></div>`,
            'span':`<span></span>`
        };
    
        document.write(`${json.div+json.span+json.div}`);   // 添加div和span
    </script>
</body>
</html>
```

+ 模板调用函数

Example:
```
<script>
    function show(){
        alert(1);
    }

    show``; // 弹出 1
</script>
```

### 数组 Array
#### Find(参数1,参数2,参数3)
+ 第一个参数，循环出数组所有的内容
+ 第二个参数，循环出所有的下标
+ 第三个参数，返回数组本身

Example:
```
<script>
    [1,2,3,4,5].find(function(x){
        console.log(x);
    });

    [1,2,3,4,5].find(function(x,y){
        console.log(x,y);
    });

    [1,2,3,4,5].find(function(x,y,z){
        console.log(x,y,z);
    });

    [1,2,3,4,5].find(function(x,y,z){
        console.log(z[y]);
    });
</script>
```


### 函数
1. 箭头函数
+ 概念:

```
var a = function(b){
    return c;
}
同等于: a = b => c;

写法: 函数名 = (参数) => {返回};
```

Example 1:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>箭头函数</title>
</head>
<body>
    <script>
        // 使用函数写出 find 里的函数
        [1,2,3].find(function(x){
            console.log(x);
        });

        [1,2,3].find(x => {console.log(x);});
    </script>
</body>
</html>
```

Example 2:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>箭头函数</title>
</head>
<body>
    <script>
        // 使用箭头函数触发事件
        // document.onclick = function(){
        //     document.body.style.background = 'black';
        // }

        document.onclick = () => {document.body.style.background = 'black';};
    </script>
</body>
</html>
```

Example 3:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>箭头函数</title>
</head>
<body>
    <script>
        // 匿名函数
        // (function(){
        //     alert(1);
        // })();

        (() => {alert(1);})();
    </script>
</body>
</html>
```

2. 延展参数
+ 如果有传参数，就执行此参数，如果没有传参数，那么就执行延展的值
+ 可以延展任何类型
+ 写法: function 函数名(参数=延展值){}
+ 之前的写法:

```
function a(x){
    var x = x || 1;
}
```

Example:
```
<script>
    // 延展参数: default 默认
    function show(x){
        console.log(x);
    }
    show(); // undefined

    
    function show1(x=1){
        console.log(x);
    }
    show1();    // 1
</script>
```

3. 拓展运算符
+ 函数中的参数使用 ...x 代表实参为数组进来的 x 变量

Example 1:
```
<script>
    // 拓展运算符 ...
    function show(...x){
        console.log(x);
    }
    show(1,2,3,4);  // Array type

    function show1(){
        console.log(arguments);
    }
    show1(1,2,3,4); // Arguments type

    function show2(...x){
        x.push(5);
        console.log(x);
    }
    show2(1,2,3,4); // Array type

    /*
    function show3(){
        arguments.push(5);
        console.log(arguments);
    }
    show3(1,2,3,4); // error, arguments 不能 push
    */
</script>
```

Example 2:
```
<script>
    function show4(y,...x){
        console.log(x);
    }
    show4(1,2,3,4); // 2,3,4


    // 一个参数只取一个值，剩余的会变成数组
    function show5(y=[10,100,1000],...x){
        console.log(x);
    }
    show5(1,2,3,4); // 2,3,4

    /*
    // 只有前面可以放参数，不可放置在后面
    function show6(...x,y){
        console.log(x);
    }
    show6(1,2,3,4); // error
    */
</script>
```

+ 可以合并数组

Example:
```
<script>
    var a = [1];
    var b = [2];
    var c = [3];

    var d = a.concat(b.concat(c));
    console.log(d); // [1,2,3]
    // 使用拓展运算符
    console.log([...a,...b,...c]);  // [1,2,3]
</script>
```

4. 生成器函数
+ 写法: function* 函数名(){}
+ 调用函数的方法: 函数名().next();

Example:
```
<script>
    function* show(){
        alert(1);
    }
    show(); // 没有运行


    // console.log(show);

    show().next();  // 弹出 1
</script>
```

+ 可以与 yield 搭配
> + yield 可以一直 next
> + yield 有点类似 return，所以 return 在这里没有作用

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>生成器函数</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        // 生成器函数 - yield
        function* show(){
            yield function(){
                console.log(1);
            }
            yield function(){
                console.log(2);
            }
            yield () => {
                document.body.style.background = 'black';
            }

            return 100; // 不会返回
        }
        // console.log(show().next());
        var k = show();
        // k.next().value();   // 1
        // k.next().value();   // 2

        document['onclick'] = () => {
            k.next().value();
        }
    </script>
</body>
</html>
```

#### set 和 get
+ 在 {} 里有 set 和 get 方法
+ 写法: set 或 get 的后面放名字
+ 执行的是这个名字，而不是函数
+ 当执行时:
> + 不赋值的情况，将进行 get 方法
> + 有赋值的情况，将进行 set 方法，set 最高支持一个参数

Example:
```
<script>
    var json = {};

    // console.log(json);

    /*
    json = {
        a(){
            console.log(1);
        }
    };
    json.a();   // 1
    */

    json = {
        set tgc(x){
            console.log(x);
        },
        get tgc(){
            // console.log(2);
            return {
                get wxx(){
                    console.log(3);
                }
            }
        }
    };

    // json.tgc;
    // json.tgc = 1;
    json.tgc.wxx;

</script>
```

### 块级作用域
+ 块级作用域可以解决密封问题

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>块级作用域t</title>
</head>
<body>
    <input type="button" name="" value="1">
    <input type="button" name="" value="2">
    <input type="button" name="" value="3">

    <!-- JavaScript -->
    <script>
        let allInput = document.getElementsByTagName('input');
        //for(var i = 0; i < 3 ;i++){
            /*
            allInput[i].onclick = function(){
                alert(i);   // 3
            }
            */
            
            /*
            (function(x){
                allInput[x].onclick = function(){
                    alert(x);
                }
            })(i);
            */
        //}

        // 把 var 变为 let，块级作用域
        for(let i = 0; i < 3 ;i++){
            allInput[i].onclick = function(){
                alert(i);   // 3
            }
        }
        
    </script>
</body>
</html>
```


### 结构赋值
+ 只要结构相同就可以赋值

Example:
```
<script>
    // 结构赋值

    // var a = 10;
    // var b = 20;
    // var c = 30;

    let [a,b,c] = [10,20,30];
    let [d,[e,f],g] = [40,[50,60],70];

    console.log(a); // 10
    console.log(d,e,f,g);   // 40 50 60 70
</script>
```

#### array 的结构赋值
+ `[数组值对应数组值]`

Example:
```
<script>
    show = (arr=[10,20,30,40]) => {
        let [b,c,d,e] = arr;
        console.log(b,c,d,e);
    };

    show(); // 10,20,30,40
</script>
```

#### json 的结构赋值
+ `{key 对应 key, value 对应 value}`

Example:
```
<script>
    var json = {
        'a':20,
        'b':30
    };

    let {a,b} = json;

    console.log(a,b);   // 20 30
</script>
```

### bind -> call
+ 任何函数都可以用 call，调用自己
+ 第一个参数: 就是函数的 this
+ 第二个参数之后: 就是函数的形参
+ ES5 的方法
+ 与 call 类似，但是 bind 不会调用自己

Example:
```
<script>
    function show(){
        console.log(this);
    }

    // console.log(show.bind(1));
    show.bind(1)(); // 1


    /*
        call 和 bind 的区别
        call 不需要 括号便可以调用: call();
        bind 需要括号来执行: bind()();
    */


    function show1(x,y,z){
        console.log(x,y);
    }
    show1.bind(1,2)(1); // x = 2,y = 1
    // 先进行前面直到结束才进行后面的形参
</script>
```

### 面向对象 Object Oriented
#### constructor
+ 可以精准的知道类的种类

Example:
```
<script>
    // 精准查询类的种类
    console.log([1,2,3,4].constructor());

    // 查找原型链
    console.log(Array.prototype);
</script>
```

#### toString + call
+ 可以通过 toString 和 call 打印出当前的种类

Example:
```
<script>
    // toString 和 call
    console.log(Object.prototype.toString.call(1)); // [object Number]
    console.log(Object.prototype.toString.call([])); // [object Array]
    console.log(Object.prototype.toString.call('')); // [object String]
    console.log(Object.prototype.toString.call(null)); // [object Null]
    console.log(Object.prototype.toString.call({})); // [object Object]
</script>
```

#### split
+ 字符串转数组
+ 写法:

Example:
```
<script>
    // split
    var a = ['abcdefgh'];
    console.log(String.prototype.split.call(a));    // ['abcdefgh']

    // join
    console.log(Array.prototype.join.call('abcde')); // a,b,c,d,e

    // json 也可以使用
    var json = {
        a:20,
        b:30
    };

    console.log(String.prototype.substring.call(json,'a')); // object Object
</script>
```

#### 原型链 prototype
+ 写法: new 函数名();

Example:
```
<script>
    // 原型链
    function show(){
        console.log(1);
    }

    var c = show;
    new c();

    console.log(c);
    console.log(c.prototype);

    show.prototype.a = function(){
        alert(1000);
    }

    var b = new show();
    b.a();    // 弹出 1000
</script>
```

#### ES6 里的类 class
+ 写法: 类名{}

Example:
```
<script>
    // ES6的原型链
    class a{
        constructor(){
            this.x = 10;
            console.log(this.x);
        }
    };
    new a();    // 10
</script>
```

#### ES6 里的继承 extends
+ 概念: 孩子继承父亲的所有财产，但是孩子本身的财产，不会继承给父亲

Example:
```
    <script>
        class show{
            constructor(l){
                this.x = l;
            }
            m(){
                alert(this.x);
            }
        };

        // new show(1).m();

        class tgc extends show{
            constructor(l){
                // 继承 show(父类)
                super(l);
            }
        };

        new tgc(100).m();   // 弹出 100
    </script>
```

#### ES6 里的 jquery

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ES6 里的 jquery</title>
    <style>
        input.active{
            background-color: red;
        }
        div{
            width: 200px;
            height: 200px;
            background-color: #ccc;
            margin: 10px;
        }
        .tgc{
            background-color: red;
        }
    </style>
</head>
<body>
    <div id="div1"></div>
    <div class="div1"></div>
    <div class="div1 tgc"></div>

    <script>
        class jquery{
            constructor(obj=''){
                this.obj = obj;
                this.allNode = [];
                switch(this.obj.charAt(0)){
                    case '#':
                        this.allNode.push(document.getElementById(this.obj.substring(1)));
                        // console.log(this.allNode);
                        break
                    case '.':
                        this.myObj = document.getElementsByClassName(this.obj.substring(1));
                        for(let i=0;i < this.myObj.length;i++){
                            this.allNode.push(this.myObj[i]);
                        }
                        // console.log(this.allNode);
                        break;
                    
                }
            }

            addClass(Class){
                for(let i = 0;i < this.allNode.length;i ++){
                    this.allNode[i].classList.add(Class);
                }
            }

            removeClass(Class){
                for(let i = 0;i < this.allNode.length;i ++){
                    this.allNode[i].classList.remove(Class);
                }
            }

            css(json){
                for(let i = 0; i < this.allNode.length;i++){
                    for(let j in json){
                        this.allNode[i]['style'][j] = json[j];
                    }
                }
            }
        }

        function $(obj){
            return new jquery(obj);
        }

        // $('.div1').addClass('tgc');

        div1.onclick = function(){
            // $('.div1').addClass('tgc');
            // $('.div1').removeClass('tgc');
            $('.div1').css({
                'width':'300px',
                'height':'100px',
                'transition':'1s',
                'background':'green'
            });
        }
    </script>
</body>
</html>
```





