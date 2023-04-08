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

### window 调用其他设备
![window 参考图](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p1.png)

#### 布局容器 - container

![布局与视图的大小](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p5.png)

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

![形成对比](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p2.png)

#### 栅格网格系统
+ 会随着屏幕或视窗(viewport)尺寸的增加
+ 系统会自动分为最多 12 列
+ 使用 row (行) 和 column (列) 的组合布局页面
+ 可放置内容在布局中
+ 通过容器定义大小，常见平分为 12 份 (也有平分 24 份以及 32 份的)

![栅格图文解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p3.png)
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
![图文解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p4.png)
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

![没有被压缩](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p6.png)

![被压缩后的差别](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p7.png)
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

![图文显示](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p8.png)


###### 列排序 order / pull and push
+ 改变列的序列或位置
+ 写法 : order-排序的级别
+ 排序的级别可以以数值的方式来定义，一个使用 first 或者 last
+ pull and push 只适用于 bootstrap 3，bootstrap 3 以上的都无法使用
+ 写法 : col-push-移动的列组合数 和 col-pull-移动的列组合数
+ pull 往前，push 往后

Example(order):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>栅格网格系统 - 列排序</title>
</head>
<body>
    <!-- 布局容器 -->
    <div class="container" style="background: thistle;">
        <!-- 行元素 -->
        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-0" style="background: lightblue;">4列</div>
            <div class="col-4 order-0" style="background: lightcoral;">4列</div>
            <div class="col-4 order-0" style="background: lightgreen;">4列</div>
        </div>

        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-3" style="background: lightblue;">4列</div>
            <div class="col-4 order-2" style="background: lightcoral;">4列</div>
            <div class="col-4 order-1" style="background: lightgreen;">4列</div>
        </div>

        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-last" style="background: lightblue;">4列</div>
            <div class="col-4 order-first" style="background: lightcoral;">4列</div>
            <div class="col-4 order-5" style="background: lightgreen;">4列</div>
        </div>
        
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![图文显示](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p9.png)

+ order-first 与 order-0 都是相同的，但是 first 的级别比数值的级别高
+ order-last 与 order-12 都是相同的，但是 last 的级别比数值的级别高
+ 当数值相同，就会选择最前面的为优先

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>栅格网格系统 - 列排序</title>
</head>
<body>
    <!-- 布局容器 -->
    <div class="container" style="background: thistle;">
        <!-- 行元素 -->
        原本
        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-0" style="background: lightblue;">第一</div>
            <div class="col-4 order-1" style="background: lightcoral;">第二</div>
            <div class="col-4 order-2" style="background: lightgreen;">第三</div>
        </div>

        对比第一
        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-last" style="background: lightblue;">第一</div>
            <div class="col-4 order-first" style="background: lightcoral;">第二</div>
            <div class="col-4 order-0" style="background: lightgreen;">第三</div>
        </div>

        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-last" style="background: lightblue;">第一</div>
            <div class="col-4 order-0" style="background: lightcoral;">第二</div>
            <div class="col-4 order-first" style="background: lightgreen;">第三</div>
        </div>

        对比最后
        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-last" style="background: lightblue;">第一</div>
            <div class="col-4 order-first" style="background: lightcoral;">第二</div>
            <div class="col-4 order-12" style="background: lightgreen;">第三</div>
        </div>

        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4 order-12" style="background: lightblue;">第一</div>
            <div class="col-4 order-last" style="background: lightcoral;">第二</div>
            <div class="col-4 order-first" style="background: lightgreen;">第三</div>
        </div>
        
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![图文显示](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p10.png)

###### 列嵌套
+ 每个列里面可以嵌套多 12 个列

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>列嵌套</title>
</head>
<body>
    <!-- 布局容器 -->
    <div class="container" style="background: thistle;">
        <!-- 行元素 -->
        <div class="row text-center" style="border: 1px solid black;">
            <!-- 列元素 -->
            <div class="col-4" style="background: lightblue;">
                <!-- 内嵌套 -->
                <div class="row text-center" style="border: 1px solid black;">
                    <!-- 列元素 -->
                    <div class="col-4" style="background: lightgoldenrodyellow;">4</div>
                    <div class="col-4" style="background: lightgray;">4</div>
                </div>
            </div>

            <div class="col-4" style="background: lightcoral;">
                <!-- 内嵌套 -->
                <div class="row text-center" style="border: 1px solid black;">
                    <!-- 列元素 -->
                    <div class="col-2" style="background: lightgoldenrodyellow;">2</div>
                    <div class="col-2" style="background: lightgray;">2</div>
                </div>
            </div>

            <div class="col-4" style="background: lightgreen;">
                <!-- 内嵌套 -->
                <div class="row text-center" style="border: 1px solid black;">
                    <!-- 列元素 -->
                    <div class="col-3" style="background: lightgoldenrodyellow;">3</div>
                    <div class="col-3" style="background: lightgray;">3</div>
                </div>
            </div>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![列嵌套图文解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p11.png)


