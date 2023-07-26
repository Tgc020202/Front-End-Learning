## ES6

### 字符串模版
+ 写法: ```变量名 = `字符串${其他变量}`；```

Example:
```
<script>
    // 字符串模版
    var string = `abc`;
    console.log(string);    // abc

    // 添加
    // Number
    var a = 10;
    var string = `abc${a}`;
    console.log(string);    // abc10

    // JSON
    var json = {
        f:20
    };
    var string = `abc${a}${json.f}`;
    console.log(string);    // abc1020

    // 函数 - 字符模版可以传函数
    function show(n){
        return n;
    };
    // 无参函数
    var string = `show a number: ${show()}`;
    console.log(string);    // show a number: undefined

    // 有参函数
    var string = `show a string: ${show(2)}`;
    console.log(string);    // show a number: 2

    // 函数里有 JSON
    function show2(){
        var json = {
            a:100,
            b:200
        };
        return json;
    };
    var string = `show a number: ${show2().a}`;
    console.log(string);    // show a number: 100
</script>
```

#### 数组的 map
+ map 用法跟 find / findIndex 差不多，但是返回的不一样
+ 最后会返回一个大数组

Example:
```
<script>
    let arr = [1,2,3];
    arr.find((x,y,z) => {
        console.log(x,y,z);
    });

    arr.findIndex((x,y,z) => {
        console.log(x,y,z);
    });

    arr.map((x,y,z) => {
        console.log(x,y,z);
    });

    // 差别
    // map 返回数组
    var a = arr.map((x,y,z) => {
        console.log(x,y,z);
    });
    console.log(a);
</script>
```

#### 标签模版和模版字符串的嵌套

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>标签模版</title>
    <style>
        .outNode{
            width: 200px;
            height: 200px;
            background-color: #ccc;
            display: none;
            margin-top: 10px;
        }

        .outNode:first-of-type{
            display: block;
        }
    </style>
</head>
<body>
    <script>
        var jsonData = {
            'topValue':['tgc','wxx','abc','hehe'],
            'bottomValue':['smart','lazy','rich']
        };

        createNode = json => `<div>
            ${json.topValue.map((v)=>`<input type = button value=${v}>`).join('')}
            ${json.bottomValue.map((v)=>`<div class='outNode'>${v}</div>`).join('')}
        </div>`;
        console.log(createNode(jsonData));

        document.body.innerHTML = createNode(jsonData);

    </script>
</body>
</html>
```

#### 字符串的 string.raw() 方法
+ 可以取消转义
+ 写法: String.raw``
+ 例如: \n 段落，使用 raw 后就会使 \n 的效果失效

Example:
```
<script>
    // 转义 raw
    console.log('a\nb\nc');

    console.log(String.raw`a\nb\nc`);   // a\nb\nc

    console.log(`\u4e00`);  // 一

    console.log(String.raw`\u4e00`);    // \u4e00
</script>
```

### Number 数字
#### 二进制
+ 只有 0 和 1
+ 例如: 2 => 10(二进制)
+ 写法: 0b二进制数字

Example:
```
<script>
    // 写法: 0b二进制数字
    console.log(0b10);  // 2

    // 520
    /*
        1   0
        2   0
        4   0
        8   1
        16  0
        32  0
        64  0
        128 0
        256 0
        512 1
        从下往上
    */
    console.log(0b1000001000);  // 520
</script>
```

##### 特殊运算
+ `||` 或
+ `&&` 和
+ `| &` 运算

+ `|` 有一的加一
Example `|`:
```
<script>
    console.log(29|23); // 31
    /*
            1 2 4 8 16
        29: 1 0 1 1 1
        23: 1 1 1 0 1
        ans 1 1 1 1 1
    */
    console.log(0b11111);   // 31
</script>
```

+ `&` 相同的加一
Example `&`:
```
<script>
    console.log(29&23); // 21
    /*
            1 2 4 8 16
        29: 1 0 1 1 1
        23: 1 1 1 0 1
        ans 1 0 1 0 1
    */
    console.log(0b10101);   // 21
