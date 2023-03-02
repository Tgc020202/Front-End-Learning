# html 有用的标签

#### 1.1 input 标签
+ 可以使用 input 插件让用户与网页互动，比如填写资料，选项以及颜色等
+ ```<input type="种类" name="" placeholder="">```
+ input 标签有很多种类型，可通过更改种类(type)使用不同的类型
+ 相关资讯可以点击传送看会之前的笔记[传送](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2004%20html%20table/Day%2004.md)，4.0 的 Form 表单的部分有介绍 input 的各种种类

Example:
```
<html>
  <body>
    <!-- input 标签 -->
    <!-- text 文字种类也是最常见的 -->
    <div>
        用户名:
        <input type="text" name="">
    </div>
    <!-- 密码种类 -->
    <div>
        密码:
        <input type="password">
    </div>
    <!-- 选项种类 -->
    <div>
        选项 1:
        <input type="checkbox">
        选项 2:
        <input type="checkbox">
        选项 3:
        <input type="checkbox">
    </div>
    <!-- 单选种类 -->
    <div>
        单选:
        <input type="radio">
    </div>
    <!-- 颜色种类 --> 
    <div>
        颜色:
        <input type="color">
    </div>
    <!-- 按钮种类 -->
    <!-- value 就是内容 -->
    <div>
        按钮:
        <input type="button" value="按钮">
    </div>
  </body>
</html>
```

#### 1.2 button 标签
+ 顾名思义就是按钮

Example 1:
```
<html>
  <body>
    <button>内容</button>
    <button>内容</button>
    <button>内容</button>
    <button>内容</button>
    <button>内容内容内容</button>
  </body>
</html>
```

Example 2(也可以用 input 来建立一个 button):
```
<html>
  <body>
    <div>
        按钮:
        <input type="button" value="按钮里的内容">
    </div>
  </body>
</html>
```
