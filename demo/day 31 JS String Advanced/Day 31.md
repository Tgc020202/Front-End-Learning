## JavaScript - 字符串的进阶

#### anchor - <a>
+ 字符串 anchor() 用来创建 HTML 锚
+ 可以使用该方法生成 a 标签
+ 不过该 a 标签只能通过参数设定 name 属性，其他的属性无法设定
+ '值'.anchor('名字');

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        console.log(''.anchor());   // name = undefined

        console.log('abc'.anchor());   // name = undefined , value = abc

        console.log('abc'.anchor('111'));   // name = 111 , value = abc

        console.log('abc'.anchor('111','222'));   // name = 111 , value = abc

        // 添加 anchor 去 body 标签
        document.body.innerHTML = ''.anchor('youtube');
        
        // 可以设置网址 - href
        document.getElementsByName('youtube')[0].href = 'https://www.youtube.com/';
        // 显示点击的字 - innerHTML
        document.getElementsByName('youtube')[0].innerHTML = '链接';

    </script>
</body>
```


#### at
+ 字符串 at() 方法为字符串的索引方法(ES6新增的内容)
+ 该方法与传统的直接索引很像，不过其参数支持反向索引
+ 索引不到的内容，返回 undefined
+ '字符串'.at(位置);
> + 位置正数: 0 从左边开始
> + 位置为负数: -1 从右边开始
> + 位置超出正或负的范围: undefined


Example:
```
<body>
    <!-- JavaScript -->
    <script>
        // 普通的索引
        console.log('abcde'[3]);    // d
        console.log('abcde'[10]);    // undefined

        // 使用 at
        console.log('abcde'.at(3)); // d
        console.log('abcde'.at(10)); // undefined
        // 支持反向索引
        console.log('abcde'.at(-1)); // e

    </script>
</body>
```


#### big 
+ 字符串 big() 方法用于创建 big 标签
+ 作用: 把字符串显示为大号字体
+ big 参数无法与标签互动
+ 其内容为字符串内容，其他属性无法指定
+ '字符串'.big();

Example:
```
<body>
    
    <!-- 拿 div 做对比 -->
    <!-- <div>我是 div</div> -->

    <!-- b 标签 -->
    <!-- <b>我是 b，我的字变粗了</b> -->

    <!-- big 标签 -->
    <!-- <big>我是 big，我的字变大了</big> -->

    <!-- big + b 标签 -->
    <!-- <big><b>我是 big + b，我的字变大又变粗了</b></big> -->


    <div id="tgc">
        tgc love small small
    </div>

    <!-- JavaScript -->
    <script>
        // console.log('123'.big('aaaaa'));    // 后面的参数没有影响

        // 变大
        tgc.innerHTML = tgc.innerHTML.big();    // 可自行注释，看差别
    </script>
</body>
```


#### blink
+ 字符串 blink() 方法用于创建 blink 标签
+ 但是 blink 标签不是标准元素
+ 作用: 使其内容不断闪烁
+ 大多数的浏览器已不支持，旧版的火狐(FireFox 3.6.4)支持
+ '字符串'.blink();

Example:
```
<body>
    
    <blink>abc</blink>
    
    <!-- JavaScript -->
    <script>
        console.log('abc'.blink('123'));    // 后面的参数没有作用
        document.body.innerHTML = 'tgc'.blink();    // 在谷歌里没有闪烁的作用，只有生成内容的功能而已
    </script>
</body>
```


#### bold
+ 字符串 bold() 方法返回包含在 b 标签里的字符串副本
+ bold() 方法没有参数
+ 不会更改原始字符串的值
+ '字符串'.bold();

Example:
```
<body>
    <!-- div -->
    <!-- <div>我是 div 标签</div> -->

    <!-- b -->
    <!-- <b>我是 b 标签</b> -->

    <div id="tgc">
        我是 tgc
    </div>
    
    <!-- JavaScript -->
    <script>
        // console.log('abc'.bold());  // 后面的参数没有作用

        // tgc.innerHTML =  tgc.innerHTML.bold();

        
        // 把 tgc 里的 t 变粗体而已
        // innerHTML 里包含了空格和隔层，\n\t
        // innerText 可以只提取字体
        tgc.innerHTML =  tgc.innerText.at(0).bold() + tgc.innerText.substring(1);
    </script>