</script>
```

##### 次方运算
+ `>>`,`<<`

Example `<<`:
```
<script>
    console.log(2<<10); // 2048

    console.log(7<<5);  // 224
    /*
        1   14  =   7 * 2
        2   28  =   14 * 2
        3   56  =   28 * 2
        4   112 =   56 * 2
        5   224 =   112 * 2
    */
</script>
```

Example `>>`:
```
<script>
    console.log(8>>2); // 2

    console.log(224>>5);  // 7
    /*
        1   112 = 224 / 2
        2   56  = 112 / 2 
        3   28  = 56 / 2
        4   14  = 28 / 2
        5   7   = 14 / 2
    */

    console.log((1e2<<3)+0b11001000);   // 1000
    /*
        1e2 = 100
        1e2<<3 = 800
        
        128 64  32  16  8   4   2   1
        1   1   0   0   1   0   0   0
        128 + 64 + 8 = 200

        800 + 200 = 1000
    */

    setTimeout(()=>{
        alert`haha`;
    },(1e2<<3)+0b11001000);
</script>
```

##### isInteger
+ 检测是否是整数，如果是就返回 true，不是就返回 false
+ 写法: Number.isInteger();

Example:
```
<script>
    var a = 1.0000;
    var b = 1.0001;
    var c = '1';

    console.log(Number.isInteger(a));   // true
    console.log(Number.isInteger(b));   // false
    console.log(Number.isInteger(c));   // false
</script>
```

##### isNaN
+ 检测是否是 NaN

Example:
```
<script>
    console.log(isNaN('2323'));     // false
    console.log(isNaN('2323a'));    // true
    console.log(Number.isNaN('2323a')); // false
</script>
```

##### parseInt
+ 变成整数

Example:
```
<script>
    console.log(Number.parseInt == parseInt);   // true

    console.log(Number.parseInt(1.22323));  // 1
</script>
```

##### parseFloat
+ 变成小数

##### Math.pow
+ 写法: Math.pow(数字,多少次方)

Example:
```
<script>
    console.log(Math.pow(4,2)); // 16
    /*
        4 * 4 = 16
    */
</script>
```

### 方法
#### in 
+ 属性是否在这个对象上

Example(window 当对象):
```
<script>
    console.log('alert' in window); // true
    console.log('tgc' in window);   // false

    window.tgc = 'haha';
    console.log('tgc' in window);   // true
</script>
```

Example(json):
```
<script>
    var json = {
        'tgc':21,
        'hah':15
    };

    console.log('tgc' in json);   // true
    console.log('wow' in json);   // false
</script>
```

Example(event):
```
<script>
    /*
    // IE 不支持
    document.addEventListener('click',function(){
        alert(1);
    });

    // 只有 IE 支持
    document.attachEvent('onclick',function(){
        alert(2);
    });
    */

    // 解决方法
    function addEvent(obj,event,fn){
        /*
        if(obj.attachEvent){
            obj.attachEvent('on'+event,fn);
        }
        else{
            obj.addEventListener(event,fn);
        }
        */
        
        'attachEvent' in window ? obj.attachEvent('on'+event,fn):obj.addEventListener(event,fn);
    }
    console.log('attachEvent' in window);   // false
    console.log('addEventListener' in window);  // true
    addEvent(document,'click',function(){
        alert(1);
    });
</script>
```

Example(array):
```
<script>
    var arr = [1,2,3,4];

    console.log(5 in arr);  // false
    console.log(4 in arr);  // false
    // 检测的是下标
    console.log(0 in arr);  // true
</script>
```

#### for of
+ 只取值(value)，而不去键(key)

Example(array):
```
<script>
    var arr = [1,2,3,4];
    for(var i of arr){
        console.log(i);
    }
    // 1,2,3,4
</script>
```


#### set
+ 跟数组有点关系

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);
</script>
```

##### add
+ 添加数据
+ 禁止重复

