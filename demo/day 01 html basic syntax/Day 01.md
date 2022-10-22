# html基本语法笔记

## 1-1-1 基本语法(Basic syntax)
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
    <li>内容<a href = "网页链接" target = "_blank">名称</a></li>
    </ul>
    
    // 有序排列(ordered list)
    <ol>
    <li></li>
    </ol>
    
  </body>
</html>
```

#### 1-1-2 div
div用于组合其他HTML元素的容器。可用于对大的内容快设置样式属性。文档布局，它取代了使用表格定义布局的老式方法。
```
<div>
  <p></p>
  <img />
</div>
```
Example:
```
<div>
    <p>
        testing 123...
    </p>
</div>
```

#### 1-1-3 hx
hx HTML标题 标签只用于标题。HTML的标题有6种分别是 h1 h2 h3 h4 h5 h6 。
h1 为最大标题，一般一个页面只用一次。
h6 为最小标题

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

