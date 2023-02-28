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
