Example:
```
<script>
    var set = new Set();

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    console.log(set);   // 1,2,3,4

    // 禁止重复
    set.add(4);
    set.add(4);
    set.add(4);
    set.add(4);

    console.log(set);   // 1,2,3,4
</script>
````

##### has
+ 查找数据，是否拥有或存在

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    console.log(set);   // 1,2,3,4

    // has
    console.log(set.has(1));    // true
    console.log(set.has(2));    // true
    console.log(set.has(3));    // true
    console.log(set.has(4));    // true
    console.log(set.has(5));    // false
</script>
```


##### size
+ 类似 length 长度

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    console.log(set);   // 1,2,3,4

    // size
    console.log(set.size);  // 4
</script>
```

##### keys 和 values
+ 都是返回 键(keys)

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    // key - value
    console.log(set.keys());  // 1,2,3,4
    console.log(set.values());  // 1,2,3,4
</script>
```

##### for of
+ 可以搭配 keys 和 values 使用

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    // key - value
    console.log(set.keys());  // 1,2,3,4
    console.log(set.values());  // 1,2,3,4

    // for of
    for(var i of set.keys()){
        console.log(i); // 1,2,3,4
    }
</script>
```

##### delete
+ 当成功删除，就会返回 true

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    // delete
    console.log(set.delete(4)); // true
    console.log(set);   // 1,2,3

</script>
```

##### clear
+ 直接清除

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    // clear
    console.log(set.clear());   // undefined
    console.log(set);   // size = 0
</script>
```

##### entries

Example:
```
<script>
    var set = new Set();
    // console.log(Set.prototype);

    // add
    set.add(1);
    set.add(2);
    set.add(3);
    set.add(4);

    console.log(set);   // 1,2,3,4

    // entries
    console.log(set.entries());
    console.log(typeof set);    // object
</script>
```

##### set 与 array 配合

Example:
```
<script>
    // 可以用于去重
    var arr = [1,2,3,4,5];
    var arr2 = [2,3,5,6,7,7,8];

    var set = new Set([...arr,...arr2]);
    var arr3 = [...set];

    console.log(arr3);   // [1,2,3,4,5,6,7,8]
</script>
```


#### map
+ 类似于 json
+ 不允许重复的 key 的存在

##### set
+ 添加数据

Example:
```
<script>
    var mapNode = new Map();
    console.log(mapNode);

    // set
    mapNode.set('tgc','rich');
    console.log(mapNode);

    mapNode.set('hah','wow');
    console.log(mapNode);


    // 不能存同样的 key，会覆盖
    mapNode.set('tgc','best');
    console.log(mapNode);
</script>
```

##### get 
+ 获取数据

Example:
```
<script>
    var mapNode = new Map();
    console.log(mapNode);

    // set
    mapNode.set('tgc','rich');
    console.log(mapNode);

    mapNode.set('hah','wow');
    console.log(mapNode);


    // 不能存同样的 key，会覆盖
    mapNode.set('tgc','best');
    console.log(mapNode);


    // get 
    console.log(mapNode.get('tgc'));    // best
</script>
```

##### has
+ 检测是否存在

Example:
```
<script>
    var mapNode = new Map();
    console.log(mapNode);

    // set
    mapNode.set('tgc','rich');
    console.log(mapNode);

    mapNode.set('hah','wow');
    console.log(mapNode);


    // 不能存同样的 key，会覆盖
    mapNode.set('tgc','best');
    console.log(mapNode);

    // has
    console.log(mapNode.has('tgc')); // true
</script>
```

##### delete
+ 删除数据

Example:
```
<script>
    var mapNode = new Map();
    console.log(mapNode);

    // set
    mapNode.set('tgc','rich');
    console.log(mapNode);

    mapNode.set('hah','wow');
    console.log(mapNode);

    // delete
    mapNode.delete('tgc');
    console.log(mapNode); 
</script>
```

##### clear
+ 清除所有数据

Example:
```
<script>
    var mapNode = new Map();
    console.log(mapNode);

    // set
    mapNode.set('tgc','rich');
    console.log(mapNode);

    mapNode.set('hah','wow');
    console.log(mapNode);

    // clear
    mapNode.clear();
    console.log(mapNode);
