# JavaScript - ES5

## ES5的历史
+ 2009 年发布
+ 2011 年 ES5.1 发布，正式成为 IOS 国际标准
+ 2015 年 ES6 

## 四大块
1. JSON 对象
2. Object 对象方法的扩展
3. 严格模式
4. Array 拓展

### ES5 - JSON
1. JSON 是一个对象
2. key and value - 键值队
3. key 是双引号
4. 缩写形式 - new Object()
5. JSON 的属性
+ ![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2059%20ES5/JSON/Images/P1.png)

Example:
```
<!-- JavaScript -->
<script>
    /*
    // 错误写法
    var json = {
        a:10
    };
    console.log(json);  // {a: 10}
    */

    /*
    // 正确写法
    var json = {
        "a":10
    };
    console.log(json);  // {a: 10}
    */

    // 正确写法
    var json = new Object();
    json.a = 10;
    console.log(json);  // {a: 10}
</script>
```

#### JSON - parse
+ 把字符串转换为 JSON
+ 写法 : JSON.parse(参数1,参数2);

Example(参数1):
```
<script>
    /*
    // 错误示范
    var string = '{a:10}';
    console.log(JSON.parse(string));    // 报错
    */

    /*
    // 错误示范
    var string = "{'a':10}";
    console.log(JSON.parse(string));    // 报错
    */

    // 正确示范
    var string = '{"a":10}';
    console.log(JSON.parse(string));    // {a: 10}
</script>
```
> + 第一个参数必须是正确的 string 的 JSON 的格式

Example(参数2):
```
<script>
    var string = '{"a":10}';
    JSON.parse(string,function(key,value){
        console.log(key,value); // a 10
    })

    var string = '{"a":10,"b":20,"c":30}';
    JSON.parse(string,function(key,value){
        console.log(key,value);
    })
</script>
```
> + 第二个参数是一个 function， function 里可以有两个参数，分别为 key 和 value.
> + key 对应着 解析的 JSON 的 key
> + value 对应着 解析的 JSON 的 value


#### JSON - stringify
+ 把 JSON 对象 转为字符串
+ JSON.stringify(参数1,参数2);

Example(参数1):
```
<script>
    var json = {a:20};
    console.log(JSON.stringify(json));  // {"a":20}
</script>
```
> + 第一个参数就是一个 JSON

Example(参数2):
```
<script>
    var json = {a:20,b:30,c:50};
    console.log(JSON.stringify(json,function(key,value){
        return value;
    }));

    console.log(JSON.stringify(json,function(key,value){
        if(value == 30){
            return undefined;
        }
        else{
            return value;
        }
    }));
</script>
```
> + 第二个参数是一个 function
> + 可用于过滤需要的数据

Example(参数3):
```
<script>
    var json = {a:20,b:30,c:50};
    console.log(JSON.stringify(json,function(key,value){
        return value;
    },5));
</script>
```
> + 第三个参数是推进
> + 1 至 10
> + key 值离左边有多少的空格


### ES5 - Object 对象

#### Object - getPrototypeOf
+ 返回对象的原型 : Object.getPrototypeOf;
+ 也可以直接使用 prototype

Example:
```
<script>
    function tgc(){

    };

    tgc.prototype = {
        "a":'10',
        "b":20,
        "c":function(){
            alert(1);
        }
    };
    console.log(Object.getPrototypeOf(new tgc()));
    console.log(tgc.prototype == Object.getPrototypeOf(new tgc())); // true
    console.log([].constructor.prototype == Object.getPrototypeOf(Array())); // true
</script>
```

#### Object - keys
+ 以数组的形式取得对象的属性(keys)

Example:
```
<script>
    var a = {
        a:10,
        b:20
    };

    /*
    var arr = [];
    for(var i in a){
        arr.push(i);
    };
    console.log(arr);   // a, b
    */

    console.log(Object.keys(a));   // a, b
</script>
```