</body>
```
> + innerHTML 里包含了空格和隔层，比如 \n, \t
> + innerText 只提取字体
> + substring(从第几个位置开始)


#### charAt
+ charAt() 方法可返回指定位置的字符
+ 第一个字符位置为 0
+ 找不到内容，返回空值
+ 字符串.charAt(位置);

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        var a ='abcde';
        console.log(a.charAt(1));   // b
        console.log(a.charAt(10));  // 空值，至少有值
        console.log(a[10]);  // undefined
    </script>
</body>
```


#### charCodeAt
+ charCodeAt() 方法可返回指定位置的字符的 Unicode 的 10 进制编码
+ 这个的返回值是 0 - 65535 之间的整数
+ 字符串第一个字符的下标是 0
> + 如果是负数或大于等于字符串的长度，返回 NaN
+ '字符串'.charCodeAt(位置);
> + 位置一开始默认为 0

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        console.log('城'.charCodeAt());

        console.log('abc'.charCodeAt());    //   默认下标是 0
        console.log('abc'.charCodeAt(0));
        console.log('abc'.charCodeAt(1));
        console.log('abc'.charCodeAt(2));
        console.log('abc'.charCodeAt(10));  // NaN

        // 转为 16 进制
        console.log('abc'.charCodeAt(2).toString(16));

        // 转为 2 进制
        console.log('abc'.charCodeAt(2).toString(2));
    </script>
</body>
```
> + charCodeAt(默认值为 0)
> + toString 可更改不同的进制算法


#### codePointAt
+ 字符串的长度是由码元组成的
+ 多个码元可以组成一个码点
+ charCodeAt 是以码元为一个索引，codePointAt 是以一个码点为一个索引，进行处理
+ '字符串'.codePointAt();

Example:
```
<body>
    <!-- JavaScript -->
    <script>

        console.log('a'.length);    // 一个码元，例子 1000

        // 🥺
        // 😈
        // 🐼

        console.log('✔'.length);   // 两个码元，例子1000 1000
        console.log('😈'.length);
        console.log('🐼'.length);

        console.log('a'.charCodeAt(0));

        console.log('🐼'.charCodeAt());     // 只检测第一个码元
        console.log('🐼'.codePointAt());    // 检测两个码元
        
        // 检测过长
        console.log('🐼'.charCodeAt(10));     // NaN
        console.log('🐼'.codePointAt(10));    // undefined
    </script>
</body>
```


#### concat
+ concat() 方法用于连接两个或多个字符串
+ 该方法没有改变原有的字符串
+ 但是会返回连接两个或多个字符串
+ '字符串'.concat('其他字符串');

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        var a = 'tgc';
        // + 相等于字符串的拼接，不是方法
        console.log(a + ' hello');

        // concat 相等于字符串的拼接的方法
        console.log(a.concat());
        console.log(a.concat(' hello'));

        // 原字符串不受影响
        console.log(a);
    </script>
</body>
```


#### endsWith
+ endsWith() 方法用来判断当前的字符串是否是以另一个给定的子字符串 “结尾”的
+ 并返回 true 或 false
+ 第二个参数可选，作为 str 的长度，通常默认为 str.length
+ '字符串'.endsWith('字符',检测的长度);

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        console.log('abcd'.endsWith('d'));  // true
        console.log('abcd'.endsWith('e'));  // false

        // 只看 1 位，平时默认为字符串的长度
        console.log('abcd'.endsWith('a',1));    // true

        // 不指定判断任何字符，就会默认判断 字符串种类
        console.log('abcd'.endsWith(''));   // true
        console.log('abcd'.endsWith(' '));   // true

    </script>
</body>
```






























