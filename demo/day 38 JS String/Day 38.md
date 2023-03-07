## JavaScript - String 字符串数据格式
+ 字面量 - ```var a = '123';```
+ 对象的形式 - ```var b = new String('123');```

#### charAt
+ 返回字符串的第几位

Example:
```
<script>
    var a = 'abcdefgh';
    console.log(a.charAt(1));   // b
</script>
```


#### indexOf
+ 找字符串要找的位置
+ 如果有找到就返回该字符串的当前位置
+ 如果没有找到就返回 -1

Example:
```
<script>
    console.log(a.indexOf('g'));   // 6
    console.log(a.indexOf('fg'));   // 5
    console.log(a.indexOf('z'));   // -1
</script>
```

+ indexOf 里面可以放两个参数
+ indexOf('要查找的字',从第几个字开始找)

Example:
```
<script>
    var b = 'mathematics';
    console.log(b.indexOf('m',1));  // 5
</script>
```


#### lastIndexOf
+ 找字符串要找的位置，但是这个是从后方开始搜索
+ lastIndexOf 里面可以放两个参数
+ lastIndexOf('要查找的字',限制查找的长度)

Example:
```
<script>
    var b = 'mathematics';
    console.log(b.lastIndexOf('m'));  // 5

    console.log(b.lastIndexOf('m',2));  // 0
</script>
```


#### substring
+ 字符串截取
+ 第一个参数时开始
+ 第二个参数是结束
> + substring(开始,结束)
+ 一个参数也可以，代表从设置的位置到结束
> + substring(设置)
+ 支持反向截取

Example:
```
<script>

    var a = 'superman';

    console.log(a.substring(3));    // erman
    console.log(a.substring(0,3));  // sup

    console.log(a.substring(0,5));  // super
    console.log(a.substring(5,0));  // super

</script>
```

#### slice
+ 跟 substring 大同小异，但是它不支持反向截取

Example:
```
<script>

    var a = 'superman';
    console.log(a.slice(3));  // erman
    console.log(a.slice(0,3));  // sup

    console.log(a.slice(0,5));  // super
    console.log(a.slice(5,0));  // 没有返回
</script>
```

#### substr
+ 字符串截取
+ 第一个参数为开始
+ 第二个参数为从第一个参数往后走几位
+ 一个参数也可以，代表从设置的位置到结束

Example:
```
<script>

    var a = 'superman';

    console.log(a.substring(3));    // erman
    console.log(a.substring(0,3));  // sup

    console.log(a.substring(0,5));  // super
    console.log(a.substring(5,0));  // super

</script>
```

#### concat
+ 拼接字符串

Example:
```
<script>

    var a = 'super';
    var b = 'man';

    console.log(a.concat(b));   // superman
</script>
```

#### split
+ 字符串转换成数组，给予字符来进行切割
+ split('分割的字符');

Example:
```
<script>

    var a = 'superman,batman,spiderman';

    console.log(a.split(','));  // arr = [superman, batman, spiderman]

</script>
```

#### toUpperCase()
+ 转为大写

Example:
```
<script>

    var a = 'superman';

    console.log(a.toUpperCase());   // SUPERMAN

    // 把第一个字母变大写
    var b = a.charAt(0).toUpperCase().concat(a.substring(1));
    console.log(b); // Superman
    
</script>
```

#### toLowerCase
+ 转为小写

Example:
```
<script>

    var a = 'SUPERMAN';

    console.log(a.toLowerCase());   // superman

    // 每相隔一个字母变小写
    var b = '';

    for(var i in a){
        if(i % 2 == 0){
            b += a.charAt(i).toLowerCase();
        }
        else{
            b += a.charAt(i);
        }
    } 
    console.log(b); // sUpErMaN
</script>
```

#### replace
+ 替换
+ 只会显示替换后的结果，的但实际上原本的字符串并没有被改变
+ 第一个参数，要替换的东西
+ 第二个参数，替换成什么东西
+ 只会更改最前面的要替换的字符当里面有很多一样的字符

Example:
```
<script>

    var a = 'superman';

    console.log(a.replace('man','woman'));  // superwoman

    var b = 'mathematics';
    console.log(b.replace('m','z'));    // zathematics
    
    var c = 'aaaaaaaaaaaaaaa';
    console.log(c.replace('a','b'));    // baaaaaaaaaaaaaa
</script>
```