Example:
```
<script>
    function tgc(){
        this.a = 20;
    }

    tgc.prototype = {
        b:30,
        c:40
    }


    console.log(Object.keys(new tgc()));    // a
</script>
```
> + 只拿函数的私有属性

#### Object - values
+ 以数组的形式取得对象的属性值(values)

Example:
```
<script>
    var json = {
        a:30,
        b:40
    };
    /*
    var arr = [];
    for(var i in json){
        arr.push(i);
    };
    console.log(arr);   // 30, 40
    */
    console.log(Object.values(json));   // 30, 40
</script>
```

Example:
```
<script>
    function tgc(){
        this.a = 20;
    }

    tgc.prototype = {
        b:30,
        c:40
    }
    console.log(Object.values(new tgc()));    // 20
</script>
```

#### Object - create
+ 创建一个具有指定原型并且可以选择性的包含指定属性的对象
+ 如果不想指定原型，可以放置 null

Example:
```
<script>
    var a = Object.create(null);
    console.log(a); // Object
</script>
```

Example:
```
<script>
    function tgc1(){

    };
    function tgc2(){

    };

    tgc1.prototype.a = 100;
    tgc2.prototype.f = 30;

    // 另类的继承
    tgc1.prototype = Object.create(tgc2.prototype);

    console.log(new tgc1().f);  // 30
    console.log(new tgc2().a);  // undefined
</script>
```

##### Object.create 进阶用法
1. writable
2. enumerable
3. configurable
> + 这三样属性 JSON 都会默认 true

```
{
'value' : 内容,            [值]
'writable' : true/false,   [是否可以修改]
'enumerable' : true/false, [是否可以枚举,比如 for in, objects.keys, JSON.stringfy]
'configurable' : true/false[是否可以删除,比如 delete]
}
```

Example:
```
<script>
    var o = Object.create(null,{
        a:{
            'value':20,
            'writable':false,
            'enumerable':false,
            'configurable':true
        }
    });

    console.log(o.a);   // 20

    // writable = false, 所以不能改变
    o.a = 30;
    console.log(o.a);   // 20

    // enumerable = false, 所以不能以枚举的方式显示
    Object.keys(o); // []

    // configurable = true, 所以可以删除对象的属性
    delete o.a;
    console.log(o.a);   // undefined
</script>
```

#### Object - seal
+ 密封，封条
+ 对象不可以拓展，不能往里面放入新的属性
+ configurable 都变成 false

Example:
```
<script>
    var json = {
        a:10,
        b:20
    };

    // 密封
    Object.seal(json);

    // 添加无效
    json.c = 30;
    console.log(json);  // 10, 20

    // 删除无效
    delete json.a;
    console.log(json);  // 10, 20

    // 更改有效
    json.a = 1000;
    console.log(json);  // 1000, 20
</script>
```

Example(进阶用法):
```
<script>
    function tgc(){
    };

    Object.seal(tgc.prototype);
    tgc.prototype.a = 30;

    console.log(new tgc().a);   // undefined
</script>


<script>
    function tgc(){
    };

    Object.seal(tgc.prototype);

    // 重新赋值
    tgc.prototype = {
        a:30
    }

    console.log(new tgc().a);   // 30
</script>


<script>
    var json = {
        a:20
    }
    
    Object.seal(json);
    // 重新赋值
    json = {
        b:100
    }

    console.log(json);   // b:100
</script>
```
> + 一旦重新赋值，seal 的效果就会失效

#### Object - preventExtensions
+ 不可拓展了
+ 与 seal 类似，但是 configurable 是 true
+ 与 seal 一样，一旦重新赋值，它的效果就会失效

Example:
```
<script>
    var json = {
        a:20
    }

    Object.preventExtensions(json);
    // 添加无效
    json.b = 30;
    console.log(json);  // a:20

    // 删除有效
    delete json.a;
    console.log(json);  // 
</script>
```

