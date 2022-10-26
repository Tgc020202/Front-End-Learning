## 1-3 html 文本格式化标签(Doc Format)

#### 1-3-1 b
+ b 标签标识 以粗体字形式展示内容

Example:
```
<span>这是正常字体</span>
<b>这是粗体字体</b>
```

#### 1-3-2 strong
+ strong 标签与 b 标签都表示粗体，但是 strong 表示强调。
+ 例如，一个单词或短语需要显示的更高调，更响亮...总之比一般的文本更为突出。这里我们就使用 strong 标签在SEO 中的应用，告知搜索引擎我们内容强调的是什么。
Example:
```
<span>这是正常字体</span>
<strong>这是粗体字体</strong>
```

#### 1-3-3 i
+ i 标签表示以斜体字体形式展现内容
Example:
```
<span>这是正常字体</span>
<i>这是斜体字体</i>
```

#### 1-3-4 em
+ em 标签告诉浏览器把其中的文本表示为强调的内容 并以斜体形式展现
Example:
```
<span>这是正常字体</span>
<em>这是强调的斜体字</em>
```

#### 1-3-5 pre
+ pre 标题可定义预格式化的文本。
+ 被包围在 pre 标签 元素中的文本通常会保留空格和换行符
+ 而文本也会呈现为等宽字体
Example:
```
<span>这是 span 标签    中间空格将不会被保留</span><br />
<pre>这是 pre 标签      中间空格将被保留</pre>
```

#### 1-3-6 small
+ small 标签 定义小型文本
Example:
```
<span>这是正常字体</span><br />
<small>这是小型文本</small>
```

#### 1-3-7 sub
+ sub 标签定义下标文本
+ 下标文本将会显示在当前文本流中字符高度的一般为基准线的下方
Example:
```
<span>这是正常字体</span><sub>这是下标文本</sub>
```

#### 1-3-8 sup
+ sup 标签定义上标文本
+ 上标文本将会显示在当前文本流中字符高度的一般为基准线的上方
Example:
```
<span>这是正常字体</span><sup>这是上标文本</sup>
```

#### 1-3-9 q
+ 短文本引用注意要引用的文本不用加双引号，浏览器会对 q 标签自动添加双引号
Example:
```
<q> 小朋友 </q>
```

#### 1-3-10 address
+ 加入地址信息，一般地址会和联系方式等东西放在一起，最好是用 div 标签放在同一个模块内
Example:
```
<div>
  <address>地址</address>
</div>
```

#### 1-3-11 caption
+ 为表格添加标题和摘要
+ tr 是列，th 是行
Example:
```
<table>
  <caption>摘要</caption>
  <thead>表头</thead>
    <tr>
      <th>[1,1]</th>
      <th>[1,2]</th>
    </tr>
    <tr>
     <th>[2,1]</th>
     <th>[2,2]</th>
    </tr>
    <tbody>
      <th>aaa</th>
      <th>bbbb</th>
    </tbody>
</table>
```
