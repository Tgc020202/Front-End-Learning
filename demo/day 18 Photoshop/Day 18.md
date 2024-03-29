# Photoshop

###### 种类
1. 像素图
> + 占容量小，更天然
> + 格式:jpg,jpeg,png,gif

2. 矢量图
> +  更清晰，纯手工
> + 格式: ai


#### 使用 Photoshop
###### 创建文件
+ 这里有几个属性可以调试
> + ![创建文件的页面](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p1.PNG)
> + width 宽
> + height 高

+ 可以选择不同的背景 background content 这里有五个种类的背景
> + 白
> + 黑
> + 自选颜色
> + 透明
> + 自定义
+ ![创建文件的页面](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p2.PNG)

+ Photoshop 支持 copy and paste 将图片带入文件里
+ 可以通过 ctrl-c 复制, ctrl-n 新建文件, ctrl-v 粘贴快捷键 来截取图片的部分 并且另开一个文件夹

###### 保存图片
+ 有两种保存的方法
1. 保存/储存
> + 快捷键:ctrl + s
> + 直接把当前的更改储存为同一个文件，也就是说一旦保存了就变不回原来的图片了
2. 另存为
> + 快捷键:ctrl + shift + s
> + 说明另外新建一个文件，并且需要重新命名
+ ![保存文件的页面](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p3.PNG)

+ 保存下来的图片，未必是越大越好
+ 当我们用在网络的时候，图片越大，质量越好，但是会受于网络的限制，导致图片出现非常慢
+ 通常比较推荐 gif 格式
> + 因为 gif 格式 具备透明效果

###### 放大(zoom in)与缩小(zoom out)
+ ![文件的页面上方](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p5.PNG)
+ 可以通过 打开 view -> 找 zoom in 和 zoom out
+ ![放大镜图标](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p4.PNG)
+ 可以点左边的工具栏里的放大镜的小图标，然后可以更改上方的几个条件，找到自己想要的样式
+ 放大
> + 快捷键:ctrl++
+ 缩小
> + 快捷键:ctrl+-
+ 最有效率的快捷键: alt + 滑鼠的滚轮

###### 辅助线的使用
+ 可以通过 打开 view -> rulers
+ ![尺子的功能](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p6.PNG)
+ 可以从尺子的位子 用鼠标点击并拖动至想要测量的位置
+ 切勿这么做
+ ![错误使用尺子的功能](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p7.PNG)
+ 应该这么做，确保对齐，以保证准确率
+ ![正确示范尺子的功能](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p8.PNG)
+ 快捷键: ctrl + r

###### 图层 layer
+ ![图层工具栏](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p9.PNG)
+ 创建图层，点击右下角倒数第二的图标
+ ![图层工具栏](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p10.PNG)
+ 可以点击右下角的垃圾箱删除图层
+ 可以点击眼睛图标，代表暂时隐蔽图层
+ 图层的层级
> + 排得越上面的图层,层级越高
> + ![图层的层级的对比](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p11.PNG)
> + Layer 1 排的比 Layer 2 的高，所以 Layer 1 把 Layer 2 覆盖了
+ 可以直接点击图层并拖动图层来调整层级
> 锁头图标可以锁着图层，使此图层无法更改
+ 当我们要截图的时候一定要先选择对想要截的部分的图层，比如我要截 Layer 2 的动漫的脸，就要先选择 Layer 2
+ 我们也可以将图片合并(group)，这样的话就不用担心要选择什么图层了
> + ![合并示范](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p12.PNG)
+ 点击 windows -> History 可以看到之前我们更改的步骤
> + ![历史记录](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p13.PNG)
> + 可以通过点击这些步骤，进入回之前的步骤
> > + + ![历史记录的用法](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p14.PNG)

###### 字体的操作
+ 左边工具栏里的 T 图标
+ ![字体](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p15.PNG)
+ 直接拉伸就可以在里面打字了
+ 右边会出现一些工具帮助我们修改字体，且每一个字体都是独立的图层

###### 图片种类的认知
1. gif (graphic interchange format) 动态
> + 空间最小，很适合网络(优点)
> + 不是完美的透明，只是由256块的颜色组成
> + 在没有透明或透明过度的情况下 可以优先选择 gif 格式

2. jpg = jpeg (joint photographic experts groups)
> + 灵活，可以随意调尺寸(优点)
> + 不支持透明
> + 不支持动态

3. png (portable network graphic)
> + 完美透明(优点)
> + 不支持动态

###### 抠图的基本
+ 从左边的工具栏里点击一个毛笔形状的东西(quick selection tools)
+ ![抠图工具](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p16.PNG)
+ 鼠标右点击，选择下面的魔法棒
+ ![抠图工具](https://github.com/Tgc020202/Front-End-Learning/blob/main/demo/day%2018%20Photoshop/p17.PNG)

+ 上方会出现几个功能
1. 第一个新选区
2. 第二个增添到选区
3. 第三个从选区减去
4. 第四个是选择两个区块之间的区块

+ Tolerance(容差)
> + 可以使用颜色来分辨，如果容差越大，截下来的图片越模糊
+ 取消选区的快捷键: ctrl + d
+ 反选的快捷键: shift + ctrl + i

###### 选取框的基本
+ 选取的快捷键: 在图层 按 ctrl + 点击那个图层
+ 左边的工具栏里 类似钢笔的图标
> + 慢慢调节，比较精准
> + 标记完后，点击 ctrl + 回车键
