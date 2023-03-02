# css 基础语法
#### 1-0 基础语法

+ a 标签的属性

Example:
```
<!DOCTYPE html>
<html>
    <head>
    <style type = "text/css">
        a{
            text-decoration: none;
            color:black;
        }

        /*未访问的链接，和a{}相同且同时存在时会覆盖*/
        a:link{
            color:darkblue;
        }

        /*鼠标移动到超链接上时*/
        a:hover{
            text-decoration: underline;
            color:green;
        }
        /*被选定的超链接*/
        a:active{
            text-decoration: underline;
            color: yellow;
        }
        /*已访问的超链接*/
        /* a:visited{
            color: lightblue;
        } */
    </style>
    </head>
    <body>
        <div>
            <a href="https://www.youtube.com/" target="_blank">Youtube</a>
        </div>
    </body>
</html>
```
> 1. link - 未访问的链接
> > ![p1](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2005%20css%20basic%20syntax/p1.PNG)
> > + 如果 History 没有这个链接就代表还未访问链接，所以就会触发
> 2. hover - 鼠标在链接上面的时候
> 3. active - 点击鼠标的时候
> 4. visited - 已访问过的链接
> > ![p2](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2005%20css%20basic%20syntax/p2.PNG)
> > + 如果 History 有了这个链接就代表已经访问了，然后就会触发



#### CSS 字体属性

| 属性 | 描述 |
|------|------|
| font | 在一个声明中设置所有字体属性 |
| font-family | 规定文本的字体系列 |
| font-size | 规定文本的字体尺寸 |
| font-size-adjust | 为元素规定 aspect 值 |
| font-stretch | 收缩或拉伸当前的字体系列 |
| font-style | 规定文本的字体样式 |
| font-variant | 规定是否以小型大写字母的字体显示文本 |
| font-weight | 规定字体的粗细 |

#### CSS 可能的值

| 值 | 描述 |
|------|------|
| xx-small,x-small,small,medium,large,x-large,xx-large | 把字体的尺寸设置为不同的尺寸，从 xx-small 到 xx-large。默认值为 medium |
| smaller | 把 font-size 设置为比父元素更小的尺寸 |
| larger | 把 font-size 设置为比父元素更大的尺寸 |
| length | 把 font-size 设置为一个固定的值 |
| % | 把 font-size 设置为基于父元素的一个百分比值 |
| inherit | 规定应该从父元素继承字体尺寸 |

#### CSS 文本属性(Text)

| 属性 | 描述 |
|------|------|
| color | 设置文本的颜色 
| direction | 规定文本的方向、书写方向 |
| letter-spacing | 设置字符间距 |
| line-height | 设置行高 |
| text-align | 规定文本的水平对齐的方式 |
| text-decoration | 规定添加到文本的装饰效果 |
| text-indent | 规定文本块首行的缩进 |
| text-shadow | 规定添加到文本的阴影效果 |
| text-transform | 控制文本的大小写 |
| unicode-bidi | 设置文本的方向 |
| white-space | 规定如何处理元素中的空白 |
| word-spacing | 设置单调间距 |
| hanging-punctuation | 规定标点字符是否位于线框之外 |
| punctuation-trim | 规定是否对标点字符进行修剪 |
| text-align-last | 设置如何对齐最后一行或紧挨着强制换行符之前的行 |
| text-emphasis | 向元素的文本应用重点标记以及重点标记的前景色 |
| text-justify | 规定当 text-align 设置为 “justify” 时所使用的对齐方法 |
| text-outline | 规定文本的轮廓 |
| text-overflow | 规定当文本溢出包含元素时发生的事情 |

+ 改变 p 里面的首字母(比如改变大小，改变颜色等)
Example:
```
<!DOCTYPE html>
<html>
  <head>
    <style>
        p:first-letter{
            font-size: 200%;
            color:blueviolet;
        }
    </style>
  </head>
  <body>
  </body>
</html>
```

#### 1-1 CSS 颜色
+ 十六进制色(Hexadecimal colors)
> + 每个十六进制颜色由三部分组成
> + 前面两个字符代表红色的多少
> + 中间两个字符代表绿色的多少
> + 最后两个代表蓝色的多少
> 红 绿 蓝 这三种颜色，每一部分的取值范围都可以从16进制的 00 - FF，或者从十进制的 0 - 255

+ 十进制数的分解
> + 十进制数个位数字的取值范围是 0 - 9

+ 十六进制数的分解
> + 有时我们需要把十六进制数转化为十进制数
> + 只需要乘以十六power位数，位数从0开始慢慢增加从个位(16 power 0)到十位(16 power 1)，再到百位(16 power 2)，以此类推
> + 比如 23(十六进制) ，2 为十位数(16 power 1 = 16)，3 为个位数(16 power 0 = 1),2 x 16 + 3 x 1 = 35(十进制)
> + 十六进制数个位数字的取值范围是 0 - 15，但是 9 以上的数字用字母表示A(10) B(11) C(12) D(13) E(14) F(15)
> 例子: #030923，红 = (0 x 16 + 3 x 1) = 3 ，绿 = (0 x 16 + 9 x 1) = 9，蓝 = (2 x 16 + 3 x 1) = 35， 所以颜色的 CSS 十进制表示法是: rgb(3,9,35)

Example:
```
<!DOCTYPE html>
<html>
  <head>
    <style>
        /*关键字颜色*/
        h1{
            color:black;
        }
        /*十六进制颜色*/
        h2{
            color:#000000;
        }
        /*十进制颜色*/
        h3{
            color:rgb(0,0,0);
        }
    </style>
  </head>
  <body>
  </body>
</html>
```

#### css 颜色实用的功能
Example(origin):
```
<!DOCTYPE html>
<html>
  <head>
    <style type = "text/css">
        h1{
            color:#79B1A3;
        }
        h2{
            color:#79B1A3;
        }
        h3{
            color:#79B1A3;
        }
    </style>
  </head>
  <body>
  </body>
</html>
```
Example(shotcut):
```
<!DOCTYPE html>
<html>
  <head>
    <style type = "text/css">
        h1,h2,h3{
            color:#79B1A3;
        }
    </style>
  </head>
  <body>
  </body>
</html>
```
