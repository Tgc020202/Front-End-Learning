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

```
