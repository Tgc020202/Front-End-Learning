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



















