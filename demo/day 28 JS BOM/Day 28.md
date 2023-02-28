## JavaScript BOM(Browser Object Model)
+ JS 操作浏览器

###### 小插曲
+ object 数据格式

Example:
```
<script>
  var a = {
  app:'myapp'
  }

  console.log(a);
</script>
```

#### 正式进入 BOM
+ 控制浏览器
+ BOM 没有官方标准
+ 各个浏览器都有各自的实现标准，属于会有兼容问题

##### 1.0 Location 地址
+ 可以查看地址 url 信息
+ Location
![p5](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2028%20JS%20BOM/p5.PNG)

###### 1.1 href
+ 返回或者设置 url 地址
+ 搜寻地址: location.href;
![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2028%20JS%20BOM/p1.PNG)

+ 设置地址: location.href = '地址';

Example:
```
<body>

    <div id="div1">go</div>

    <!-- JavaScript -->
    <script>
        // console.log(location);

        // 返回页面的地址 - href
        console.log(location.href);
        
        // href 设置地址
        div1.onclick = function(){
            location.href = 'https://www.youtube.com/';
        }
    </script>
</body>
```

###### 1.2 Reload page 刷新页面
+ 直接刷新页面
+ location.reload();

Example:
```
<body>

    <div id="div1">go</div>

    <!-- JavaScript -->
    <script>
        // 刷新页面 reload
        div1.onclick = function(){
            location.reload();
        }
    </script>
</body>
```

##### 2.0 History 历史
+ 对象包含用户访问过的 url

###### 2.1 back
+ 返回上一个页面
+ history.back();

###### 2.2 forward
+ 返回下一个页面
+ history.forward();

###### 2.3 go
+ 返回到某个页面
+ history.go(数值);
> + 数值：
> > + 正数: 往下多少页面
> > + 负数: 往回多少页面

##### 3.0 alert 警告窗的使用
+ 弹窗窗口

###### 3.1 confirm 确认窗
+ 会有两个选项
> + 确定: true
> + 取消: false

Example:
```
<body>
    <div id="div1">go</div>

    <!-- JavaScript -->
    <script>
        /*
        // alert - confirm
        div1.onclick = function(){
            alert(confirm('small small 最漂亮?'));
        }
        */

        // 制作一个强迫对方点确定的弹窗
        div1.onclick = to;
        function to(){
            if(confirm('small small 最漂亮?')){
                alert('对对对');
            }
            else{
                to();
            }
        }
    </script>
</body>
```

###### 3.2 prompt 弹出输入框
+ 会有一个输入框
> + 可以利用用户输入的数据

Example:
```
<body>
    <div id="div1">go</div>

    <!-- JavaScript -->
    <script>
        // prompt 输入框
        // window.prompt('请输入密码');

        div1.onclick = function(){
            if(prompt('世界上漂亮的小姐姐是谁？') == 'small small'){
                alert('对对对');
            }
            else{
                alert('没眼光');
            }
        }

    </script>
</body>
```

##### 4.0 Navigator
+ 对象包含有关浏览器的信息
+ 可以返回浏览器信息，但是兼容性很差
+ navigator

![p3](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2028%20JS%20BOM/p3.PNG)

###### 4.1 userAgent
+ 用户信息
+ 可以返回浏览器用户信息
+ 各个浏览器都有这个值，可以看使用的是什么浏览器
+ 比如:
> + 谷歌 Chrome
> + 火狐 firefox
> + ie MS IE
+ navigator.userAgent

![p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2028%20JS%20BOM/p2.PNG)


##### 5.0 screen 对象
+ screen
+ 返回屏幕属性的一个对象
+ 不同的浏览器，属性的种类的数量也会有所不同

![p4](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2028%20JS%20BOM/p4.PNG)

###### 5.1 height
+ 电脑的显示器的高度
+ screen.height

###### 5.2 width 
+ 电脑的显示器的宽度
+ screen.width

###### 5.3 avaiHeight
+ 除了信息栏的高度
+ screen.height

###### 5.4 availWidth 
+ 除了信息栏的宽度
+ screen.width

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        console.log(screen);
        console.log(screen.height);
        console.log(screen.width);
        console.log(screen.availHeight);
        console.log(screen.availWidth);
    </script>
</body>
```

###### 5.5 screenX/Y 或 screenLeft/Top
+ 浏览器距离屏幕左边和上面的距离
+ screenX = screenLeft : 浏览器距离左边的距离
+ screenY = screenTop : 浏览器距离上面的距离

Example:
```
<body>
    <!-- JavaScript -->
    <script>
        console.log(screenX);
        console.log(screenLeft);
        console.log(screenY);
        console.log(screenTop);
    </script>
</body>
```

###### 5.6 innerHeight/Width 窗口的内部大小
+ 浏览器内容的宽度和高度

###### 5.7 outerHeight/Width 窗口的外部大小
+ 浏览器的宽度和高度

Example:
```
<body>
    <!-- JavaScript -->
    <script>      
        // 内部
        console.log(innerHeight);
        console.log(innerWidth);
        
        // 外部
        console.log(outerHeight);
        console.log(outerWidth);
    </script>
</body>
```

