## JavaScript - 函数

#### 函数的参数 parameter
+ function 函数名(参数){}
+ 参数可以有很多个，可以没有，也可以任何数据类型
+ 函数可能是死的，有了参数之后就有了活力，然后函数就活了

###### 无参数
Example:
```
<script>
  function a(){
    console.log('small small');
  }
  a();
</script>
```
> + 很普通，没有任何操作或改变

###### 一个参数
Example:
``` 
<script>
  function b(text){
    console.log(text);
  }
  b(123);
</script>
```
> + 输入什么，就打印什么

###### 函数里面重新定义了参数
Example:
``` 
<script>
  function c(text2){
    var text = '呆呆';
    console.log(text);
  }
  c(123);
</script>
```
> + 函数里定义的参数，才会被选择
> + 因为外面的参数会被，函数里的参数刷新

###### 调用的时候没有定义参数
Example:
``` 
<script>
  function d(text){
    console.log(text);  // undefined
  }
  d();
</script>
```
> + 没有定义参数的话就同等于创建变量，却没有赋予任何值，undefined

###### 多个参数
Example:
``` 
<script>
  function e(node,text,color,width,height){
    var oNode = document.createElement(node);
    oNode.innerHTML = text;
    oNode.style.background = color;
    oNode.style.width = width;
    oNode.style.height = height;
    document.body.appendChild(oNode);
  }
  e('div','我是 div','red','100px','100px');
  e('span','我是 span','green','200px','200px');
</script>
```
> + 可以同时拥有很多参数

###### 用数组 array 当参数
Example:
``` 
<script>
  function f(arr){
    var oNode = document.createElement(arr[0]);
    oNode.innerHTML = arr[1];
    oNode.style.background = arr[2];
    oNode.style.width = arr[3];
    oNode.style.height = arr[4];
    document.body.appendChild(oNode);
  }
  f(['div','我是一个数组','yellow','300px','300px']);
</script>
```
> + 可以使用数组的方式，但是切记调用的时候，参数一定要是数组


#### 函数的不定参 arguments
+ arguments 对象不是一个数组(array)
+ 类似数组，但除了 length 属性和索引元素外，没有任何 数组的属性
+ 创建函数时，没有放入参数，就会自动默认为不定参

1. 证明:
+ 创建函数时，没有放入参数 parameter，就会自动默认为不定参 arguments
+ 可以使用下标从 arguments 中取值，如果没值，等于 undefined
+ 接受任何数据种类的混合使用

Example:
```
<!-- JavaScript -->
<script>
  // 任何函数里都有 arguments
  // 当没有放入参数在创建函数，就会自动默认为 arguments
  function a(){
    console.log(arguments);

    // 使用下标从 arguments 中取值，如果没有值，就会显示 undefined
    console.log(arguments[0]);

    console.log(arguments[3]);
  }
  // 接受任何数据种类的混合使用
  a('1',2,3);
</script>
```

2. 证明:
+ 数组与不定参 是两个不同的东西
+ 不定参不能使用数组的功能
+ 在不定参的函数里调用数组，数组在函数来就会没有功能

Example:
```
<script>
  // 数组的功能 - push
  var arr = [1,2,3];
  arr.push(10);

  console.log(arr);

  function b(){
    // 无法使用数组的功能，比如 push
    // arguments.push(10);  // 会出 bug
    console.log(arguments[2]);
  }
  // 将创建的数组放入 b 函数里进行调用
  b(arr); // undefined
  
</script>
```

3. 证明:
+ 当调用函数用的不定参的数量不足于函数里运行的不定参，就会默认为 undefined
+ 不会导致系统发生故障

Example:
```
<script>
  function c(){
    var oNode = document.createElement(arguments[0]);
    oNode.innerHTML = arguments[1];
    oNode.style.background = arguments[2];
    oNode.style.width = arguments[3];
    oNode.style.height = arguments[4];
    document.body.appendChild(oNode);
  }
  c('div','我现在用的是 arguments','red','500px','300px');
  
  // 当调用函数用的不定参的数量不足于函数里运行的不定参，就会默认为 undefined
  // 不会导致系统发生故障
  c('span','我现在用的是 arguments','green');
</script>
```


