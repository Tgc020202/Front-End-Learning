## JavaScript

### 面向对象 object-oriented
+ 所有的操作都是对对象的操作

#### 对象 object
+ new Object();
+ 万物皆是对象
+ 对象的机制:
> 1. 引用机制
> 2. 可赋予私有属性
> 3. 只要是对象就不相等的

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Object 对象的机制</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        var a = document.body;

        // 引用机制
        var b = a;
        b.style.background = 'black';   // body 变黑

        // 可赋予私有属性
        b.index = 1;
        alert(a.index); // 弹出 1
    </script>
</body>
</html>
```

##### 分辨对象
+ 除了 dom 元素，bom 元素(string,boolean,...) 里面需要添加 new(实例化) 才可以定义为对象.

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>new 实例化</title>
</head>
<body>
    <!-- JavaScript -->
    <script>
        var a = String(123);

        var b = a;
        b.c = 10;
        console.log(a.c);   // undefined


        // 使用 new 实例化
        var a = new String(123);

        var b = a;
        b.c = 10;
        console.log(a.c);   // 10
    </script>
</body>
</html>
```

##### 对象 this 的指向
+ Bom
> + 实例化之后 this 就指向实例化对象
> + 没实例化之前 this 永远就指向 window
+ Dom
> + this 永远指向发生事件的源头

Example：
```
<script>
    /* this 的指向*/
    var a = function(){
        alert(this);
    }

    // Bom
    // 实例化之后 this 就指向实例化对象
    // 没实例化之前 this 永远就指向 window
    new a();    // object Object

    // Dom
    // this 永远指向发生事件的源头
    a();    // object Window


</script>
```


##### 对象的第三个机制
+ 只要是对象就不相等，除非是引用的

Example:
```
<script>
    /*
        只要是对象就不相等
        除非是引用的
    */
    var a = [1,2,3];
    var b = a;
    var c = [1,2,3];
    var d = new Array(1,2,3);

    console.log(a == b);    // True
    console.log(a == c);    // False
    console.log(a == d);    // False
</script>
```

##### Constructor
+ 找到所有东西的原型函数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Constructor</title>
</head>
<body>
    <script>
        // 找到所有东西的原型函数
        alert(alert.constructor);   // function Function() { [native code] }
    </script>
</body>
</html>
```

##### Function 函数
+ 函数是一种 object
+ 它可以引用机制，也可赋予私有属性
+ 任何的函数都可以使用 call
+ 函数的参数，还有 arguments 都是引用


##### call
+ 改变 this 的指向
+ call 的第一个参数就是 call 之前的函数的 this

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>call 改变 this 指向</title>
</head>
<body>
    <script>
        function a(){
            alert(this);
        }
        a.call(1);

        function b(){
            this.style.background = '#000';
        }
        b.call(document.body);
    </script>
</body>
</html>
```

+ 从第二个参数到以后的参数相等于函数的第一个参数到以后的参数

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>call 改变 this 指向</title>
</head>
<body>
    <script>
        function a(x,y,z){
            alert(this);    // 1
            alert(x);   // 2
            alert(y);   //3
            alert(z);   // undefined
        }
        a.call(1,2,3);
    </script>
</body>
</html>
```

+ call 可以使函数执行完了

Example:
```
<script>
    function show(){
        this.a = 20;
        this.c = 25;
    }

    function show2(){
        this.a = 25;
        this.c = 30;
        show.call(this);
    }

    function show3(){
        show2.call(this);
    }

    alert(new show3().a + new show3().c);   // 45
</script>
```


##### apply 
+ 它的第一个参数就是 apply 之前的函数的 this
+ 跟 call 的差别在它只有两个参数

Example:
```
<script>
    // apply 写法
    function show(){
        alert(this);
    }
    show.apply(1);
</script>
```

Example(跟 call 的差别):
```
<script>
    // 只有两个参数
    function show(){
        alert(this);
    }
    show.apply(1,[],2); // 弹出 1 ，但是 2 没有作用
</script>
```

Example(报错，无法运行):
```
<script>
    // 只有两个参数
    function show(x){
        alert(x);
    }
    show.apply(1,2); //报错，因为 2 不是对象
</script>
```

+ 对第二个参数放置对象就不会报错了
+ 写法: 函数名.apply(this,对象);
Example(改正):
```
<script>
    // 只有两个参数
    function show(x){
        alert(x);
    }
    // 改正
    show.apply(1,new String('2')); // 2
</script>
```

+ 正确写法 : 函数名.apply(this,函数的参数且必须是对象类);
Example:
```
<script>
    /*
        函数名.apply(this,函数的参数且必须是对象类);
    */
    function show(x){
        alert(this);    // 1
        alert(x);       // 2
    }
    show.apply(1,new String('2'));
