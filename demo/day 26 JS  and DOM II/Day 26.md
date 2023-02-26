## JavaScript & DOM(Document Object Model)

#### 选取父级 parentNode
+ .parentNode
+ 用来选取父级，并进行一些操作
+ 父亲是唯一的，所以一个子级只可以锁定一个父级

Example:
```
<body>
    <div>
        <div id="div1"></div>
    </div>

    <!-- JavaScript -->
    <script>
        // console.log(div1);
        div1.style.width = '100px';
        div1.style.height = '100px';
        div1.style.background = 'red';

        // 选取父级 -> 选取外层
        div1.parentNode.style.width = '200px';
        div1.parentNode.style.height = '200px';
        div1.parentNode.style.background = 'yellow';

        // 选取 div1 的父级的父级
        div1.parentNode.parentNode.style.width = '300px';
        div1.parentNode.parentNode.style.height = '300px';
        div1.parentNode.parentNode.style.background = 'green';

    </script>

</body>
```
> + div1 的父级是 普通 div 标签
> + div1 的父级的父级是 body 标签


#### 选取子级 children
+ .children
+ 用来选择子级，并进行一些操作
+ 一个父级可以有很多的子级

Example(选取子级的例子):
```
<body>
    <div id="parentDiv">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </div>

    <!-- JavaScript -->
    <script>
        // console.log(parentDiv.children);    // 可检测到有多少个子

        /*
        // 选取子级，可以添加属性给子级
        parentDiv.children[0].style.width = '100px';
        parentDiv.children[0].style.height = '100px';
        parentDiv.children[0].style.background = 'red';

        // 可以跳过其他子级使用，比如跳过 1 直接选择 2
        parentDiv.children[2].style.width = '200px';
        parentDiv.children[2].style.height = '200px';
        parentDiv.children[2].style.background = 'yellow';

        */
        
        // 可以使用循环给予属性
        for(var i = 0;i < parentDiv.children.length;i ++){
            parentDiv.children[i].style.width = '200px';
            parentDiv.children[i].style.height = '200px';
            parentDiv.children[i].style.background = 'green';
        }

    </script>
</body>
```
> + parentDiv 的子级是一群 div 标签
> + 我们可以通过下标选取特定的子级，比如 parentDiv.children[0]

Example(选取子级的子级的例子):
```
<body>
    <div id="parentDiv">
        <div>
            <span></span>
            <span></span>
            <p></p>
        </div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </div>

    <!-- JavaScript -->
    <script>
        // 选取子级的子级
        console.log(parentDiv.children[0].children);

        // 精准的选择 子级的子级
        console.log(parentDiv.children[0].children[2]);

    </script>
</body>
```
> + 可以通过下标更精准的选取子级的子级

#### 生成元素 createElement
+ document.createElement('想要创建的元素');

#### 尾部插入元素 appendChild
+ document.要被插入的父元素.appendChild(想要插入的子元素);
+ 只会插入子级的最后方

#### 返回或设置元素内容 innerHTML
+ 可以查看里面的内容

Example:
```
<body>
    <div id="div1">
        <span></span>
        <p></p>
        <div></div>
    </div>

    <!-- JavaScript -->
    <script>
        // 可以查看里面的内容
        console.log(div1.innerHTML);
    </script>
</body>
```

+ 可以改写内容

Example:
```
<body>
    <div id="div1">
        <span></span>
        <p></p>
        <div></div>
    </div>

    <!-- JavaScript -->
    <script>
        div1.innerHTML = '<span>123</span>'
        
        console.log(div1.innerHTML);
    </script>
</body>
```
> + 父级.innerHTML = '想要改写的内容';

+ innerHTML 返回元素里面的内容，如果赋值了，就是先清空里面的内容，再加上新的内容

Example:
```
<body>
    <div id="div1">
        <span></span>
        <p></p>
        <div id="div2">2</div>
    </div>

    <!-- JavaScript -->
    <script>
        div2.onclick = function(){
            alert(123);
        }

        // 赋值了以后 div2.onclick 就没有用处了
        div1.innerHTML = div1.innerHTML + '<span>123</span>';
    </script>
</body>
```

#### 混合运用 (createElement, innerHTML, appendChild)

