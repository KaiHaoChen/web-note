视频链接：https://www.bilibili.com/video/BV1XJ411X7Ud/ 
[toc]

# 使用css
- 内联样式：在标签内部使用style属性来设置元素的样式
- 内部样式：将样式写在style标签里
- 外部样式：css样式编写一个css文件，通过link标签引入css文件
```
内联样式：开发时绝对不要使用内联样式
内部样式：更加方便服用
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
```css
:first-child 第一个子元素
:last-chile 最后一个子元素
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

```css
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

```css
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