#### Object - freeze
+ 结冰，冻结
+ 对象不可以拓展，不能往里面添加新的属性
+ configurable 所有的都是 false
+ writable 所有的都是 false
+ 一旦重新赋值，它的效果就会失效

Example:
```
<script>
    var json = {
        a:20,
        b:30
    }

    Object.freeze(json);

    // 更改无效
    json.a = 100;
    // 删除无效
    delete json.b;
    // 添加无效
    json.c = 1000;

    console.log(json);  // 20,30
</script>
```

#### Object - defineProperty
+ Object.defineProperty(对象,属性,修改或者添加的值);
+ 方法会直接在一个对象上定义一个新的属性，或者修改一个对象的现有属性，并且返回这个对象

Example:
```
<script>
    var json = {};

    Object.defineProperty(json,'key',{
        value:'tgc',
        writable:false,
        enumerable:false,
        configurable:false
    });

    json.key = "wow";
    console.log(json);  // tgc
</script>

<script>
    var json = {"key":"wxx"};

    Object.defineProperty(json,'key',{
        value:'tgc'
    });

    console.log(json);  // tgc
</script>
```

Example(进阶):
```
<script>
    function tgc(){}

    Object.defineProperty(tgc.prototype,"hehe",{
        value:function(){
            alert(1);
        },
        writable:false
    });

    // 相同
    /*
    tgc.prototype = {
        "hehe":function(){
            alert(1);
        }
    }
    */

    // 修改无效
    tgc.prototype.hehe = function(){
        alert(2);
    }

    new tgc().hehe();   // 弹出 1
</script>
```

#### Object - isSealed
+ 只会返回 true 或 false
+ true : 无法在对象中修改现有的属性的特性，且无法向对象中添加新属性
+ false : 其他的

Example:
```
<script>
    var json = {};
    console.log(Object.isSealed(json)); // false

    Object.preventExtensions(json);
    console.log(Object.isSealed(json)); // true
    
</script>

<script>
    // 里面一旦有值，preventExtensions 就会允许 delete，然后就不满足 seal 了
    var json = {"key":"tgc"};

    Object.preventExtensions(json);
    console.log(Object.isSealed(json)); // false

</script>

<script>
    // 可以使用 defineProperty 来解决
    var json = {"key":"tgc"};

    Object.preventExtensions(json);
    Object.defineProperty(json,"key",{
        configurable:false
    });
    console.log(Object.isSealed(json)); // true

</script>
```

#### Object - isExtensible
+ 判断对象是否可拓展，如果不能拓展就返回 false，否则就返回 true

Example:
```
<script>
    var json = {};

    // 未设置任何东西
    console.log(Object.isExtensible(json)); // true

    // 使 json 不可拓展
    Object.seal(json);
    console.log(Object.isExtensible(json)); // false
</script>
```

#### Object - isFrozen
+ 只会返回 true 或 false
+ true : 无法在对象中修改现有的属性的特性，且无法向对象中添加新属性(configurable = false)，且不能修改属性的内容(writable = false)
+ false : 其他的

Example:
```
<script>
    var json = {"key":"tgc"};
    console.log(Object.isFrozen(json)); // false

    Object.preventExtensions(json);
    console.log(Object.isFrozen(json)); // false

    Object.seal(json);
    console.log(Object.isFrozen(json)); // false

    Object.freeze(json);
    console.log(Object.isFrozen(json)); // true
</script>

<script>
    var json = {"key":"tgc"};
    console.log(Object.isFrozen(json)); // false

    // 使其不能拓展
    Object.preventExtensions(json);
    // 使其不能添加，删除和更改
    Object.defineProperty(json,"key",{
        writable:false,
        configurable:false,
    });
    console.log(Object.isFrozen(json)); // true
</script>
```

#### Object - hasOwnProperty
+ 确定某个对象是否具有指定的一个属性
+ 有就返回 true，没有就返回 false
+ 实例化对象
+ 与 in 是有区别的

Example:
```
<script>
    var json ={
        a:"tgc"
    };

    console.log('a' in json);   // true
    console.log(json.hasOwnProperty('a'));  //true
</script>
```

