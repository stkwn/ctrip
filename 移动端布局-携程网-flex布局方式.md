# 移动端布局-携程网-flex布局方式

### 1 设置文件夹，导入样式表

主要包含了css文件夹、images文件夹、upload文件夹，还有建立index.html

css: 初始化样式表

导入样式表

### 2 search-index模块

采用固定定位。**注意：**

**- 固定的盒子要有宽度。**

**- 固定定位跟父亲没有关系，以屏幕为主。**

所以要设置min-width：320px ； max-width：540px

固定定位的盒子，margin 居中对齐的方式是失效的；所以要用算法。

```html
.search-index {
	position: fixed;
	top: 0px;
    left:50%;
    transform:translateX(-50%)
    //如果要写left，就要写transform，否则也是居中对齐的
	width:100%;
	min-width: 320px;
	max-width: 540px;
	height:44px;
	background-color: pink;
    
}


```

父盒子设置了flex布局，子元素不管是什么元素，都可以设置宽高。

右边子元素固定，左边可伸缩，可以给左边子元素设置flex：1；

移动端精灵图的做法：
先按等比缩放成原来的一半大小；
选择图标，记录图标大小;
还要记录图片的坐标。写到css里，要用负的；

--------------------

![64240086136](D:\01studyPrintMaterials\01Markdown笔记\images\ctrip\ctrip01)

这种布局就是UL里面放5个li 。 ul 是弹性布局； li是flex：1；每个li里面是1个a

每个a：上面一个span标签用背景图；下面一个span放文字。

![64240106673](D:\01studyPrintMaterials\01Markdown笔记\images\ctrip\ctrip02.jpg)

这5个span可以分别起类名：.local-nav-icon-icon1 ~ .local-nav-icon-icon5
他们都是以.local-nav-icon开头的，可以学习属性选择器。
.local-nav li [class^=".local-nav-icon"] {集体声明样式}
.local-nav li .local-nav-icon-icon2 { background-position:0 -32px};
.local-nav li .local-nav-icon-icon3 { background-position:0 -64px};
...
通过这种方式，可以修改每个图标背景图片的位置。
但是用JavaScript更容易实现。

-------------------

![64240780851](D:\01studyPrintMaterials\01Markdown笔记\images\ctrip\ctrip03.jpg)

一个大盒子nav，里面有3个小盒子nav-common。每个nav-common 还有3个盒子 ，采用flex布局。



.nav-items:nth-child(-n+2) {}   //-n+2就是前面2个盒子。

3倍背景图 。设置背景图的时候，先除3，把background-size设置为除以3之后的。

渐变色：

background: -webkit-linear-gradient(left, #FA5A55, #fa994D);