</script>
```

###### apply 搭配数组
+ 数组是一个对象
+ 写法 : 函数名.apply(this,数组);
+ apply 的第一个参数为 this 对象
+ 在数组里:
> + 第一个对应的函数里的第一个形参
> + 接着往后执行

Example:
```
<script>
    /*
        函数名.apply(this,数组);
    */
    function show(x,y,z){
        alert(this);    // 1
        alert(x);       // 1
        alert(y);       // 2
        alert(z);       // 3
    }
    show.apply(1,[1,2,3,4,5]);
</script>
```


##### 原型链 prototype
+ 最原始的原型
+ 给原型加方法

Example:
```
<script>
    Array.prototype.tgc = function(){
        alert(this);
    };
    [1,2,3].tgc();   // 1,2,3
</script>
```

+ 可以使用其他的数据类型连接原型链

Example:
```
<script>
    // String 字符串
    String.prototype.text = function(){
        alert(this);
    };
    "123".text();   // 123

    // Number 数字
    Number.prototype.num = function(){
        alert(this);
    };
    var a = 123;
    a.num();   // 123

    // Function 函数
    Function.prototype.func = function(){
        alert("我是函数");
    };
    function b(){};
    b.func();   // 我是函数
</script>
```

+ 如果给 object 连接原型链，那么所有的原型都等于连接了这个原型链

Example:
```
<script>
    // Object 对象
    Object.prototype.obj1 = function(){
        alert("我是对象");
    };
    // 万物皆可对象
    [].obj1();   // 我是对象
    new Date.obj1();   // 我是对象
    new String.obj1();   // 我是对象
    Function.obj1();   // 我是对象
</script>
```

+ 也可以用 JSON 方法赋予

Example:
```
<script>
    // 普通的函数原型链写法
    function tgc(){

    }

    tgc.prototype.wxx = function(){
        alert("luv u");
    };

    tgc.prototype.xxx = function(){
        alert("ermmmm");
    };

    new tgc().wxx();    // luv u
    new tgc().xxx();    // ermmmm
</script>

<script>
    // JSON 模式
    function tgc(){

    }

    tgc.prototype = {
        'wxx':function(){alert("luv u");},
        'xxx':function(){alert("ermmmm");}
    };

    new tgc().wxx();    // luv u
    new tgc().xxx();    // ermmmm
</script>
```

###### prototype 的继承方法
+ 放等号(=)
> + 好处简单
> + 坏处不精准，如果没有赋予变量，但是函数还是会照常执行(NaN)

Example:
```
<script>
    function tgc(){
        this.a = 1;
        this.b = 2;
    }

    function wxx(){
        tgc.call(this);
    }

    tgc.prototype = {
        'a1':function(){alert(this.a + this.b);},
        'b2':function(){alert(2);},
        'c3':function(){alert(3);}
    }

    wxx.prototype = tgc.prototype;
    new wxx().a1(); // 3
</script>

<script>
    function tgc(){
        this.a = 1;
        this.b = 2;
    }

    // 如果 wxx 函数没有 call tgc 函数的变量
    function wxx(){
        // tgc.call(this);
    }

    tgc.prototype = {
        'a1':function(){alert(this.a + this.b);},
        'b2':function(){alert(2);},
        'c3':function(){alert(3);}
    }

    wxx.prototype = tgc.prototype;
    new wxx().a1(); // NaN
</script>
```

+ 更精准的可以用自己的想要的方法等于别人的方法

Example:
```
<script>
    function tgc(){
        this.a = 1;
        this.b = 2;
    }

    function wxx(){
        tgc.call(this);
    }

    tgc.prototype = {
        'a1':function(){alert(this.a + this.b);},
        'b2':function(){alert(2);},
        'c3':function(){alert(3);}
    }

    wxx.prototype.a1 = tgc.prototype.a1;
    new wxx().a1(); // 3
</script>
```
> + 比如 : `wxx.prototype.a1 = tgc.prototype.a1;`


+ for in 也可以继承

Example:
```
<script>
    function tgc(){
        this.a = 1;
        this.b = 2;
    }

    function wxx(){
        tgc.call(this);
    }

    tgc.prototype = {
        'a1':function(){alert(this.a + this.b);},
        'b2':function(){alert(2);},
        'c3':function(){alert(3);}
    }

    for(var i in tgc.prototype){
        wxx.prototype[i] = tgc.prototype[i];
    }

    new wxx().a1(); // 3
</script>
```

+ 使用实例化继承

Example:
```
<script>
    function tgc(){
        this.a = 1;
        this.b = 2;
    }

    function wxx(){
        tgc.call(this);
    }

    tgc.prototype = {
        'a1':function(){alert(this.a + this.b);},
        'b2':function(){alert(2);},
        'c3':function(){alert(3);}
    }

    wxx.prototype = new tgc();

    new wxx().a1(); // 3
</script>
```
> + 比如 : `wxx.prototype = new tgc();`


##### 函数运行自己不加括号，就会返回自己

Example:
```
<script>
    function a(){alert(1);}
    alert(a);   // function a(){alert(1);}
</script>
```
















