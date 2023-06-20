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

###### i
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

###### d - digit 转义
+ 把原本的意义给出转变了
+ 写法: 变量名.search(/\d/);
+ 所有的数字 0-9

Example:
```
<script>
    var a = 'abcgiloVeyoug520haha';

    alert(a.search(/\d/));   // 13
</script>
```

###### 集合 [数值]
+ 写法: 变量名.search(/[范围]/);
> + 范围可以是 0 到 9 之间的数字，或者是 a 到 z 之间的字母

Example:
```
<script>
    var a = 'abcgiloVeyoug520haha';

    alert(a.search(/[0-5]/));   // 13
    alert(a.search(/[0-3]/));   // 14

    alert(a.search(/[a-z]/));   // 0
</script>
```

+ 可以设置两个范围
+ 写法: 变量名.search(/[数字范围字母范围]/);

Example:
```
<script>
    var a = 'abcde123fghijkl';

    alert(a.search(/[0-5]/));   // 5
    alert(a.search(/[d-z0-9]/));   // 3
</script>
```
> + 开始搜索直到其中一个条件达成，就会直接打印出当前结果

###### match
+ 它会以数组的方式返回符合它条件的数据
+ 写法: 变量名.match(/要查找的字符串/);

Example:
```
<script>
    var a = 'abcde123fghijkl';

    alert(a.match(/[0-5]/));    // 1
    alert(a.match(/[c-z]/i));   // c
</script>
```

###### g - group
+ 代表全部
+ 写法: 变量名.match(/要查找的字符串/g);

Example:
```
<script>
    var a = 'abcde123fghijkl';

    alert(a.match(/[0-5]/));    // 5
    alert(a.match(/[c-z]/g));   // c,d,e,f,g,h,i,j,k,l
</script>
```

###### 在正则中 {} 大括号
+ 限制正则条件的的长度
+ 写法: 变量名.match(/要查找的字符串{量词}/g);

Example:
```
<script>
    // 大括号
    var a = 'abcde123fghijkl';

    alert(a.match(/[0-5]/));    // 5
    alert(a.match(/[c-z]/g));   // c,d,e,f,g,h,i,j,k,l
    alert(a.match(/[c-z]{2}/g));   // cd,fg,hi,jk
</script>
```

+ 贪婪法制
> + 只要符合多个的量词，会优先匹配最多的
> + {量词1,量词2}
> > + 量词2 可以不写 {1,}，就会代表无限长度
> > + 量词2 永远大过量词1，否则会报错

Example:
```
<script>
    // 大括号
    var a = 'abcde123fghijkl';

    alert(a.match(/[0-5]/));    // 5
    alert(a.match(/[c-z]/g));   // c,d,e,f,g,h,i,j,k,l
    alert(a.match(/[c-z]{2}/g));   // cd,fg,hi,jk
    alert(a.match(/[c-z]{1,2}/g));   // cd,e,fg,hi,jk,l
    alert(a.match(/[c-z]{1,}/g));   // cde,fghijkl
    // alert(a.match(/[c-z]{3,1}/g));   // error
</script>
```

###### 快捷键
+ `+` 符号代表 {1,}
+ `?` 符号代表 {0,1}，如果不符合就会变为空
+ `*` 符号代表 {0,}，如果不符合就会变为空

Example:
```
<script>
    var a = 'abcde123fghijkl';

    alert(a.match(/[c-z]{1,}/g));   // cde,fghijkl
    alert(a.match(/[c-z]+/g));   // cde,fghijkl
    alert(a.match(/[c-z]?/g));   // ,,c,d,e,,,,f,g,h,i,j,k,l,
    alert(a.match(/[8-9]?/g));   // ,,,,,,,,,,,,,,,
    alert(a.match(/[c-z]*/g));   // ,,cde,,,,fghijkl,
    
</script>
```

+ 搭配 d 

Example:
```
<script>
    var a = 'abc123def12ghi2';

    // d 找出数字
    // + {1,}
    // g 打印全部
    alert(a.match(/\d+/g));   // 123,12,2
</script>
```

###### w - word
+ 相当于 [a-zA-Z0-9_]
+ 所有的东西都会变为 word，但是一些特殊符号是不会有反应的

Example:
```
<script>
    var a = 'abc123DEf_12ghi2';

    // w {a-zA-Z0-9_}
    // + {1,}
    // g 打印全部
    alert(a.match(/\w+/g));   // abc123DEf_12ghi2

    // 特殊符号
    var a = 'abc%123DEf/_12*ghi2';
    alert(a.match(/\w+/g));   // abc,123DEf,_12,ghi2
</script>
```

###### `^` - caret 脱字符
+ 又被称为非或者是`不是`
+ 只有在正则里面叫非

Example:
```
<script>
    var a = 'abc123DEf_12ghi2';

    // ^ 非
    // [0-9] 0 到 9 之间的数字
    // + {1,}
    // g 全部
    alert(a.match(/[^0-9]+/g));   // abc,DEf_,ghi
</script>
```

###### replace 替换
+ 写法: 变量名.replace(/被代替/,替换成);

Example:
```
<script>
    var a = '作业一和作业二和作业三和作业四';

    alert(a.replace(/和/,''));  // 作业一作业二和作业三和作业四


    // replace 替换
    // g 全部
    alert(a.replace(/和/g,''));  // 作业一作业二作业三作业四
</script>
```

+ 将数字给替换了
> + 写法: 变量名.replace(/\d/,'');

Example:
```
<script>
    var a = 'abcd123efgh34ij';

    // replace 替换
    // d 数字
    // g 全部
    alert(a.replace(/\d/g,''));  // abcdefghij
</script>
```

