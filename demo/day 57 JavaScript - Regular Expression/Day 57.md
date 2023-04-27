## JavaScript

### Regular Expression 正则表达书
+ 只能对字符串进行操作 
+ 只有 string 类型可以
+ 正则表达式的声明方式: 
> 1. var 变量名 = new RegExp("字符串");

#### Search 查找
+ 正则查找位置的方法
+ 变量名.search(/要查找的字符串/);
+ 返回的值是以 0 为开始

Example:
```
<script>
    var a = 'tgc is me';

    // 查找
    alert(a.search(/e/));   // 8
</script>
```

Example:
```
<script>
    var a = 'tgc is me';
    var b = new RegExp('e');
    
    alert(a.search(b)); // 8
</script>
```

+ 查找不到的话会返回 -1

Example：
```
<script>
    var a = 'tgc is me';
    alert(a.search(/x/));   // -1
</script>
```

+ 放置 i 在后方，可以使其不区分大小写，来进行搜寻
+ 写法: 变量名.search(/要查找的字符串/i);

Example:
```
<script>
    // 不区分大小写
    var a = 'TGC IS ME';
    alert(a.search(/e/));   // -1

    // 放置 i 在后方，使其不区分大小写
    alert(a.search(/e/i));   // 8
</script>
```

Example:
```
<script>
    var a = 'abcgiloVeyoughaha';
    var b = new RegExp('love','i');

    alert(a.search(b));   // 5
</script>
```













