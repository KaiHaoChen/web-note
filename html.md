视频链接：https://www.bilibili.com/video/BV1XJ411X7Ud/ 
[toc]

# 注释
```
    <!-- 我是一个注释 -->
```
- 养成写注释的习惯
- 注释简单明了
- 注释不能嵌套

# 标签的属性
```
    <font color="yellow">属性</font>
```

- 属性只能在开始标签或自结束标签
- 属性为键值对 （x = y）
- 属性和标签名或其他属性应该使用空格隔开

# 文档声明
- h5说明写在开头
```
<!DOCTYPE html> 
```

# 实体（转义字符）
- 在网页编写中浏览器会将多个空格默认解析为一个空格
```
空格：&nbsp;
大于号：&gt;
小于号：&lt;
```

# meta
- 主要用于设置网页的元数据
- charset 网页字符集
- name 指定的数据名称
- content 指定的数据内容

```
    <!-- 网站关键字 -->
    <meta name="keywords" content="H5,前端，css"> 

    <!-- 网站描述 -->
    <meta name="description" content="这是非常不错的网站">

    <!-- 网站重定向 -->
    <!-- 三秒后跳转百度 -->
    <meta http-equiv="refresh" content="3;url=https：//www.baidu.com">
```

# 块元素和行内元素
- 块元素（block element）:网页中用来布局
- 行内元素（inline element）：用来包裹文字
- 一般情况会在块元素中放行内元素

# 语义化标签
- header 网页头部
- main 网页主体
- footer 网页底部
- nav 网页导航
- aside 侧边栏
- article 独立的文章
- section 独立模块
- div 常用布局元素
- span 行内元素

# 列表
- ul：无序列表
- ol：有序列表
- li：列表项
- dl：自定义列表
- dt：定义的内容
- dd：对内容解释说明

```
    <ul>
        <li>html</li>
        <li>css</li>
        <li>js</li>
    </ul>
    <ol>
        <li>html</li>
        <li>css</li>
        <li>js</li>
    </ol>
```

# 超链接
- 超链接是一个行内元素
- 属性href指定跳转的路径

```
    <!-- 超链接 -->
    <a href="https://www.baidu.com">baidu</a>
```

# 相对路径
- ./ 可以省略（默认）
- ./ 表示当前文件所在的目录
- ../ 表示当前文件所在目录的上一级目录

# 图片标签
- img属于替换元素
- src:指定的是外部图片的路径
- alt:图片描述，图片默认显示不出来显示描述
- 图片高度和宽度中如果只修改一个，另外一个会等比缩放
```
<img src="./img/1.gif" alt="图片描述">
```

# 内联框架
- 用于向当前页面中引入一个其他页面
- src：指定引入网页的路径
- frameborder：指定内联框架的边框

```
<iframe src="https://www.baidu.com" frameborder="0"></iframe>
```

# 音频视频
- video：引入一个外部视频文件
- audio：引入一个外部的音频文件
- controls：是否允许用户控制播放
- autoplay：是否自动播放
- loop：循环播放
```
    <audio src="123" controls autoplay></audio>
```