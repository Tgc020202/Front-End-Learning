## 盒子模型
+ 一个元素在页面中所占位置大小
+ 包含的样式
> + width / height / margin /padding / border / content

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>盒子模型 - content</title>
    <style>
        #div1{
            float: left;
            background-color: black;
        }
        #div2{
            float: left;
            width: 200px;
            height: 200px;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div id="div2"></div>
    </div>
</body>
</html>
```
> + 盒子模型 - content
> > + 原本 div1(父类) 没有宽高，但是 div2(子类) 有宽高，所有子类把父类撑起来了，这就是所谓的 content


## css 的引用
1. 外链 - ```<link rel="stylesheet" type="text/css" href="css 的文件路径">```
2. 内嵌 - 在文件里使用 ```<style type="text/css">设置属性</style>```
3. 行内 - 在元素的标签里使用 ```<标签 style="设置属性"></标签>```
4. import - ```@import url('css 文件的路径');```
+ 级别: 行内 > 内嵌 > 外链
+ 被选中使用的概率: 位置越下面，被使用的概率最大


## 选择器
1. id
2. 标签
3. class
4. 通配符
+ 级别: id > class > 标签 > 通配符




















