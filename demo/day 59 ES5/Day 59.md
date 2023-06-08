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
+ ![p1]()

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






