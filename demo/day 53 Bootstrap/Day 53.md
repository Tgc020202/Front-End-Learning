## Bootstrap 框架
+ 使页面变得好看，简洁，直观，强悍的前端开发
+ html, css, javascript 的工具集
+ 自定义 jQuery 插件

### Bootstrap 框架代码的形式
+ viewport - 用户是否可以缩放页面
+ width/height - 指定视区的逻辑宽度与高度
+ device-width/device-height - 指示视区的宽度/高度为设备的屏幕宽度/高度
+ initial-scale - 指令用于设置 web 的初始缩放比例
+ initial-scale=1 - 将显示未经缩放的 web 文档

### Bootstrap 的引入方式
1. 使用链接
+ 使用链接的前提是需要保证网络的质量
+ 引入 Bootsrap 的样式 : 

```
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
```

+ 引入 Bootstrap 的插件

```
<!-- JavaScript -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>
```

2. 安装 Bootstrap 文件 - 文件包含 css 样式和 js 插件
+ 相对比较稳定
+ 引入 Bootsrap 的样式 : 
> + 需要先安装 bootstrap 的文件
> + 引入写法 : <link href="文件夹名称/css/bootstrap.min.css" rel="stylesheet">

```
<link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
```

+ 引入 Bootstrap 的插件
> + 引入写法 : <script src="文件夹名称/js/bootstrap.min.js"></script>

```
<!-- JavaScript -->
<script src="bootstraptools/js/bootstrap.min.js"></script>
```

### Bootstrap 的默认模板

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous"> -->
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>初识 Bootstrap</title>
</head>
<body>
    <h1>Hello World！</h1>


    
    <!-- JavaScript -->
    <!-- <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script> -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

#### window 调用其他设备
![window 参考图](p1)

#### 布局容器

![布局与视图的大小](p5)

###### container
+ 会有固定的宽度，左右两侧会有空间
+ 支持响应布局的容器
+ 布局写法:

```
<div class="container"></div>
```

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>初识 Bootstrap</title>
</head>
<body>
    <div>
        这是没有布局的
    </div>

    <div class="container">
        使用 container 布局
        container 会有固定的宽度，左右两侧会有空间
    </div>

    <div class="container" style="background: thistle; height: 200px;">
        使用 container 布局
        container 会有固定的宽度，左右两侧会有空间
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

###### container-fluid
+ 会占用 100% 的宽度，占据全部视口(viewport)的容器
+ 布局写法:

```
<div class="container-fluid"></div>
```

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>初识 Bootstrap</title>
</head>
<body>
    <div>
        这是没有布局的
    </div>

    <div class="container" style="background: lightblue; height: 200px;">
        使用 container 布局<br>
        container 会有固定的宽度
        左右两侧会有空间
    </div>

    <div class="container-fluid" style="background: thistle; height: 200px;">
        使用 container-fluid 布局<br>
        container-fluid 会占用 100% 的宽度，占据全部视口(viewport)的容器
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![形成对比](p2)

#### 栅格网格系统
+ 会随着屏幕或视窗(viewport)尺寸的增加
+ 系统会自动分为最多 12 列
+ 使用 row (行) 和 column (列) 的组合布局页面
+ 可放置内容在布局中
+ 通过容器定义大小，常见平分为 12 份 (也有平分 24 份以及 32 份的)

![栅格图文解析](p3)
> + md: 中等屏
> + xs: 超小屏
> + sm: 小屏
> + lg: 大屏

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>栅格网格系统</title>
</head>
<body>
    <!-- 布局容器 -->
    <div class="container" style="background: thistle; height: 200px;">
        <!-- 行元素 -->
        <div class="row">
            <!-- 列元素 -->
            <div class="col-md-4" style="background: lightblue;">4列</div>
            <div class="col-md-8" style="background: lightcoral;">8列</div>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```
![图文解析](p4)
> + 切记要保证屏幕/视图的大小


+ 生成更多的行 rows

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>栅格网格系统</title>
</head>
<body>
    <!-- 布局容器 -->
    <div class="container" style="background: thistle;">
        <!-- 行元素 -->
        <div class="row">
            <!-- 列元素 -->
            <div class="col-sm-4 col-md-4" style="background: lightblue;">4列</div>
            <div class="col-sm-8 col-md-8" style="background: lightcoral;">8列</div>
        </div>
        <!-- 行元素 -->
        <div class="row">
            <!-- 列元素 -->
            <div class="col-4" style="background: lightblue;">4列</div>
            <div class="col-8" style="background: lightcoral;">8列</div>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

###### col 的好处

![没有被压缩](p6)

![被压缩后的差别](p7)
> + 当屏幕的大小改变，只要不超过 12 列，col 指定的列不会被影响，


###### 列偏移 offset
+ 写法 : offset-偏移的数值
+ 偏移的数值加 col 的数值别超过 12，超过 12 就会跳行

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>栅格网格系统 - 列偏移 offset</title>
</head>
<body>
    <!-- 布局容器 -->
    <div class="container" style="background: thistle;">
        <!-- 行元素 -->
        <div class="row text-center">
            <!-- 列元素 -->
            <div class="col-4" style="background: lightblue;">4列</div>
        </div>

        <div class="row text-center">
            <!-- 列元素 -->
            <div class="col-4 offset-4" style="background: lightblue;">4列</div>
        </div>

        <div class="row text-center">
            <!-- 列元素 -->
            <div class="col-4 offset-8" style="background: lightblue;">4列</div>
        </div>

        <div class="row text-center">
            <!-- 列元素 -->
            <div class="col-4 offset-10" style="background: lightblue;">4列</div>
        </div>

        <div class="row text-center">
            <!-- 列元素 -->
            <div class="col-4 offset-12" style="background: lightblue;">4列</div>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![图文显示](p8)