#### 函数 - 递归 recursion
+ 递归是函数自己间接调用自己的使用方式

1. 使用递归需要有限制或者给系统缓冲的时间，否则会显示 error
Example:
```
<script>
  // 如果没有限制或者缓冲，就会显示 error
  function a(){
    a();
  }
  a();
</script>
```

2. 递归搭配 setTimeout，给予系统缓冲的时间

Example：
```
<script>
  // 使用 setTimeout 给系统缓冲的时间，就没问题了
  var i = 0;
  function b(){
    i++;
    console.log(i);
    setTimeout(b,10); // 每 10 毫秒调用一次 b 函数
  }
  b();
</script>
```

3. 递归与数组的搭配

 Example:
 ```
<script>
  // 使用数组制作递归
  var arr = [1,2,3] , 
  i = 0;

  function c(){
    if(i == arr.length){
      return; // return 代表元素的返回
    }
    console.log(arr[i]);
    i++;
    c();
  }
  c();
</script>
```

4. 递归与两个函数的互相调用

Example:
```
<script>
  // 使用递归互相调用彼此
  function d(){
    document.body.style.background = 'red';
    setTimeout(e,100);
  }
  function e(){
    document.body.style.background = 'yellow';
    setTimeout(d,100);
  }
  d();
</script>
```

5. 递归与条件语句的搭配

Example:
```
<script>
  // 递归搭配条件语句
  var i = 0;
  function f(){
    if(i % 2 == 1){
      document.body.style.background = 'red';
    }
    else{
      document.body.style.background = 'yellow';
    }
    i++;
    setTimeout(f,100); 
  }
  f();
</script>
```


#### 函数 - 返回 return
+ return 语句会终止函数的执行，并返回函数的值

1. 没有设置任何的行动，就会 return undefined

Example:
```
<script>
  // 如果没有设置任何的行动，就会 return undefined
  function a(){}
  console.log(a());   // undefined
</script>
```

2. return 可以返回任何想要返回的值

Example:
```
<script>
  function b(){
    return 10;
  }
  console.log(b());   // 10
</script>
```

3. 一旦执行 return，就不往后执行了

Example:
```
<script>
  function c(){
    return '呆呆';
    console.log('哇哈哈');
  }
  console.log(c());   // 呆呆
</script>
```

4. 可用于递归终止的条件语句

Example:
```
<script>
  // 可用于递归终止的条件语句
  var i = 0;
  function d(){
    if(i < 3){
      console.log(i)
    }
    else{
      return ;
    }
    i++;
    d();
  }
  d();
</script>
```

5. 使用变量操作

Example:
```
<script>
  function e(){
    return alert(1);
  }
  var f = e();
  console.log(f); // undefined，因为 alert 不属于值
</script>
```


#### 函数 - 封装
+ 封装一个选项卡，并且传递参数

###### 选项卡

Example:
+ [封装的例子](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2029%20JS%20Function/6_testImplemented.html)


## 小插曲 - 浏览器的技术应用

#### 提取网页图片
+ 打开网页，打开控制面板
+ 点击查找 application > frames > top > images ; 可以拿出此网页的所有图片

![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2029%20JS%20Function%20%26%20Web%20function/p1.PNG)


#### 提取网页音乐
+ 用于示范的网址：
```
https://www.joox.com/my-en/album/JybIwUl8ew9kHPUgxxXp3g==
```
+ 接着打开控制页面(inspect)
+ network > media > 找音乐的文件夹; 就可以安装了


#### 提取网页视频(to be continue)
+ 用于示范的网址：
```
https://www.youtube.com/watch?v=VfZuvrEDcWI&list=RDMMVFe8u5BR7Wk&index=3
```
+ 接着打开控制页面(inspect)
+ element > ctrl + f  > 输入 video 标签 > 找音乐的文件夹; 就可以安装了