+ 实例化

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body class="tgc">
    <script>
        // 区别
        console.log('className' in document.body);  // true
        console.log(document.body.hasOwnProperty('className')); // false
    </script>

    <script>
        function tgc(){};
        tgc.prototype = {
            a:10
        }
        console.log('a' in tgc.prototype);  // true
        console.log(tgc.prototype.hasOwnProperty('a')); // true
    </script>

    <script>
        var a = new String('aaa');
        console.log(String.prototype.hasOwnProperty('split')); // true
    </script>
</body>
</html>
```

#### Object - setPrototypeOf
+ `_proto_`
+ 设置对象的原型链
+ Object.setPrototypeOf(子对象,父对象);
+ 继承 - 儿子继承父亲的，父亲不能拿儿子的

Example:
```
<script>
    var obj1 = {
        x:1
    };
    var obj2 = {
        y:1
    };
    Object.setPrototypeOf(obj1,obj2);
    console.log(obj1);
    console.log(obj1.y);    // 1
    console.log(obj2.x);    // undefined
</script>
```

Example(给函数使用继承):
```
<script>
    function tgc(){};
    tgc.prototype = {
        a:function(){
            alert(1);
        }
    }

    function tgc2(){};
    /*
    // 普通的继承方法
    tgc2.prototype = new tgc();
    console.log(new tgc2().a);  // function(){alert(1);}
    */
    
    // 使用 setPrototypeOf
    Object.setPrototypeOf(tgc2.prototype,tgc.prototype);
    console.log(new tgc2().a);  // function(){alert(1);}
</script>
```

### ES5 - 严格模式
1. 消除一堆 JS 上的静默错误，通过改变他们来抛出错误。
2. 严格模式修复了 JS 引擎执行优化的错误。严格模式可以让 JS 允许的速度更快。
3. 严格模式金钟了 ES 的未来的版本可能会定义的一些语言。
4. IE8 以前的版本不兼容了。

#### 严格模式的使用方法
+ 就是在需要严格模式之前，写上 'use strict';
1. 没有 var 的变量不认为是全局变量，必须严谨添加 window，使其变为全局变量

Example:
```
<script>
    // window
    // var 不写 var，就会默认 window的
    // var a = 10;
    a = 10; // window.a = 10;
    alert(a);   // 弹出 10
</script>

<script>
    // 使用 use strict
    'use strict';
    b = 10;
    alert(b);   // error, b is not defined
</script>

<script>
    // 使用 use strict
    // 解决方法
    'use strict';
    window.b = 10;
    alert(b);   // 弹出 10
</script>
```

2. 严格会引起静默失效
+ 有一些永恒的变量是不允许赋值的
> + 例子: window, top, NaN

Example:
```
<script>
    window = 1;
    console.log(window);
</script>

<script>
    'use strict';
    window = 1;
    console.log(window);    // Cannot set property window of #<Window> which has only a getter
</script>
```

+ writable，configurable，enumerable 也都不允许赋值

Example 1:
```
<script>
    // 严格模式会提醒，已经无法更改了，所以没必要写更改的代码
    'use strict';
    var json = {};
    Object.defineProperty(json,"tgc",{
        value:'18',
        writable:false
    });
    json.tgc = 20;
    console.log(json.tgc);  // error
</script>
```

Example 2:
```
<script>
    'use strict';
    var json = {tgc:20};
    Object.preventExtensions(json);
    json.a = 30;
    console.log(json);  // error
</script>
```

3. 试图删除不可删除的属性，也会报错(在非严格模式下，不会奇效，但也不会报错)

Example:
```
<script>
    // 非严格模式
    delete Object.prototype;
</script>

<script>
    // 严格模式
    'use strict';
    delete Object.prototype;    // error
</script>
```

4. 属性更规整了，不允许出现不规整的属性赋值

Example:
```
<script>
    // 非严格模式
    false.true = 1;
    null.true = 1;
    (222).k = 1;