#### 排版
###### 标题
+ 与 HTML 相仿，使用标签 h1 至 h6
+ hr 标签用于生成百分百宽度的横线，用于分隔内容
+ bootstrap 对 h1 至 h6 的效果进行了覆盖
+ bootstrap 提供了对应的类名，为不是标题元素的元素可以设置标题元素的样式
+ 可以在标题内使用其他的副标题

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>Header 标题</title>
</head>
<body>
    <div class="container">
        <h1>标题一</h1>
        <h2>标题二</h2>
        <h3>标题三</h3>

        <!-- 使非标题的元素拥有标题元素的属性 -->
        <div class="h1">我是标题一</div>

        <!-- 在标题内增添副标题 -->
        <h1>大标题<small>副标题</small></h1>

        <!-- 在标题内添加元素并设置其类名为small -->
        <h1>大标题<span class="small">副标题</span></h1>

        <!-- 使用非标题的同时，增添副标题 -->
        <div class="h1">大标题<small>副标题</small></div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![例子](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p12.png)

###### 段落
+ 与 HTML 相仿，使用标签 p
+ lead 可以用于突出强调内容

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>Paragraph 段落</title>
</head>
<body>
    <div class="container">
        <p>我是段落</p>

        <!-- lead -->
        <p class="lead">
            我是加了 lead 的段落，
            <b>加粗内容</b>，
            <strong>加粗内容二</strong>，
            <small>缩小内容</small>，
            <em>斜体内容</em>
        </p>


    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![字体图文解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p13.png)

