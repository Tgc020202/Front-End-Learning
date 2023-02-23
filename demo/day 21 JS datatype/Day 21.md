## JavaScript - Datatype 数据类型
+ Number
+ String
+ Boolean
+ Undefined
+ Null 
+ Object


#### 1.1 Number 数字
+ 可以使用 + - * / > < 这些算法

###### 1.1.1 加法 +
Example:
```
<script>
    console.log(1 + 1);

    var a = 1;
    console.log(a + 1);
</script>
```

###### 1.1.2 减法 -
Example:
```
<script>
    console.log(10 - 5);
</script>
```

###### 1.1.3 除法 /
Example:
```
<script>
    console.log(10 / 5);
</script>
```

###### 1.1.4 乘法 *
Example:
```
<script>
    console.log(10 * 5);
</script>
```

###### 1.1.5 取余 mod %
Example:
```
<script>
    console.log(10 % 5);
</script>
```

###### 1.1.6 大于小于 > <
+ 这个只会返回布尔值(true or false)
Example:
```
<script>
    console.log(10 > 5);

    console.log(10 < 5);
</script>
```

###### 1.1.7 大于等于 小于等于 >= <=
+ 这个只会返回布尔值(true or false)
Example:
```
<script>
    console.log(10 >= 5);

    console.log(10 <= 5);
</script>
```


###### 1.1.8 | 异或符号(XOR)
+ 位运算
+ 这个是二进制算法符号
Example:
```
<script>
    console.log(3|5);   // 答案 = 7
</script>
```
> 解释:
> 二进制: 1 2 4 8 16 32 64 128 256 512 1024 2048 ...
> 3 = 1 1 0 
> 5 = 1 0 1
> 把有数值 1 的号码拿下来
> 答案: 1 1 1 = 1 + 2 + 4 = 7


###### 1.1.9 & 同或符号(XNOR)
+ 位运算
+ 这个是二进制算法符号
Example:
```
<script>
    console.log(3&5);   // 答案 = 1
</script>
```
> 解释:
> 二进制: 1 2 4 8 16 32 64 128 256 512 1024 2048 ...
> 3 = 1 1 0 
> 5 = 1 0 1
> 把两边都有数值 1 的号码拿下来
> 答案: 1 0 0 = 1 = 1

###### 1.1.10 bug
+ 小数点会有 bug
Example:
```
<script>
    console.log(1.1 + 2.2); // 3.3000000000000003
    console.log(1.1 + 2.2 == 3.3);  // false
</script>
```

###### 1.1.11 级别
1.  + - * /
2.  > < <= >=
3.  | &



#### 1.2 String 字符串

###### 1.2.1 特性
+ String 加上任何东西都会变成 string
Example:
```
<script>
    console.log(typeof('123'));
    console.log(typeof('123'+1));
    console.log(typeof('123'+undefined));
</script>
```
+ 使用除了 + 以外的符号，就会默认为 number
+ 当把 string 变为 number 却算不出来数值的话就会显示 nan = not a number
Example:
```
<script>
    console.log(typeof('123')); //String
    console.log(typeof('123' + 1)); //String
    console.log(typeof('123' + undefined)); //String

    console.log(typeof('123' - 1)); //Number
    console.log(typeof('123' * 1)); //Number
    console.log(typeof('123' / 1)); //Number
    console.log(typeof('123' / undefined)); //Number

    console.log('123' - 1); //122
    console.log('123' * 1); //123
    console.log('123' / 1); //123
    console.log('123' / undefined); // NaN
</script>

###### 1.2.2 下标
+ 可以在 string 里使用下标 -> string[位置]
+ 当位置超出了范围就会等于 undefined
Example:
```
<script>
    console.log('abc'[0]);  // 0 代表第一位
    console.log('abc'[3]);  // undefined
</script>
```

###### 1.2.3 剪切 substring 
+ 字符串剪切
+ 方法1: substring()
+ substring(参数1，参数2)
> + 参数1 - 从第几位开始剪，有包含自己
> + 参数2 - 剪刀第几位，不包含自己
+ substring(参数1)
> + 从参数1剪到最后
Example:
```
<script>
    console.log('abcde'.substring(1,3));  // bc
    console.log('abcde'.substring(3));  // de
</script>
```

+ 方法2: charAt()
+ charAt(参数)
Example:
```
<script>
    console.log('abcde'.charAt(1)); // b
</script>
```

###### 1.2.4 大小写的变换
+ 大写: toUpperCase()
+ 小写: toLowerCase()
Example:
```
<script>
    console.log('abc'.toUpperCase()); // ABC
    console.log('ABC'.toLowerCase()); // abc
</script>
```

###### 1.2.4 字符串拼接 concat
+ concat(参数)
Example:
```
<script>
    console.log('abc'.
    concat('123'));

    console.log('abc'.
    concat('123').
    concat('abc'));
</script>
```

###### 1.2.5 字符串替换 replace
+ replace(参数1,参数2)
+ 参数1 - 要被替换的内容
+ 参数2 - 是替换的内容
+ 只能换一次，当有两个相同的，就会选择最前面的一个
Example:
```
<script>
    console.log('abcdef'.replace('b','x')); // axcdef
    
    console.log('abbbbb'.replace('b','x')); // axbbbb
<script>
```

###### 1.2.6 字符串查找 indexOf
+ 查找内容
+ indexOf(参数)
+ 会显示参数的位置
+ 如果没有此参数，就会返回 -1
Example:
```
<script>
    console.log('abcdef'.indexOf('c')); // 2
    console.log('abcdef'.indexOf('ab'));  // 0
    console.log('abbbbb'.indexOf('x')); // -1
<script>
```

###### 1.2.7 测试
+ abcdefg
+ 把 abcd 变成大写
+ 把 e 删了
Example：
```
<script>
    var a = 'abcdefg';
    var first = a.substring(0,4).toUpperCase();
    var last = a.substring(4).replace('e','');

    console.log(first.concat(last));
<script>
```


#### 1.3 Boolean 布尔值
+ true 等于 1, false 等于 0
Example:
```
<script>
    console.log(true + 0);    // 1
    console.log(false + 0);   // 0
    console.log(true + true); // 2
</script>
```

#### 1.4 Undefined and Null 未定义与空
+ 函数有默认的返回值，就是undefined
+ 有东西，但是没定义，也是undefined
+ undefined 相等于 null 是对的
Example:
```
<script>
    console.log(undefined == null); // true
</script>
```
+ null 是从内存里面给清空了
Example：
```
<script>
    var a = 10;
    a = null;
    console.log(a); // null
</script>
```

#### 1.5 Object 对象
+ 对象:
> + Array 数组
> + Json 对象
> + function 对象
> + Number
> + String
> + Boolean
> + 还有很多