</script>

<script>
    // 严格模式
    'use strict';
    false.true = 1; // Cannot create property 'true' on boolean 'false'
    null.true = 1;  // Cannot set properties of null (setting 'true')
    (222).k = 1;    // Cannot create property 'k' on number '222'
    // error
</script>
```

5. 增加了一写关键字(eval, arguments)，不允许赋值

Example:
```
<script>
    var eval = 1;
</script>

<script>
    'use strict';
    // var arguments = 1;
    var eval = 1;   // error, Unexpected eval or arguments in strict mode
</script>
```

6. 函数内的正确参数使用

Example:
```
<script>
    function tgc(a,a,c){
        console.log(a+b+c);
    };
    // 显示错误 : 找不到 b
    tgc(1,2,3); //  b is not defined at tgc
</script>

<script>
    function tgc(a,a,c){
        'use strict';
        console.log(a+b+c);
    };
    // 显示错误 : a 参数重复了
    tgc(1,2,3); // Duplicate parameter name not allowed in this context
</script>
```

### ES5 - Array 数组拓展

#### Array - Every
+ 检测数组的所有元素是否符合条件，如果符合就返回 true，否则就返回 false

Example:
```
<script>
    var arr = [1,2,3];
    arr.every(function(x){
        console.log(x); // 1
    });

    arr.every(function(x){
        console.log(x); // 1,2,3
        return x;   // true,true,true,false
    });

    arr.every(function(x){
        console.log(x); // 1,2
        return x<=1;    // true,false
    });
</script>
```

#### Array - Some
+ 检测数组的所有元素是否符合条件，只要一个符合就返回 true，除非都不符合就返回 false
+ 一旦条件满足就不继续往下看了

Example:
```
<script>
    var arr = [1,2,3];
    arr.some(function(x){
        console.log(x); // 1,2,3
    });

    // Example 1
    arr.some(function(x){
        console.log(x); // 1
        return x<=1;
    });

    console.log(arr.some(function(x){
        return x<=1;    // true
    }));

    // Example 2
    arr.some(function(x){
        console.log(x); // 1,2
        return x>=2;    // true
    });

    console.log(arr.some(function(x){
        return x>=2;    // true
    }));

</script>
```

#### Array - Filter
+ 过滤
+ 检测所有的元素，通过你的 return 过滤条件，过滤出一个新的数组

Example:
```
<script>
    var arr1 = [1,2,3,'4','5',null];
    var arr2 = [];

    for(var i = 0 ; i < arr1.length; i++){
        typeof arr1[i] == 'number' && arr2.push(arr1[i]);
    }
    console.log(arr2);  // 1,2,3
</script>

<script>
    var arr1 = [1,2,3,'4','5',null];

    var arr2 = arr1.filter(function(x){
        return typeof x == 'number';
    });
    console.log(arr2);  // 1,2,3
</script>
```

#### Array - Foreach
+ 参数是一个函数，函数里面的参数有三个值
> + 第一个值分别对应的数组的每一个值
> + 第二个是索引值
> + 第三个是数组的本身

Example:
```
<script>
    var arr = [1,2,3];
    arr.forEach(function(x,y,z){
        console.log(x,y,z);
    });

    arr.forEach(function(x,y,z){
        // x = 数值
        // y = 索引值
        // z = 数组本身
        console.log(x == z[y]);
    });
</script>
```

#### Array - Map
+ 参数是一个函数，函数里面的参数有三个值
> + 第一个值分别对应的数组的每一个值
> + 第二个是索引值
> + 第三个是数组的本身
+ 与 forEach 不同的地方在于，他会返回一个新数组
+ 可以通过 return 来操作新数组的内容

Example:
```
<script>
    var arr = ['tgc','help','wxx'];
    var arr2 = arr.map(function(x){
        return x.toUpperCase();
    });
    console.log(arr2);  // ['TGC','HELP','WXX']
</script>
```










