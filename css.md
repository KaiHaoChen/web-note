视频链接：https://www.bilibili.com/video/BV1XJ411X7Ud/ 
[toc]

# 使用css
- 内联样式：在标签内部使用style属性来设置元素的样式
- 内部样式：将样式写在style标签里
- 外部样式：css样式编写一个css文件，通过link标签引入css文件
```
内联样式：开发时绝对不要使用内联样式
内部样式：更加方便使用
外部样式：
    <link rel="stylesheet" href="./style.css">
```

# 注释
```
        /* css注释 */
```

# 基本语法
- 选择器：通过选择器可以选中页面中的指定元素
- 声明块：通过声明块来指定为元素设置的样式

```
声明块由一个一个的声明组成
声明是一个名值对结构
        一个样式名对应一个样式值，名和值之间以:连接，以;结尾
```

# 选择器
## 元素选择器
- 作用：根据标签名来选中指定的元素
- 语法：标签名{}
- 例子：p{} h1{} div{}
```css
      p {
            color: red;
        }
```

## id选择器
- 作用：根据元素的id属性值选中一个元素
- 语法：#id属性值{}
- 例子：#box{} #red{}
```css
      #red{
            color: red;
        }
```

## 类选择器
- 作用：根据元素的class属性值选中一组元素
- 语法：.class属性值
- 多个class用空格隔开
```css
      .test {
            color: red;
        }
```
## 复合选择器

### 交集选择器
- 作用：选中同时复合多个条件的元素
- 语法：选择器1选择器2选择器n{}
- 注意：交集选择器如果有元素选择器，必须使用元素选择器开头
```css
        div.red {
            color:red;
        }
```
### 并集选择器
- 作用：同时选择多个选择器对应的元素
- 语法：选择器1，选择器2，选择器n{}
```css
      h1,span {
            color: red;
        }

```

## 关系选择器

### 子元素选择器
- 作用：选中指定父元素的指定子元素
- 语法：父元素 > 子元素
```css
     div > span {
            color: red;
        }
```

### 后代元素选择器
- 作用：指定指定元素内的指定后代元素
- 语法：祖先 后代
```css

        div span {
            color: red;
        }
```

### 兄弟选择器
- 作用：选择下一个兄弟 
- 语法：前一个 + 后一个

- 作用：选择下面所有的兄弟
- 语法：兄 ~ 弟
```css

        p + span {
            color: red;
        }

        p ~ span {
            color: red;
        }
```

## 属性选择器
- [属性名] 选择含有指定属性的元素

```css
        [title] {
            color: red;
        }
```
- [属性名=属性值] 选择含有指定属性和属性值的元素
```css
        [title=a] {
            color: red;
        }
```

- [属性名^=属性值] 选择属性值以指定值开头的元素
```css
        [title^=a] {
            color: red;
        }
```

- [属性名￥=属性值] 选择属性值以指定值结尾的元素
```css
        [title$=b] {
            color: red;
        }
```
- [属性名*=属性值] 选择属性值中含有某值的元素的元素
```css

        [title*=a] {
            color: red;
        }
```

## 伪类
### 伪类选择器
- 伪类用来描述一个元素的特殊状态
- 比如：第一个元素、被点击的元素、鼠标移入的元素
- 伪类一般情况下使用：开头
```text
:first-child 第一个子元素
:last-child 最后一个子元素
:nth-child() 选中第n个子元素
    n 第n个元素
    2n 或 even 表示选中偶数位的元素
    2n+1 或 odd 表示选中奇数位的元素

以下伪类在相同元素中进行排序
:first-of-type
:last-of-type
:nth-of-type()


        ul > li:first-child {
            color: red;
        }

        ul > li:last-child {
            color: blue;
        }

        ul > li:nth-child(3) {
            color: green;
        }

        
        ul > li:first-of-type {
            color: red;
        }
```
### 超链接伪类
- 没有访问过的链接
- 访问过的链接

```text
:link:没访问过的链接
:visited:访问过的链接（只能修改颜色）
:hover：用来表示鼠标移入的状态
:active：用来表示鼠标点击

        a:link {
            color: red;
        }

        a:visited {
            color: blueviolet;
        }

        a:hover {
            color: orange;
        }

        a:active {
            color: chartreuse;
        }
```
### 伪元素
- 表示页面中一些特殊的并不真是存在的元素
- 伪元素使用：：

```text
::first-letter 表示第一个字母
::first-line 表示第一行
::selection 表示选中内容
::before 元素的开始
::after 元素的最后
    - before和after结合content属性使用

        p::first-letter {
            color: red;
        }

        p::first-line {
            color: yellow;
        }

        p::selection {
            color: aqua;
        }

        div::before {
            content: 'abc';
        }

        div::after {
            content: 'efg';
        }

```

## 餐厅练习（选择器练习）
https://flukeout.github.io/
```text
1.plate
2.bento
3.#fancy
4.plate > apple
5.#fancy > pickle
6.apple.small
7.orange.small
8.bento > orange.small
9.plate,bento
10.plate,apple,bento,orange
11.plate > pickle,plate > apple ,plate > orange
12.plate + apple
13.bento ~ pickle
14.plate > apple
15.plate > orange:first-child
16.plate > apple , plate > pickle
17.apple,pickle
18.plate:nth-child(3)
19.bento:first-of-type
20.apple:first-of-type
21.plate:nth-child(even)
22.plate:nth-child(3),plate:nth-child(5)
23.plate:nth-child(2) > apple
24.orange:last-of-type,apple:last-of-type
25.bento:empty
26.apple:not(.small)
27.[for]
28.plate[for]
29.bento[for=Vitaly]
30.[for^=Sa]
31.[for$=ato]
32.[for*=obb]
```