###### 强调
+ text muted: 提示，浅灰色(#999)
+ text-primary: 主要，蓝色(#428bca)
+ text-success: 成功，浅绿色(#3c763d)
+ text-info: 通知信息，浅蓝色(#31708f)
+ text-warning: 警告，黄色(#8a6d3b)
+ text-danger: 危险，褐色(#a94442)


Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>强调</title>
</head>
<body>
    <div class="container">
        <!-- 强调效果 -->
        <div class="text-muted">.text-muted: 提示，浅灰色</div>
        <div class="text-primary">.text-primary: 主要，蓝色</div>
        <div class="text-success">.text-success: 成功，浅绿色</div>
        <div class="text-info">.text-info: 通知信息，浅蓝色</div>
        <div class="text-warning">.text-warning: 警告，黄色</div>
        <div class="text-danger">.text-danger: 危险，褐色</div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![图文解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p14.png)


###### 对齐效果 alignment
+ text-left: 左对齐 (被设为默认，且适用于 Bootstrap 3)
+ text-right: 右对齐 (适用于 Bootstrap 3)
+ text-justify: 两端对齐 (适用于 Bootstrap 3)
+ text-center: 居中对齐
+ text-start: 左对齐
+ text-end: 右对齐
+ style="text-align: justify;": 两端对齐

Example(Bootstrap 5):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>对齐效果</title>
</head>
<body>
    <div class="container">
        <!-- 对齐效果 -->
        <p class="text-left">我是左对齐</p>
        <p class="text-right">我是右对齐</p>
        <p class="text-start">我是左对齐</p>
        <p class="text-end">我是右对齐</p>
        <p class="text-center">我是居中对齐</p>
        <p class="text-justify">
            我是两端对齐,我是很长很长很长很长很,
            长很长很长很长很长很长很长很长很长很长,
            很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长的段落
        </p>
        <p style="text-align: justify;">
            我是两端对齐,我是很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长的段落
        </p>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![文字解析](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p15.png)


#### 列表
+ 无序列表: ul
+ 有序列表: ol
+ 定义列表: dl

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>初始列表</title>
</head>
<body>
    <div class="container">
        无序列表
        <ul>
            <li>1</li>
            <li>2</li>
        </ul>
        有序列表
        <ol>
            <li>1</li>
            <li>2</li>
        </ol>
        定义列表
        <dl>
            <dt>标题1</dt>
            <dd>说明1</dd>
            <dt>标题2</dt>
            <dd>说明2</dd>
        </dl>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![列表](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p16.png)

###### 去点列表
+ 顾名思义，就是没有点的列表

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>去点列表</title>
</head>
<body>
    <div class="container">
        无序列表
        <ul class="list-unstyled">
            <li>1</li>
            <li>2</li>
        </ul>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```
![去点列表](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p17.png)

###### 内联列表
+ 使其在同一个水平线上
+ 写法: list-inline 和 list-inline-item

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>内联列表</title>
</head>
<body>
    <div class="container">
        <ul class="list-inline">
            <li class="list-inline-item">1</li>
            <li class="list-inline-item">2</li>
            <li class="list-inline-item">3</li>
            <li>4</li>
            <li>5</li>
        </ul>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![内联列表](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2053%20Bootstrap/Images/p18.png)


###### 自定义列表 - 内联列表 {待更新}
+ 写法: dl-horizontal (只能在 Bootstrap 3 使用)
+ 平时可以通过，写法: list-group list-group-horizontal

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>自定义列表 - 内联列表</title>
</head>
<body>
    <div class="container">
        <dl class="dl-horizontal">
            <dt>标题1</dt>
            <dd>说明1</dd>
            <dt>标题2</dt>
            <dd>说明2</dd>
        </dl>

        <dl class="list-group list-group-horizontal">
            <dt class="list-group-item">标题1</dt>
            <dt class="list-group-item">标题2</dt>
        </dl>

        <dl class="list-group list-group-horizontal">
            <dd class="list-group-item">说明1</dd>
            <dd class="list-group-item">说明2</dd>
        </dl>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

#### 代码风格
+ 单行内联代码: <code></code>
+ 多行块代码: <pre></pre>
+ 显示用户输入代码: <kbd></kbd>

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>代码风格</title>
</head>
<body>
    <div class="container">
        <code>
            this is a simple code use code
            this is a simple code use code
        </code>
        <code>this is a simple code use code</code>

        <pre>
            this is a simple code use pre
            this is a simple code use pre
        </pre>
        <pre>this is a simple code use pre</pre>

        <kbd>
            this is a simple code use kbd
            this is a simple code use kbd
        </kbd>
        <kbd>this is a simple code use kbd</kbd>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![代码风格](p19)

###### 快捷键效果

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>代码风格 - 快捷键的效果</title>
</head>
<body>
    <div class="container">
        <p>使用<kbd>ctrl</kbd>+<kbd>s</kbd>进行保存</p>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![按键风格](p20)


###### 显示 HTML 代码
+ `&lt;` 替代 `<`
+ `&gt;` 替代 `>`
+ 比如: `<h1></h1>` -> `&lt;h1&gt; &lt;/h1&gt;`

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>代码风格 - HTML 格式</title>
</head>
<body>
    <div class="container">
        <pre>
            &lt;h2&gt;你好，一起学习 bootstrap&lt;/h2&gt;
        </pre>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![HTML 格式](p21)


###### 滚动条 
+ 写法: .pre-scrollable(适用于 Bootstrap3)
+ 写法: .overflow-auto

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>代码风格 - 滚动条</title>
</head>
<body>
    <div class="container">
        <pre class="pre-scrollable overflow-auto list-unstyled">
            <li>1..................</li>
            <li>2..................</li>
            <li>3..................</li>
            <li>4..................</li>
            <li>5..................</li>
            <li>6..................</li>
            <li>7..................</li>
            <li>8..................</li>
            <li>9..................</li>
            <li>10.................</li>
            <li>11.................</li>
            <li>12.................</li>
            <li>13.................</li>
            <li>14.................</li>
            <li>15.................</li>
            <li>16.................</li>
            <li>17.................</li>
            <li>18.................</li>
            <li>19.................</li>
            <li>20.................</li>
            <li>21.................</li>
            <li>22.................</li>
            <li>23.................</li>
            <li>24.................</li>
        </pre>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

####  表格样式
+ 基础表格:
> + table
+ 附加样式表格:
> + table-striped: 斑马线表格
> + table-bordered: 带边框表格
> + table-hover: 鼠标触碰高亮表格
> + table-condensed: 紧凑型表格

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表格样式</title>
</head>
<body>
    普通表格
    <table>
        <tr class="table-active">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-danger">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-success">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
    </table>

    <hr><br>
    基础表格
    <table class="table">
        <tr class="table-active">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-danger">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-success">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
    </table>

    <hr><br>
    斑马线表格
    <table class="table table-striped">
        <tr>
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr>
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr>
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
    </table>

    <hr><br>
    带边框表格
    <table class="table table-bordered">
        <tr class="table-active">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-danger">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-success">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
    </table>

    <hr><br>
    鼠标触碰高亮表格
    <table class="table table-hover">
        <tr class="table-active">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-danger">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-success">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
    </table>

    <hr><br>
    紧凑型表格
    <table class="table table-responsive">
        <tr class="table-active">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-danger">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
        <tr class="table-success">
            <th>1</th>
            <th>2</th>
            <th>3</th>
        </tr>
    </table>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![各种表格样式](p22)

###### 颜色
![各种颜色样式](p23)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表格样式 - 颜色</title>
</head>
<body>
    <div class="container">
        <table class="table">
            <tr>
                <th>table</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-primary">
                <th>table-primary</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-secondary">
                <th>table-secondary</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-success">
                <th>table-success</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-danger">
                <th>table-danger</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-warning">
                <th>table-warning</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-info">
                <th>table-info</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-light">
                <th>table-light</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
            <tr class="table-dark">
                <th>table-dark</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
            </tr>
        </table>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```


##### 表单样式
+ .form-control
> + input
> + select
> + textarea

Example(普通样式):
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表单的基本样式</title>
</head>
<body>
    <input type="text" name="" id="">
    <br>
    <select>
        <option value="">请选择国家</option>
        <option value="">马来西亚</option>
        <option value="">中国</option>
        <option value="">印度尼西亚</option>
    </select>
    <br>
    <textarea name="" id="" cols="30" rows="10"></textarea>
    <br>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

###### 文本框 input
+ .form-control: 普通大小
+ .form-control-lg: 大
+ .form-control-sm: 小

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表单的样式 - input</title>
</head>
<body>
    <!-- 普通 -->
    <input type="text" name="" id="" style="background-color: blue;">
    <br>
    
    <!-- 独占一行 -->
    <input type="text" name="" id="" class="form-control" style="background-color: green;">
    <br>

    <hr>

    <!-- 可设定 row 和 col 控制 input 的宽 -->
    <div class="row">
        <div class="col-3">
            <!-- normal size -->
            <input type="text" name="" id="" class="form-control" style="background-color: red;">
            <br>
            <!-- large size -->
            <input type="text" name="" id="" class="form-control form-control-lg" style="background-color: orange;">
            <br>
            <!-- small size -->
            <input type="text" name="" id="" class="form-control form-control-sm" style="background-color: yellow;">
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![观察长宽](p24)

###### 下拉框 select
+ .form-control: 普通大小
+ .form-control-lg: 大
+ .form-control-sm: 小

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表单的样式 - select</title>
</head>
<body>
    <!-- 普通 -->
    <select style="background-color: blue;">
        <option value="">羽球</option>
        <option value="">篮球</option>
        <option value="">足球</option>
    </select>
    <br>
    
    <!-- 独占一行 -->
    <select class="form-control" style="background-color: green;">
        <option value="">羽球</option>
        <option value="">篮球</option>
        <option value="">足球</option>
    </select>
    <br>

    <hr>

    <!-- 可设定 row 和 col 控制 input 的宽 -->
    <div class="row">
        <div class="col-3">
            <!-- normal size -->
            <select class="form-control" style="background-color: red;">
                <option value="">羽球</option>
                <option value="">篮球</option>
                <option value="">足球</option>
            </select>
            <br>
            <!-- large size -->
            <select class="form-control form-control-lg" style="background-color: orange;">
                <option value="">羽球</option>
                <option value="">篮球</option>
                <option value="">足球</option>
            </select>
            <br>
            <!-- small size -->
            <select class="form-control form-control-sm" style="background-color: yellow;">
                <option value="">羽球</option>
                <option value="">篮球</option>
                <option value="">足球</option>
            </select>
        </div>
    </div>
    <hr>
    <div class="row">
        <div class="col-3">
            <!-- normal size -->
            <select class="form-control" style="background-color: red;" multiple="multiple">
                <option value="">羽球</option>
                <option value="">篮球</option>
                <option value="">足球</option>
            </select>
            <br>
            <!-- large size -->
            <select class="form-control form-control-lg" style="background-color: orange;" multiple="multiple">
                <option value="">羽球</option>
                <option value="">篮球</option>
                <option value="">足球</option>
            </select>
            <br>
            <!-- small size -->
            <select class="form-control form-control-sm" style="background-color: yellow;" multiple="multiple">
                <option value="">羽球</option>
                <option value="">篮球</option>
                <option value="">足球</option>
            </select>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![观察长宽](p25)

###### 文本域 textarea
+ .form-control: 普通大小
+ .form-control-lg: 大
+ .form-control-sm: 小

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表单的样式 - textarea</title>
</head>
<body>
    <!-- 普通 -->
    <textarea name="" id="" cols="10" rows="2" style="background-color: blue;"></textarea>
    <br>
    
    <!-- 独占一行 -->
    <textarea name="" id="" cols="10" rows="2" class="form-control" style="background-color: green;"></textarea>
    <br>

    <hr>

    <!-- 可设定 row 和 col 控制 input 的宽 -->
    <div class="row">
        <div class="col-3">
            <!-- normal size -->
            <textarea name="" id="" cols="10" rows="2"  class="form-control" style="background-color: red;"></textarea>
            <br>
            <!-- large size -->
            <textarea name="" id="" cols="10" rows="2" class="form-control form-control-lg" style="background-color: orange;"></textarea>
            <br>
            <!-- small size -->
            <textarea name="" id="" cols="10" rows="2"  class="form-control-sm" style="background-color: yellow;"></textarea>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![观察长宽](p26)

###### 复选框 checkbox
+ 垂直显示
> + 透过 div 元素
> + 需要赋予 div 元素 .form-check-label

+ 水平显示
> + 透过 label 元素
> + 需要赋予 label 元素 .form-check-inline

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表单的样式 - checkbox</title>
</head>
<body>
    <!-- 普通 -->
    <input type="checkbox" name="hobby" value="">唱歌
    <input type="checkbox" name="hobby" value="">跳舞
    <input type="checkbox" name="hobby" value="">下棋

    <!-- 使用 bootstrap 样式 -->
    <!-- 垂直显示 -->
    <div class="row">
        <div class="col-3">
            <div class="form-check-label">
                <label for=""><input type="checkbox" name="hobby" value="">唱歌</label>
            </div>
            <div class="form-check-label">
                <label for=""><input type="checkbox" name="hobby" value="">跳舞</label>
            </div>
            <div class="form-check-label">
                <label for=""><input type="checkbox" name="hobby" value="">下棋</label>
            </div>
        </div>
    </div>

    <!-- 水平显示 -->
    <div class="row">
        <div class="col-4">
            <label for="" class="form-check-inline"><input type="checkbox" name="hobby" value="">唱歌</label>
            <label for="" class="form-check-inline"><input type="checkbox" name="hobby" value="">跳舞</label>
            <label for="" class="form-check-inline"><input type="checkbox" name="hobby" value="">下棋</label>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![图文详解](p27)

###### 单选框 radio
+ 垂直显示
> + 透过 div 元素
> + 需要赋予 div 元素 .form-switch

+ 水平显示
> + 透过 label 元素
> + 需要赋予 label 元素 .form-switch

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>表单的样式 - radio</title>
</head>
<body>
    <!-- 普通 -->
    <input type="radio" name="sex" value="">男
    <input type="radio" name="sex" value="">女

    <!-- 使用 bootstrap 样式 -->
    <!-- 垂直显示 -->
    <div class="row">
        <div class="col-3">
            <div class="form-switch">
                <label for=""><input type="radio" name="sex" value="">男</label>
            </div>
            <div class="form-switch">
                <label for=""><input type="radio" name="sex" value="">女</label>
            </div>
        </div>
    </div>

    <!-- 水平显示 -->
    <div class="row">
        <div class="col-4">
            <label for="" class="form-switch"><input type="radio" name="sex" value="">男</label>
            <label for="" class="form-switch"><input type="radio" name="sex" value="">女</label>
        </div>
    </div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```
![图文详解](p28)


#### 按钮 button
+ bootstrap 美化了原本的按钮
+ .btn

![按钮的种类](p28)

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>按钮</title>
</head>
<body>
    <button class="">without bootstrap</button>
    <button class="btn">normal btn</button>
    <button class="btn btn-danger">btn-danger</button>
    <button class="btn btn-primary">btn-primary</button>
    <button class="btn btn-info">btn-info</button>
    <button class="btn btn-success">btn-success</button>
    <button class="btn btn-default">btn-default</button>
    <button class="btn btn-warning">btn-warning</button>
    <button class="btn btn-link">btn-link</button>
    <button class="btn btn-dark">btn-dark</button>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

###### .btn 不单单局限于 button 元素

Example:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="bootstraptools/css/bootstrap.min.css" rel="stylesheet">
    <title>按钮</title>
</head>
<body>
    <button class="btn btn-primary">button 按钮元素</button>
    <hr>
    <a href="" class="btn btn-primary">a 链接元素</a>
    <hr>
    <span class="btn btn-primary">span 元素</span>
    <hr>
    <div class="btn btn-primary">div 元素</div>

    <!-- JavaScript -->
    <script src="bootstraptools/js/bootstrap.min.js"></script>
</body>
</html>
```

![图文展示](p30)


###### 按钮大小
















