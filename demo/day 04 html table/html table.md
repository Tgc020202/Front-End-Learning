## 3-0 Table

#### 3-1 Table 基础
+ 在 HTML 中 table 标签表示一个表格，每个表格均有若干行(由 tr 标签定义)，每行被分割为若干单元格(由 td 标签定义)
+ Table 表格属性：
>  + border:设置表格边框
>  + width:设置表格宽度
>  + align:设置表格对齐
>  + cellpadding:设置单元格间距
>  + cellspacing:设置像素间隙

Example:
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset = "utf-8">
        <meta name = "viewport" content = "width=device-width,initial-scale=1">
        <title>table 属性</title>
    </head>

    <body>
        <table width = "100%" border = "1" style = "text-align: center;" cellspacing = "0">
            <!-- text-align:center表中文字的格式未居中 -->
            <thead> <!-- 表头 -->>
                <tr>
                    <td>主题</td>
                    <td>主题</td>
                    <td>主题</td>
                </tr>
            </thead>
            <tbody> <!-- 表身 -->
                <tr>
                    <td>主题2</td>
                    <td>主题2</td>
                    <td>主题2</td>
                </tr>
            </tbody>
            <tfoot> <!-- 页脚 -->
                <td>页脚</td>
                <td>页脚</td>
                <td>页脚</td>
            </tfoot>
        </table>
    </body>
</html>
```

#### 3-2 rowspan 跨行合并/colpan 跨列合并
Example:
```
<!DOCTYPE html>
<html>
    <head>
        <title>表格的合并</title>
    </head>
    <body>
        <!-- 
            有两种合并的方式
            rowspan:跨行合并
            colspan:跨列合并
        -->
        <table width = "100%" border = "1" style = "text-align: center;" cellspacing = "0">
            <caption>Table的合并</caption>
            <tbody>
                <tr>
                    <td colspan = "5">合并了5列</td>
                </tr>
                <tr>
                    <td rowspan = "3">2</td>
                    <td>2</td>
                    <td>2</td>
                    <td>2</td>
                    <td>2</td>
                </tr>
                <tr>
                    <td>3</td>
                    <td>3</td>
                    <td>3</td>
                    <td>3</td>
                </tr>
                <tr>
                    <td>4</td>
                    <td>4</td>
                    <td>4</td>
                    <td>4</td>
                </tr>
            </tbody>
        </table>
    </body>
</html>
```

#### 3-3 Table 样式
+ 表格边框：为了使边框出现边框(基于样式)，可以添加如下样式
Example:
```
table,th,td{border: 1px solid blue}
```
+ 表格文本对齐针对表格文本，可以对其设置对齐方式:
> + text-align:设置水平方向对齐方式
> + vertical-align:设置垂直方向对齐 left : 默认值，水平方向向左对齐
> + center:水平方居中对齐
> + right:水平方向右对齐
Example:
```
/* css */
/* 右对齐 */
td{text-align:right;}
vertical-align: 设置垂直方向对齐方式
top: 垂直方向顶端对齐
middle: 垂直方向中部对齐
bottom: 垂直方向底端对齐

/* 底端对齐 */
td{vertical-align:bottom;}
```
> + 消除边框用: border-collapse:collapse;
> + 设置奇数项: table tr:nth-child(odd){}
> + 设置偶数项: table tr:nth-child(even){}

Example:
```
<!DOCTYPE html>
<html>
    <head>
        <title> Css 表格样式 </title>
        <style type = "text/css">
            .table{
                margin: 0px auto;
                text-align: center;
                width: 90%;
                border_collapse: collapse;  /* 折叠边框 */
            }

            table td,
            table th{
                border: 1px solid #cad9ea;
                height: 30px;
            }

            table thead th{
                background-color: #cce8eb;
                width: 100px;
            }
            /* 颜色交替显示 */
            table tr:nth-child(odd) /* 选定表格的奇数项 */{
                background-color: orange;
            }
            table tr:nth-child(even)/* 选定表格的偶数项 */{
                background-color: blue;
            }    
        </style>
    </head>
    <body>
        <table class = "table">
            <caption>
                <h2>Table的样式设置</h2>
            </caption>
            <thead>
                <tr>
                    <th>课程</th>
                    <th>成绩</th>
                    <th>班级</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>111</td>
                    <td>222</td>
                    <td>333</td>
                </tr>
                <tr>
                    <td>444</td>
                    <td>555</td>
                    <td>666</td>
                </tr>
                <tr>
                    <td>777</td>
                    <td>888</td>
                    <td>999</td>
                </tr>
                <tr>
                    <td>1111</td>
                    <td>2222</td>
                    <td>3333</td>
                </tr>
                <tr>
                    <td>4444</td>
                    <td>5555</td>
                    <td>6666</td>
                </tr>
                <tr>
                    <td>7777</td>
                    <td>8888</td>
                    <td>9999</td>
                </tr>
            </tbody>
        </table>
    </body>
