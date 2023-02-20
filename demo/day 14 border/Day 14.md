## css border 边框
+ 占元素的大小，是往外长的
+ 用法:
```
/*有border 实线 颜色 非缩写*/
.borderDefault {
/*宽度*/
border-width: 20px;
/*颜色*/
border-color: aquamarine;

/*border的线的种类*/
border-style: solid;

/*
也可以更准确的设置属性
border-方向-width: 宽度;
border-方向-color: 颜色;
*/
border-top-width: 40px;
border-top-color: red;

border-right-width: 80px;
border-right-color: orange;

border-bottom-width: 120px;
border-bottom-color: green;

border-left-width: 160px;
border-left-color: lightskyblue;
}
```

+ 缩写用法: border: 大小 颜色 线的种类;
+ 线的种类: 实线(solid)，虚线(dotted,dashed)
+ 颜色: rgb(), #, 颜色名称

Example:
```
/*有border 实线*/
.borderNode {
width: 200px; height: 200px;background-color: #17b978;
border:10px solid black;
}
/*有border 虚线*/
.dotborderNode {
width: 200px; height: 200px;background-color: #17b978;
border:10px  dotted black;
}
.dashborderNode {
width: 200px; height: 200px;background-color: #17b978;
border:10px  dashed black;
}

/*有border 实线 颜色*/
.bordercolor1 {
width: 200px; height: 200px;background-color: #17b978;
border:10px solid rgb(22, 134, 214);
}
.bordercolor2 {
width: 200px; height: 200px;background-color: #17b978;
border:10px solid #05bd20;
}
```