Example(createElement, innerHTML, appendChild 混合应用):
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>混合应用</title>
    <style>
        div{
            width: 100px;height: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <!-- 按钮 -->
    <input type="button" value="小按钮" name="" id="ipt">

    <!-- 父级 = 给子级存在的位置 -->
    <div id="outNode"></div>

    <!-- JavaScript -->
    <script>
        /*
        var oInput = document.createElement('input');

        console.log(oInput);

        // 插入元素到子级的最后方
        document.body.appendChild(oInput);
        */


        var i = 0;
        // 当点击小按钮就会生成 div
        ipt.onclick = function(){
            // 生成元素
            var oDiv = document.createElement('div');
            // 编改内容
            oDiv.innerHTML = i;
            // 插入元素到最后方
            outNode.appendChild(oDiv);
            i++;
        }

    </script>
</body>
```
> + 点击按钮就会生成一个新的红方块在之前的子级的后方


#### 指定位置插入元素 insertBefore
+ 父元素.insertBefore(要插入的元素的变量,要插入哪个元素的前面的名字);

Example:
```
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>InsertBefore 指定位置的插入</title>
    <style>
        *{padding: 0;margin: 0;}

        #div1{
            width: 100px;height: 100px;
            background-color: red;
            float: left;
        }
        #div2{
            width: 200px;height: 200px;
            background-color: yellow;
            float: left;
        }
        #div3{
            width: 300px;height: 300px;
            background-color: green;
            float: left;
        }

    </style>
</head>
<body>
    <div id="outNode">
        <div id="div1"></div>
        <div id="div2"></div>
    </div>

    <!-- JavaScript -->
    <script>
        var oDiv = document.createElement('div');
        // 给予 id
        oDiv.id = 'div3';
    
        // 插入到 div2 的前面
        outNode.insertBefore(oDiv,div2);

    </script>
</body>
```
> + div3(绿色方形)插入红色和黄色方形之间
> + outNode.insertBefore(oDiv,div2); -> div2 变成在 oDiv(div3) 的后面了


#### 修改元素 replaceChild
+ 父级.replaceChild(要替换的元素,被替换的元素);

Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
    </div>

    <!-- JavaScript -->
    <script>
        // 把 outNode 里的 span 标签变为 input 标签
        var oInp = document.createElement('input');
        // outNode.replaceChild(oInp,outNode.children[0]);

        // 更清晰
        onclick = function(){
            outNode.replaceChild(oInp,outNode.children[0]);
        }
    </script>
</body>
```
> + 一点击屏幕，1111 就变成 input 了
> + 如果要换成其他的标签，只需要在生成元素更改想要生成的元素就行了
> > + document.createElement('p');  -> 生成 p 标签


#### 删除子级元素 removeChild
+ 只能删除子级第一层罢了

Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
        <span>22222</span>
        <span id="oSpan">33333</span>
    </div>

    
    <!-- JavaScript -->
    <script>
        allSpan = document.getElementsByTagName('span');
        console.log(allSpan);

        // 下面这个 for 循环会出 bug
        // 因为一旦第一个子元素被删，下一个子元素会顶替第一个元素的位置
        /*
        for(var i = 0;i < 2;i ++){
            outNode.removeChild(allSpan[i]);
        }
        */

        // 解决方法
        for(var i = 0;i < 2;i ++){
            outNode.removeChild(allSpan[0]);    // 把 i 改为 0
        }
    </script>
</body>
```
> + 全部父级的第一层子级会依次被删除
> + outNode.removeChild(allSpan[0]);  -> 只设置为0
> > + 因为被当第一个元素被删除，第二个元素就会上来顶替第一个元素的位置

Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
        <span>22222</span>
        <span id="oSpan">33333</span>
    </div>

    
    <!-- JavaScript -->
    <script>
        // 不知道父级的情况下删了自己
        oSpan.parentNode.removeChild(oSpan);
    </script>
</body>
```
> + 可以通过调用自己的父级然后再用父级的 removeChild 将自己删了
> + 想删的元素的名.parentNode.removeChild(想删的元素的名);


#### 删除 remove
+ 删除所有

Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
        <span>22222</span>
        <span id="oSpan">33333</span>
    </div>

    
    <!-- JavaScript -->
    <script>
        allSpan = document.getElementsByTagName('span');
        console.log(allSpan);

        // outNode.remove(allSpan);    // 可以直接删完
        
    </script>
</body>
```
> + 直接删除父级里的所有这个标签
> + 变量 = document.getElementsByTagName('标签');
> + 父级.remove(标签的变量);


#### 删除自身元素

Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
        <span>22222</span>
        <span id="oSpan">33333</span>
    </div>

    
    <!-- JavaScript -->
    <script>
        // 直接删了有 id (oSpan) 的标签
        oSpan.remove();
    </script>
</body>
```
> + 在已知标签的 id 的情况下，直接删除
> + id.remove();


Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
        <span>22222</span>
        <span id="oSpan">33333</span>
    </div>

    
    <!-- JavaScript -->
    <script>
        outNode.children[0].remove();
    </script>
</body>
```
> + 在已知标签的所在位置的情况下，直接删除
> + 父级.children[位置的 index].remove();

Example:
```
<body>
    <div id="outNode">
        <span>11111</span>
        <span>22222</span>
        <span id="oSpan">33333</span>
    </div>

    
    <!-- JavaScript -->
    <script>
        // 删了父级，子级也会消失
        outNode.remove();
    </script>
</body>
```
> + 父级被删了，子级也会消失