</html>
```

## 4-0 Form 表单
> + 表单是一个包含单元素的区域，允许用户在表单中(比如:文本域，下拉列表，单选框，复选框等等)输入信息的元素
> + 单表是一个块级元素
> + 功能:获取用户的输入信息 用于向服务器传输数据 从而实现用户与 web 服务器的数据交互
+ 表单常用属性
> + name 属性: 规定表单的名称
> + action 属性: 规定当提交表单时，向何处发送表单数据
> + method 属性: 规定如何发送表单数据(表单数据发送到 action 属性所规定的页面)，常见的用 post，get 方式请求
+ HTML 表单元素
> + input 行内元素
> + textarea
> + button
> + select

| input type 属性值 | 表现形式 |
| type | 单行输入文本 |
| password | 单行输入文本 |
| button | 代表普通按钮 可以触发事件 |
| reset | 重置按钮 |
| submit | 提交按钮 能够自动触发 form 表单的提交动作 |
| image | 图片提交按钮 |
| checkbox | 复选框 |
| radio | 单选框 |
| file | 文本选择框 |
| hidden | 隐藏输入框 |
| date | 日期输入框 可以选择日期 |

+ input 根据不同的 type 属性，可以变化为多种状态输入方式:
+ input 标签 type 属性值:
> + input type = "text": 定义供文本输入的单行输入字段
> + input type = "password": 定义密码字段
> + input type = "submit": 定义提交表单数据至表单处理程序的按钮
> + input type = "image": 定义图片提交按钮
> + input type = "radio": 定义单选按钮
>> + checked: 属性为选中状态，不管值为多少
> + input type = "checkbox": 定义复选框
>> + checked: 属性为选中状态，不管值为多少
> + input type = "button": 定义普通按钮
> + input type = "reset": 定义重置按钮
> + input type = "file": 定义文件框
> + <input type = "text" />:定义供文件输入的单行输入字段
> + <input type = "password" />: 定义密码字段
> + <input type = "submit" />: 定义提交表单数据至表单处理程序的按钮
> + <input type = "image" />: 定义图片提交按钮
> + <input type = "radio" />: 定义单选按钮
>> + checked: 属性为选中状态，不管值为多少
> + <input type = "checkbox" />: 定义复选框
>> + checked: 属性为选中状态，不管值为多少
> + <input type = "button" />: 定义普通按钮
> + <input type = "reset" />: 定义重置按钮
> + <input type = "file" />: 定义文件框
> + *placeholder* 表示输入框内的默认值，用户直接输入内容，默认内容会消失。value 属性也可以有默认字体，但是用户需要删除字体才能填写
> + input 也是行内元素，需要转换为块级元素才可以设置宽高

Example:
```
<!DOCTYPE html>
<html>
    <head>
        <title>Form 表单元素的学习</title>
    </head>
    <body>
        <form action = "#" name = "myForm">
            <p>用户名:
                <input type = "text" name = "username" value = "筱朋友">
            </p>  <!-- value 为默认值 -->
            <p>密 码:
                <input type = "password" name = "pwd">
            </p>
            <p>按 钮:
                <input type = "button" value = "普通的按钮"><br>
                <button style = "cursor:pointer">按钮</button>  <!-- 鼠标放上去就会有一个小手掌 -->
            </p>
            <p>
                <input type = "image" src = "image18.jpg" id = "img" style = "width:400px;height:300px">
                <input type = "submit" name = "提交按钮">
            </p>
            <p>重置按钮:
                <input type = "reset" name = "重置按钮">
            </p>
            <p><input type = "date" name = ""></p>
            <p>复选框:
                <input type = "checkbox" checked = "checked" name = "hobby">散步
                <input type = "checkbox" name = "hobby">打球
                <input type = "checkbox" name = "hobby">玩游戏
            </p>
            <p>性别:
                <input type = "radio" name = "sex">男
                <input type = "radio" name = "sex">女
            </p>
        </form>
    </body>
</html>
```