## 继承
- 元素设置的样式同时也会应用到他的后代元素上
- 继承是发生在祖先后代之间
- 继承的设计是为了方便我们的开发
- 背景相关，布局相关的这些样式不会被继承
  
## 选择器的权重
- 优先级越高，越优先显示
- 如果优先级计算相同，则优先使用靠下的样式
- 可以在某一个样式后边添加！important,此时该样式会获取到最高优先级，慎用！！

```text
- 内联样式 1000
- id选择器 100
- 类和伪类选择器 10
- 元素选择器    1
- 通配选择器 0
- 继承的样式 没有优先级
```
 ## 单位
```text
像素
百分比
    - 相对于父元素属性的百分比
em
    - 相对于元素字体大小
    - 1em = 1font-size
    - em会根据字体大小的改变而改变
rem
    - rem是相对于根元素的字体大小

```
## 颜色
```text
css中可以直接使用颜色名来设置各种颜色
RGB通过三种颜色的不同浓度来调配不同的颜色
RGB
    - R red 、 G green 、 B blue
    - 每一种颜色的范围在 0 - 255（0% - 100%）之间
    - 语法:RGB(红色,绿色,蓝色)
RGBA
    - 在rgb基础上增加a透明度
    - 1表示完全不透明 0表示完全透明 .5半透明
十六制RGB
    - 语法：#红色绿色蓝色
    - 颜色浓度 00-ff
    - 如果颜色两位重复可以简写
```

## 文档流
- 网页是一个多层结构
- css可以分别为每一层设置样式
- 最底下的一层称为文档流，文档流是网页的基础
```text
- 元素在文档流
- 元素脱离文档流

- 块元素
    a.块元素会在页面中独占一行（自上向下垂直排列）
    b.默认宽度是父元素的全部（会把父元素撑满）
    c.默认高度是被内容撑开（子元素）

- 行内元素
    a.行内元素不会独占页面的一行，只占自身的大小
    b.行内元素从左到右水平排列，如果一行之内不能容纳所有的行内元素则元素会换到第二行继续排列
    c.行内元素的默认宽度和高度都是被内容撑开
```

## 盒子模型
- css将页面中的所有元素都设置为一个矩形的盒子
- 对页面的布局就变成了将不同盒子摆放不同位置
- 每一个盒子都有几个部分组成：
      - 内容区（content）
      - 边框（border）
      - 内边距（padding）
      - 外边距（margin）


### 盒子模型-边框（border）
- 边框的宽度 border-width
```text
- 默认值 一般3个像素
- 指定四个方向的边框宽度 
    a.上 右 下 左
    b.上 左右 下
    c.上下 左右
    d.上下左右 
- 也可以border-xxx-width xxx可以是top right left bottom
```
- 边框的颜色 border-color
```text
- 用来指定四个边的边框颜色，规则同border-width一样
- 可以省略不写，自动使用color的值 
```
- 边框的样式 border-style
```text
默认值:none

solid 实线
dotted 点状虚线
dashed 虚线
double 双线
```
- border简写属性
```text
没有顺序要求，空格隔开就行
```
### 盒子模型-内边距（padding）
- 内容区和边框之间的距离是内边距
- 一共有四个方向的内边距
- 内边距会影响盒子的大小
- 背景颜色会延申到内边距上
- padding属性简写
```text
规则和border-width 一样
```
### 盒子模型-外边距（margin）
- 外边距不会影响盒子可见框的大小
- 外边距会影响盒子位置
```text
margin-top：设置正值，元素会向下移动
margin-right：默认情况设置margin-right不会产生任何效果
margin-bottom：设置正值，下边的元素会向下移动
margin-left：设置正值，元素会向右移动

margin简写：上 右 下 左
```

### 盒子水平布局
由以下几个属性决定
- margin-left
- border-left
- padding-left
- width
- padding-right
- border-right
- margin-right

以上元素相加 = 其父元素内容区的宽度（必须满足）

```text
- 如果等式不成立，则称为过度约束，则等式会自动调整

调整情况：
    - 如果七个值中没有auto的情况，则浏览器会自动调整margin-right以等式满足
    - 这七个值中有三个值设置为auto
      width
      margin-left
      margin-right
      - 如果某个值为auto,则会自动调整为auto的那个值以使等式成立

      - 如果宽度和外边距都为atuo，优先宽度
      - 如果两个外边距都为auto,则居中;（margin:0 auto;）
```

### 盒子垂直布局
- 默认情况下父元素的高度被内容撑开
- 如果子元素的大小超过父元素，则子元素就会从父元素溢出
- 使用overflow属性来设置溢出的子元素

```text
可选值：
    visible：默认值 子元素从父元素溢出，在父元素外部显示
    hidden：溢出的内容将会被裁剪
    scroll：生成滚动条
    auto：根据需要生成滚动条

overflow-x overflow-y 水平垂直方向单独判断
```
### 垂直外边距的重叠
- 兄弟元素
```text
兄弟元素间的相邻垂直外边距会取两者之间的较大值
```
- 父子元素
```text
父子元素相邻外边距，子元素会传递给父元素（上外边距）
```
### 行内元素盒子模型
- 行内元素不支持高度和宽度
- 行内元素设置padding border margin 垂直方向不影响页面布局
```text
display 用来设置元素显示的类型
    可选值：
        inline 将元素设置为行内元素
        block 将元素设置为块元素
        inline-block 将元素设置为行内块元素（既可以设置宽度和高度又不会独占一行）
        table 将元素设置为表格
        none 元素不在页面显示

visibility 用来设置元素的显示状态
    可选值
        visible 默认值
        hidden 元素隐藏但占据位置
```