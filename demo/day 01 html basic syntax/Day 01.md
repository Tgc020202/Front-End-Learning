# 1-1 html 基础语法

#### 1-1-1 基础语法(Basic syntax)
```
<!DOCTYPE html> //指明版本信息

<html> //称为根元素，所有的网页元素都在当中，一个html只会有一个根节点
  <head> //元素用于定义文档的头部
    <title>文档标题</title>
    <p>段落标签</p>
    <p>段落标签<a href = "网页链接" target = "_blank">名称</a></p>
  </head>
  
  <body>
    // 标题大小：1(大)至6(小)
    <h1>标题</h1>
    <h2>标题</h2>
    <h3>标题</h3>
    <h4>标题</h4>
    <h5>标题</h5>
    <h6>标题</h6>
    
    // 无序排列(unordered list)
    <ul>
    <li>内容</li>
    <li>内容<a href = "网页链接" target = "属性">名称</a></li>
    </ul>
    
    // 有序排列(ordered list)
    <ol>
    <li></li>
    </ol>
    
  </body>
</html>
```

#### 1-1-2 div
+ div用于组合其他HTML元素的容器。可用于对大的内容快设置样式属性。文档布局，它取代了使用表格定义布局的老式方法。

Example:
```
<div>
    <p>
        testing 123...
    </p>
</div>
```

#### 1-1-3 hx
+ hx HTML标题 标签只用于标题。HTML的标题有6种分别是 h1 h2 h3 h4 h5 h6 。
+ h1 为最大标题，一般一个页面只用一次。
+ h6 为最小标题

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <h1>this is title 1</h1>
    <h2>this is title 2</h2>
    <h3>this is title 3</h3>
    <h4>this is title 4</h4>
    <h5>this is title 5</h5>
    <h6>this is title 6</h6>
    
    <div></div>
  </body>
</html>
```

#### 1-1-4-p
+ p 元素是段落元素 会自动在其前后创建一些空白 而浏览器会自动添加这些空间。

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <div>
      <p>段落一</p>
      <p>段落二</p>
    </div>
  </body>
</html>
```

#### 1-1-5 br
+ br 换行符

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <div>
      <p>这是第一行<br />这是第二行</p>
    </div>
  </body>
</html>
```

#### 1-1-6 hr
+ hr 标签定义 HTML 页面中的主题变化(比如话题的转移)，并显示为一条水平分割线。

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <div>
      <p>分隔线在下面<hr>上面有分隔线</p>
    </div>
  </body>
</html>
```

#### 1-1-7 img
+ img 标签 用来申明图像的插入。
+ src 属性:规定显示图像的 URL(当图片存于跟文件同一个位置，可以直接使用 [图名.jpg])
+ URL 为图像的相对路径或者绝对路径均可
+ alt 属性:文本
+ title 属性:定义图片的标题，鼠标放在图片上会显示

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <div>
      <img src = "图片的位置属性" alt = "文本" title = "图片显示的标题" />
    </div>
  </body>
</html>
```

#### 1-1-8 a
+ a 标签用来设置超文本链接。
+ 超链接可以是一个字，一个词或者一组词，也可以是一幅图
+ 可以通过点击这些内容来跳转到新的文档或者当前文档中的某个部分。
+ 如果要设置成点击图片进入网站，可以通过把标题设为<img src = "图片的位置属性">
- href 属性:描述了链接的目标 url
- target 属性:设置链接跳转方式(_blank)

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <div>
      <p><a href = "链接" target = "属性">标题</a></p>
    </div>
  </body>
</html>
```

#### 1-1-9 span
+ span 用来组合文档中的行内元素，可用作文本的容器。
+ span 元素没有固定的格式表现
+ 当应用样式时，它才会产生视觉上的变化。
- span vs p:span 是行内元素，p是段落块元素

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <title>文档标题</title>
  </head>
  <body>
    <div>
      <span>添加内容</span>
    </div>
  </body>
</html>
```

#### 1-1-10 ul
+ ul 标签作为无序列表，他是一个项目的列表
+ 此类项目使用粗体圆点进行标记
+ 无序列表始于<ul>标签
+ 每个列表始于<li>标签

Example:
```
<ul>
   <li>无序列表一</li>
   <li>无序列表二</li>
   <li>无序列表三</li>
</ul>
```

#### 1-1-11 ol
+ ol 标签作为有序列表，他也是一个项目的列表
+ 此项目使用数字进行标记
+ 有序列表始于<ol>标签
+ 每个列表项始于<li>标签

Example:
```
<ol>
   <li>有序列表一</li>
   <li>有序列表二</li>
   <li>有序列表三</li>
</ol>
```

- 有序列表是可以调整的，不单单可以是数字，只需要加上type关键字
- 但是在HTML5中有一些类型不被认可，所有保险起见还是使用数字

Example:
```
<ol type = "i">
   <li>有序列表一</li>
   <li>有序列表二</li>
   <li>有序列表三</li>
</ol>
```

#### 1-1-12 注释(comment)
+ 注释标签用于在源代码中插入注释。
+ 注释不会显示在浏览器中。
+ 可使用注释对代码进行解释，这样做有助于以后的时间对代码的的修改，当编写了大量的代码时，就有奇效。

Example:
```
<!-- 这就是一的p标签的写法 -->
```

#### 1-2-0 属性标签
+ HTML 元素可以通过设置属性，实现某些特定的效果
+ 属性可以在原始中添加附加信息
+ 属性一般描述于开始标签
+ 属性总是以名称/值对的形式出现
+ 比如:name = "value"

Example:
```
<p class = "container">
  这是一个带有 class 属性且值为 container 的段落<p>标签
</p>
```