+ 也可替换为函数

Example:
```
<script>
    var a = 'abcd123efgh34ij';

    // replace 替换
    // d 数字
    // g 全部
    alert(a.replace(/\d/g,function(i){
        // alert(i);
    }));

    // 替换成 [变]
    alert(a.replace(/\d/g,function(i){
        return ('变');  // abcd变变变efgh变变ij
    }));
</script>
```

###### 在正则里的 | 符号
+ 代表或

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>禁语</title>
</head>
<body>
    我帅
    我好呆
    我好可爱
    我是大傻逼
    我最漂亮

    <!-- JavaScript -->
    <script>
        var a = document.body.innerHTML;
        document.body.innerHTML = a.replace(/漂亮|帅|逼/g,function(x){
            var m = '';
            for(var i = 0 ; i < x.length ; i++){
                m += '*';
            }
            return m;
        });
    </script>
</body>
</html>
```

###### 在正则里的 . 符号
+ 代表所有

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>让所有字变成有颜色</title>
</head>
<body>
    <div id="div1">今天是5月1日劳动日，但是我还要上课!!!今天是5月1日劳动日，但是我还要上课!!!今天是5月1日劳动日，但是我还要上课!!!
    </div>

    <!-- JavaScript -->
    <script>
        var val = div1.innerHTML;

        // 找出全部
        // alert(val.match(/./g));

        div1.innerHTML = val.replace(/./g,function(x){
            return '<span style="color:rgb('+ parseInt(Math.random() * 256) + ',' + parseInt(Math.random() * 256) + ',' + parseInt(Math.random() * 256) + '")>'+ x +'</span>';
        })
    </script>
</body>
</html>
```

#### test 匹配
+ 

Example:
```
<script>
    // test 匹配
    var password = 'a-abc:8';
    var detect = /[a-z]{1}-{1}[a-z]{3}:{1}\d{1}/g;

    alert(detect.test(password));   // true
</script>
```

##### 特别的符号
> + 需要添加 `\`符号
> + 例子: `.`符号 -> `\.`

Example:
```
<script>
    // 特别的符号的匹配 要添加 \
    var password = 'a.abc*8';
    var detect = /[a-z]{1}\.{1}[a-z]{3}\*{1}\d{1}/g;

    alert(detect.test(password));   // true
</script>
```

##### 搭配 ^ 做匹配
+ 头部
+ 会从头部进行判断匹配，如果头部正确，就会直接返回正确

Example:
```
<script>
    // 复杂化匹配
    var account1 = 'abc123...abc123';
    var account2 = 'abc...abc123';
    var account3 = 'abc...abc';
    
    var detect = /[a-z]+\d+/g;

    // 会检测最前端和最后端，只要有一方是符合条件的就会返回正确
    console.log(detect.test(account1));   // true
    console.log(detect.test(account2));   // true
    console.log(detect.test(account3));   // false
</script>

<script>
    // 复杂化匹配，加上 ^ 符号
    var account1 = 'abc123...abc123';
    var account2 = 'abc...abc123';
    var account3 = 'abc...abc';
    var account4 = 'abc123...abc';
    
    // 加上 ^ 符号
    var detect = /^[a-z]+\d+/g;

    // 会从头部检测，如果头部正确，就会直接返回正确
    console.log(detect.test(account1));   // true
    console.log(detect.test(account2));   // false
    console.log(detect.test(account3));   // false
    console.log(detect.test(account4));   // true
</script>
```

##### 搭配 $ 做匹配
+ 尾部
+ 会从尾部进行判断匹配，如果尾部正确，就会直接返回正确

Example(Progress):
```
<script>
    // 复杂化匹配，加上 $ 符号
    var account1 = 'abc123...abc123';
    var account2 = 'abc...abc123';
    var account3 = 'abc...abc';
    var account4 = 'abc123...abc';
    
    // 加上 $ 符号
    var detect = /[a-z]+\d+$/g;

    // 会从尾部检测，如果尾部正确，就会直接返回正确
    console.log(detect.test(account1));   // true
    console.log(detect.test(account2));   // true
    console.log(detect.test(account3));   // false
    console.log(detect.test(account4));   // false
</script>
```

###### 在正则中 () 括号
+ 括号相当于大集合

Example:
```
<script>
    var a = 'a1b2c3d4';
    var re = /([a-z]{1}\d{1}){2}/g;
    alert(re.test(a));  // true


    var re2 = /([a-z]{1}\d{1}){1,3}/g;
    alert(a.match(re2));  // a1b2c3,d4
</script>
```

###### s - space
+ 空格

Example:
```
<script>
    var a = 'tgc tgc';
    var b = '';
    var c = '  ';

    alert(/^\s/g.test(a));    // false，前面有空
    alert(/^[^\s]/g.test(a));    // true，前面不能有空
    alert(/[^\s]/g.test(a));    // true，不是空

    alert(/[^\s]/g.test(b));    // false，不是空
    alert(/[^\s]/g.test(c));    // false，不是空
</script>
```
> + 切记 `/[^\s]/g.test(a)` 检测的是字符串里边是否存在不是空格的元素，一旦发现存在不是空格的元素，就会直接返回正确，并不是检测字符串里边是否有空格元素。

###### 所有中文的集合
+ [\u4e00-\u9fa5]
+ 写法: /[\u4e00-\u9fa5]+/g;

Example:
```
<script>
    var a = '123123213213';
    var b = '一二三';

    var re = /[\u4e00-\u9fa5]+/g;

    alert(re.test(a));  // false
    alert(re.test(b));  // true
</script>
```






















