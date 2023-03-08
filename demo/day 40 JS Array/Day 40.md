## JavaScript - 数组 Array

#### 创造数组
+ var 数组名 = [数组里的内容];
+ var 数组名 = new Array(数组里的内容);

Example:
```
<script>

    var a = [1,2,3];
    var b = new Array(1,2,3);

    console.log(a);
    console.log(b);
</script>
```

+ 当数组里的内容只有一个数值参数，就会变为数组的 length

Example:
```
<script>
    var c = new Array(3);   // 3 是 length

    console.log(c); // ['','','']
    console.log(c.length); // 3
</script>
```

#### push 添加
+ 往数组的最后面添加一条数据

Example:
```
<script>

    var arr = ['a','b'];

    arr.push('c');
    console.log(arr);   // ['a','b','c']
</script>
```

+ push 会返回新数组的长度

Example:
```
<script>

    var arr = ['a','b'];

    arr.push('c');

    console.log(arr.push('haha'));   // 4
</script>
```

#### unshift 添加
+ 往数组的最前面添加一条数据

Example:
```
<script>

    var arr = ['a','b'];

    arr.unshift('z');   
    console.log(arr);   // ['z','a','b']
</script>
```

+ unshift 会返回一个新的数组

Example:
```
<script>

    var arr = ['a','b'];

    arr.unshift('z');   
    
    console.log(arr.unshift('haha'));   // ['haha','z','a','b']
</script>
```

#### shift 删除
+ 删除最前面的数据

Example:
```
<script>

    var arr = ['a','b'];
    arr.shift();
    console.log(arr);   // b
</script>
```

+ shift 会返回删除的数据

Example:
```
<script>

    var arr = ['a','b'];
    console.log(arr.shift());   // a
</script>
```

#### pop 删除
+ 删除最后面的数据

Example:
```
<script>

    var arr = ['a','b'];
    arr.pop();
    console.log(arr);   // a
</script>
```

+ pop 会返回删除的数据

Example:
```
<script>

    var arr = ['a','b'];

    console.log(arr.pop()); // b
</script>
```

#### reverse 反转
+ 把数组里的数据的顺序反转

Example:
```
<script>

    var arr = [1,2,3];
    arr.reverse();
    console.log(arr);   // [3,2,1]
</script>
```

+ reverse 会直接返回已经反转的结果

Example:
```
<script>

    var arr = [1,2,3];
    arr.reverse();
    console.log(arr);   // [3,2,1]
    console.log(arr.reverse()); // [1,2,3]
</script>
```

#### concat 拼接
+ 将两个数组拼接成一个数组

Example:
```
<script>

    var arr = [1,2,3];
    var arr2 = [4,5,6];

    console.log(arr.concat(arr2));  // [1,2,3,4,5,6]
</script>
```

#### slice 截取
+ 数组截取，不影响数组
+ slice(起始,结束);
+ 结束不包过在内

Example:
```
<script>

    var arr = [1,2,3,4,5,6,7,8];

    // 截取 2 和 3
    console.log(arr.slice(1,3));    // [2,3]
    console.log(arr);   // 不受影响
</script>
```

#### splice 
+ 可移出数据，也可替换数据
+ splice(起始);
> + 起始的位置也会被移除
> + 起始后面的数据都被移除

Example:
```
<script>
    var arr = [1,3,'5',9];
    arr.splice(2);
    console.log(arr);   // [1,3]
</script>
```
+ splice(起始,多少个);
> + 多少个代表从起始开始要移除多少个数据

Example:
```
<script>
    var arr = [1,3,'5',9];
    arr.splice(2,1);
    console.log(arr);   // [1,3,9]

    var arr = [1,3,'5',9];
    arr.splice(2,2);
    console.log(arr);   // [1,3]
</script>
```
+ splice(起始,多少个,替换1,替换2,...);
> + 第三个参数开始全部都会被添加进去数组里

Example:
```
<script>
    var arr = [1,3,'5',9];
    arr.splice(2,1,'tgc');
    console.log(arr);   // [1,3,'tgc',9]
    
    var arr = [1,3,'5',9];
    arr.splice(2,1,'tgc','呆呆','small');
    console.log(arr);   // [1,3,'tgc','呆呆','small',9]
</script>
```
+ splice(起始,0,替换1,替换2,...);
> + 第三个参数为 0 ，就会直接插入数据进入设定起始的位置

Example:
```
<script>
    // 第二个参数为 0，就直接插入数据
    var arr = [1,3,'5',9];
    arr.splice(2,0,'tgc');
    console.log(arr);   // [1,3,'tgc','5',9]
</script>
```
+ console.log(数组.splice(起始,多少个));
> + 会返回数组里移出的数据

Example:
```
<script>
    var arr = [1,3,'5',9];
    console.log(arr.splice(2,1));   // ['5']
</script>
```

#### sort 排序
+ 从小到大排序
+ 它只看第一个数为，例如: 520 -> 5

Example:
```
<script>
    // 证明1 : 顺序
    var arr = [1,4,2,3];
    console.log(arr.sort());    // [1,2,3,4]

    // 证明2 : 只看第一个数位
    var arr = [1400,200,30,4];
    console.log(arr.sort());    // [1400,200,30,4]
    
    var arr = [1,4,5,21];
    console.log(arr.sort());    // [1,21,4,5]
</script>
```

+ 添加代码使其正常使用于任何数位 : sort(function(a,b){return a-b;})
+ 逆序 : sort(function(a,b){return b-a;})

Example:
```
<script>
    // 矫正
    var arr = [14,41,32,23];
    console.log(arr.sort(function(a,b){
        return a-b;
    }));    // [1,2,3,14]

    // 逆序
    var arr = [1,14,2,3];
    console.log(arr.sort(function(a,b){
        return b-a;
    }));    // [14,3,2,1]
</script>
```

+ sort(function(a,b){return a-b;}) 不对字母产生效果
+ 但是 sort() 可以对字母使用并排列

Example:
```
<script>
    // 证明3 : sort(function(a,b){return a-b;}) 不对字母有任何作用
    var arr = ['a','c','d','b'];
    console.log(arr.sort(function(a,b){
        return a-b;
    }));    // ['a','c','d','b']

    // 证明4 : sort() 可以发挥作用
    var arr = ['a','c','d','b'];
    console.log(arr.sort());    // ['a','b','c','d']
</script>
```

+ 如果第一个非数字相同，便会查看第二个非数字来排序，以此类推

Example:
```
<script>
    // 证明4 : 如果第一个非数字相同，就会比较第二个非数字，以此类推
    var arr = ['abc','aab','bcd','bca'];
    console.log(arr.sort());    // ['aab','abc','bca','bcd']
</script>
```

#### join
+ 数组转字符串
+ 会返回字符串，但是不影响原本的数组

Example:
```
<script>

    var arr = [1,2,3];

    arr.join('');
    console.log(arr);   // [1,2,3]
    console.log(arr.join(''));  // 123
</script>
```

+ 就算数组里有字符串也没问题

Example:
```
<script>
    var arr = [1,'2',3];
    console.log(arr.join(''));  // 123
</script>
```

#### length 长度
+ 返回长度

Example:
```
<script>

    var arr = [1,2,3];
    console.log(arr.length);    // 3
</script>
```