</script>
```

##### for of

Example:
```
<script>
    var mapNode = new Map();
    console.log(mapNode);

    // set
    mapNode.set('tgc','rich');
    console.log(mapNode);

    mapNode.set('hah','wow');
    console.log(mapNode);

    // for of
    for(let [k,v] of mapNode){
        console.log(k,v);
    }
    
</script>
```

##### json 与 map 的转换

Example:
```<script>
    // JSON 转 map
    var json = {
        'tgc':20,
        'aaa':21,
        'bbb':'good',
        'abc':'15'
    };

    var mapNode = new Map();
    for(var i in json){
        mapNode.set(i,json[i]);
    }
    console.log(mapNode);


    // map 转 JSON
    var json2 = {};
    for(let [k,v] of mapNode){
        json2[k] = v;
    }
    console.log(json2);
</script>
```


### Promise
+ 它是一个对象(Object)
+ 类似于一个事件，有成功或失败
+ 只要触发一个，函数就直接完成自己的任务
+ 写法:
```
one 只执行一次
then(成功的函数,失败的函数)
// 另一种写法
then(成功的函数).catch(失败的函数)
```

Example:
```
<script>
    /*
    new Promise(function(Resolved,Rejected){
        // Resolved();
        // Rejected();
    }).then(function(){
        alert('success');
    },function(){
        alert('failed');
    });
    */

    // 另一种写法
    new Promise(function(Resolved,Rejected){
        // Resolved();
        // Rejected();
    }).then(function(){
        alert('success');
    }).catch(function(){
        alert('failed');
    });
</script>
```

+ Promise 的厉害之处，就是可以无限的回掉

Example:
```
<script>
    new Promise(function(Resolved,Rejected){
        Resolved('hahaha');
        // Rejected();
    }).then(function(x){
        alert(x);
        return 'who';
    }).then(function(x){
        alert(x);
        return 'you';
    }).then(function(x){
        alert(x);
    });
</script>
```
> + 回掉了三次
> + 第一次弹出 hahaha
> + 第二次弹出 who
> + 第三次弹出 you

+ catch 了之后也还可以回掉

Example:
```
<script>
    new Promise((succ,error)=>{
        error('haha')
    }).then(()=>{}).catch((x)=>{
        console.log(x);
        return 'is you';
    }).then((x)=>{
        console.log(x);
    });
</script>
```

#### throw
+ 抛出异常，表示出大事了，不执行之后的代码了
+ 之后的代码将不再执行

Example:
```
<script>
    // throw 'tgc rich';

    console.warn('tgc rich');

    console.error('tgc rich');
</script>
```

+ console.warn() 警告，不会终止运行
+ console.error() 报错，给自己知道，不会终止运行


#### race
+ 竞速方法
+ 拿来做比较
+ 只看第一个 Promise，成功就是成功，失败就是失败

Example:
```
<script>
    Promise.race([new Promise((succ,error)=>{
        // succ('12345');
        setTimeout(succ,1000,'1');
    }),new Promise((succ,error)=>{
        // succ('abcde');
        setTimeout(succ,1200,'2');
    }),new Promise((succ,error)=>{
        // succ('11111');
        setTimeout(succ,1400,'3');
    })]).then((x)=>{
        console.log(x);
    }),()=>{

    };
</script>
```

#### all
+ 要不然就是全胜，要不然就是失败

Example:
```
<script>
    Promise.all([new Promise((succ,error)=>{
        // succ();
        // setTimeout(succ,1000);
        setTimeout(succ,1000,'11111');
    }),new Promise((succ,error)=>{
        // succ();
        // setTimeout(succ,2000);
        setTimeout(succ,1000,'22222');
    }),new Promise((succ,error)=>{
        // succ();
        // setTimeout(succ,3000);
        setTimeout(succ,1000,'33333');
    })]).then((x)=>{
        console.log(x); // 打印出 ['11111', '22222', '33333']
    }).catch(()=>{
        console.log(2);
    });
</script>
```











