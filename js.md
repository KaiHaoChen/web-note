视频链接：[【JavaScript核心基础_讲师（李立超）_JS教程】](https://www.bilibili.com/video/BV1mG411h7aD?vd_source=ef643319126f7224463297380162bd6c)
[toc]

# 基本语法
## 入门
### 注释
- 单行注释 //
- 多行注释 /*  内容 */

### 变量
- 声明变量： let  变量名
- 变量赋值： a = xxx
- 声明赋值 let 变量 = 值

### 常量
- 声明常量： const 常量名
- 常量声明后不能修改

### 标识符
- 标识符只能含有字母、数字、下划线、$、且不能以数字开头
- 不能使用js关键字和保留字
- 命名规范：驼峰命名（首字母大写，每个单词开头大写）

## 数据类型
### Number
- JS中的所有整数和浮点数都是Number类型
- Infinity 是一个特殊的数值表示无穷
- NaN 表示非法的数值
- 大整数使用n结尾

### 类型
- typeof 用来检查不同的值的类型

### 字符串
- 使用单引号和双引号来表示字符串
- 转义字符 \
- 模板字符串
```
- 使用反单引号表示 `
- 模板字符串可以嵌入变量
```

### boolean
- 布尔值只有两个true 和 false

### null
- 空值用来表示空对象

### undefined
- 声明变量没有赋值，它的值就是undefined

### symbol
- 用来创建唯一的标识

#### 类型转换
#### 字符串
- 调用toString()方法将其他类型转换为字符串
- 调用String()函数将其他类型转换为字符串

#### 数字
- 使用Number()函数来将其他类型转换为数值
```
- 字符串
    如果字符串是合法的数字则直接转换为数字
    如果字符串不是合法数字则转换为NaN
    如果字符串是空或空格，则转换为0
- 布尔
    true转换1   false转换0
- null转换0
- undefined转换为NaN

```
- parseInt() - 将字符串转换为整数
```
解析时，会自左向右读取字符串，直到读取字符串中的整数0
```
- parseFloat() - 将字符串转换为浮点数
#### 布尔
- 使用Boolean()函数来将其他类型转换为布尔值
```
数字：
    除了0和NaN 转换为false
    其余为true
字符串：
    空串转换为false
    其余为false
null和undefined 都转换为false
```

## 对象
```
- 添加属性：对象.属性名 = 属性值
- 读取属性：对象.属性名，如果没有返回undefined
- 删除属性 delete 对象.属性名

```
### 属性
- 属性名使用驼峰命名
- 使用[]去操作属性，可以使用变量

### 枚举对象
- for-in语句
- for-in有几个属性执行几次
```
for(let propName in 对象){

}
```
### 可变类型
- 当两个对象相等或者全等，比较的是内存地址
- 如果两个对象指向同一个对象，通过一个变量修改对象，例外一个也会影响

### 变量和对象
- 防止对象被重新赋值，！！使用const申明对象

### 方法
- 当一个对象的属性指向一个函数，那么我们就称这个函数是该对象的方法

### 序列化
- 对象转化为字符串
- JSON.stringify
- JSON.parse
- JSON.parse(JSON.stringify(obj))


## 函数
- 函数也是对象  
```
创建函数对象
    function() 函数名{}
调用函数
    函数对象（）
```

### 函数创建方式
- 函数申明
```
function() 函数名{}
```
- 函数表达式
```
const fn2 = function(){}
```
- 箭头函数
```
const fn3 = （）=> {}
```
### 函数参数
#### 参数定义
- 如果实参和形参的数量相同，则对应
- 如果实参多余形参，则多余的实参不会使用
- 如果形参多余实参，则多余的形参undefined

#### 箭头函数
- 当箭头函数只有一个参数时，可以省略（）
- 定义参数的时候可以指定默认值,没有传参是就使用默认值
```
const fn = (a=10) => {}

```
#### 对象参数
- 对象作为参数传递，传递的是内存地址

#### 函数参数
- 函数也是对象，也可以作为参数传递

### 函数返回值
- 使用return关键字来指定函数的返回值
- 箭头函数的返回值可以直接写在箭头后

### 作用域
- 全局作用域
```
- 全局作用域在网页运行时创建，在网页关闭时消耗
- 所有直接编写在script标签中的代码都位于全局作用域中
- 全局作用域中的变量，可以在任意位置访问
```
- 局部作用域
```
- 块作用域在代码块执行的时创建，代码块执行完毕他就销毁
- 块作用域声明的变量为局部变量，外部无法访问
```
- 函数作用域
```
- 函数作用域在函数调用时产生
- 函数定义的变量为局部变量
- 函数每次调用都是一个全新的作用域
```
### 作用域链
```
当我们使用一个变量时，js会优先使用当前作用域中的变量，如果没有找到则去上一层作用域寻找
```

### window对象
- 浏览器为我们提供window对象
- 除了window对象还负责存储js中的内置对象和浏览器的宿主对象
- window对象的属性可以通过window对象访问，也可以直接访问

### var
- 使用var定义的变量，都会作为window对象的属性保存
- 使用let声明的变量不会存储在window对象
- var虽然没有块作用域，但又函数作用域


### 提升
- 使用var声明的变量，他会在所有的代码执行前声明
- 函数声明创建的函数，会在其他代码执行前创建
- let声明的变量实际也提升，但是赋值之前禁止访问

### 立即执行函数
- 立即是一个匿名函数，它只会调用一次
```
(function(){}());
```
### 函数中的this
- this会指向一个对象
- this所指向的this会根据函数调用的方式不同而不同
```
- 以函数形式调用，this指向的是window
- 以方法的形式调用时，this指向的是调用方法的对象
```
- 箭头函数的this总是指向上一层作用域的this

### 严格模式
- "use strict"

### arguments
- arguments是一个隐含参数
- arguments是一个类数组对象
- arguments用来存储函数的实参

### 可变参数
- ...args

### call和apply
- 第一个参数为函数的this
- apply参数使用数组

### bind
- 创建一个新的函数
- 与call apply 指定this一样但是无法修改

### 闭包
- 闭包就是能访问到外部作用域的函数
- 函数嵌套
- 内部函数要引用外部函数的变量
- 内部函数要作为返回值返回
- 函数定义的时候已经确定了词法作用域

### 闭包注意
- 闭包在外部函数调用产生，外部函数每次调用都会产生一个全新的闭包    
- 内部函数丢失时销毁


## 面向对象
```
class Dog {

}
const d1 = new Dog()
```
### 属性
- 使用static声明的属性，是静态属性,只能通过类去访问
```
class Person {
    age
    name
}
```
### 方法
```
class Person {
    name = "ckh"

    sayHello(){

    }
}
```
### 构造方法
- constructor
- 构造函数会在调用类创建对象时执行
```
class Person {
    name
    constructor(name){
        this.name = name;
    }
}
```
### 封装
- 通过#将属性设置为私有
- 通过get set方法来操作属性
- 封装保证数据的安全
```
class Person {
    #name
    constructor(name){
        this.#name = name;
    }

    getName(){
        return this.#name;
    }

    setName(name){
        this.#name = name;
    }
}
```

### 多态
- 灵活性
```
function sayHello(obj){

}
sayHello(new Dog())
```

### 继承
- extend
- super 父类
- ocp开闭原则
```
修改关闭，扩展开放
```
```
class Animal {
    constructor(name){
        this.name = name
    }

    sayHello(){

    }
}

class Dog extend Animal {

}
```

### 对象结构
- 对象自身
- 原型对象_proto_  
```
1.在类中通过xxx(){}方式添加的方法
2.主动向原型中添加属性和方法
```
### 原型 ⭐
- 访问原型对象
```
对象.__proto__ 
Object.getPrototypeOf(对象)
```
- 原型对象中的数据
```
1.对象中的属性和方法
2.constructor

注意：原型对象也有原型
p对象 - 原型 - 原型 - null
obj对象 - 原型 - null
```
### 原型的作用
- 同类型的对象原型对象都是同一个
- 避免重复创建方法
- 继承：子类的原型就是父类

### 修改原型
- 注意：不能通过类的实例去修改原型
- 通过类的prototype属性

### instanceof和hasOwnProperty
- instanceof检查的时对象的原型链上是否有该类的实例
- hasOwnProperty用来检查一个对象是否有该属性

### 旧类
```
var Animal = (function(){
    function Animal(){

    }
    return Animal
})()

var Cat = (function(){
    function Cat(){

    }

    Cat.prototype = new Animal()
    return Cat
})()

```

### new
- 创建一个普通js对象
- 将构造函数的prototype属性设置为新对象的原型
- 使用实参来执行构造函数，并且将新对象设置为函数中的this

## 数组

### 数组长度
- arr.length

### 遍历数组
- for 循环 
- for-of
```
语法：for(变量 of 可迭代对象){

}
```
### 数组方法
- push() 数组末尾添加元素，返回新数组的长度
- pop() 删除最后一个元素并返回
- unshift() 数组开头添加元素
- shift（）数组开头删除元素
- splice()
```
参数：
1.删除的开始位置
2.删除的个数
3.插入的元素
```
- reverse() 反转数组
- Array.isArray()检查一个对象是否是数组
- concat 连接多个数组
- indexOf 获取元素在数组第一次出现的索引
- join 将数组的元素拼接一个字符串
- slice 截取字符串
```
参数：
1.截取的起始位置（包含）
2.截取的结束位置（不包含）
    第二个参数不写截取到最后
```

### 复制
- slice
- ...展开运算符
```
const arr = []
const arr2 = [...arr]
```
- Object.assign({},obj)
- {...obj}

### 浅拷贝和深拷贝
- 浅拷贝只对对象本身复制，不会复制对象中的属性
- 深拷贝不只复制对象本身，还复制对象中的属性和元素
- structuredClone（）深拷贝


## 内置对象
### Map
```
创建： new Map()
属性和方法：
    map.size()
    map.set(key,value)
    map.get(key)
    map.delete(key)
    map.has(key)
    map.clear()
```
### Set
```
set不能存储重复的数据
创建： 
    new Set()
    new Set([...])

方法：
    size()
    add()
    has()
    delete()

数组去重：
    new Set(arr)
    [...set]
```

### Math
```
Math.abs() 绝对值
Math.min() 
Math.max()

Math.floor() 向下取整
Math.ceil() 向上取整
Math.round() 四舍五入
Math.trunc() 去除小数

Math.random() 生成0-1的随机数
```
### Date
```
创建：
    new Date()
方法：
    getFullYear() 获取四位年份
    getMonth() 返回日期的月份（0-11）
    getDate() 返回日期的日
    getDay() 返回日期周几（0-6）
    Date.now()  getTime() 返回当前日期对象的时间戳 1970/1/1 到当前时间的毫秒数
格式化：
    toLocaleDateString 日期转为字符串
    toLocaleTimeString 时间转为字符串
```

### 字符串的方法
- 字符串本质是字符数组

```
属性和方法
length 字符串长度
字符串[索引]
concat 连接两个字符串
includes 检查字符串是否含有某个字符串
slice 切片
split 拆分数组
toLowerCase 小写
toUpperCase 大写
``` 

### 正则表达式
```
字面量创建：/正则/匹配模式
let re = /a|b/
re.test("ab")  

re.exec() 获取字符串符合正则字符串的内容
/a[a-z]c/g 全局匹配
```
```
let reg = new RegExp("a")
reg.test("ab")
参数
1.正则表达式
2.匹配模式    

```
- 正则表达式大部分字符可以直接写
- |表示或
- []表示字符集

```
[a-z] 任意的小写字母
[A-Z] 任意的大写字母
[a-zA-Z] 任意字母
[0-9] 任意数字

/[a-z]/
/[A-Z]/
/[a-zA-Z]/
/[a-z]/i 忽略大小写
```
- [^] 除了
```
/[^9]/ 除了9
```
- . 表示任意字符
- 正则表达式中\转义字符
- 开头和结尾
```
^ 开头
$ 结尾

/^a/ a开头
/a$/ a结束
/^a$/ 只匹配 a
```
- 量词
```
{m} m个
{m,} 至少m个
{m,n} m-n个
+ 一个以上，相当于{1，}
* 任意数量
? {0,1}
  

/a{3}/ 3个a
/^a+/
/^ba*$/
```

#### 字符串正则表达式
- split() 根据正则表达式拆分
- search() 搜索正则表达式第一次出现
- replace() 根据正则表达式替换内容

## DOM
### 文档节点
- document原型链
```
HTMLDocument -> Document -> Node -> EventTarget
```
- 部分属性
```
document.documentElement 根元素
document.head head元素
document.title title元素
document.body body元素
document.links 页面所有超链接 
```
### 元素节点
#### 获取元素节点
```
- document.getElementById() 通过id获取元素节点对象
- document.getElementsByClassName() 根据元素的class属性值获取元素
- document.getElementsByTagName() 根据标签名获取元素
- document.getElementsByName() 根据name属性获取（表单项）
- document.querySelectorAll() 根据选择器查询元素
  ！！不会实时更新
- document.querySelector 根据选择器返回第一个元素 
``` 
#### 元素节点属性方法
```
- element.childNodes 获取当前元素的子节点
- element.children 获取当前元素的子元素
- element.firstElementChild 获取当前元素第一个子元素
- element.lastElementChild 获取当前元素最后一个子元素 
- element.nextElementSibling 获取当前元素下一个兄弟元素
- element.previousElementSibling 获取当前元素上一个兄弟元素
- element.parentNode 获取当前元素的父节点

// 动态添加元素
const li = doucument.createElement("li")
li.textContent = "xx"
list.appendChild(li)

element.insertAdjacentElement()
// beforeend afterbegin beforebegin（元素前面） afterend(元素后面)

element.insertAdjacentHTML()

element.replaceWitch() 替换元素

element.remove() 删除元素

element.cloneNode() 复制节点

```

### 文本节点
```
修改文本三个属性
element.textContent 获取或修改元素中的文本
    - 不考虑css样式
element.innerText
    - 考虑css样式
element.innerHTML 获取或修改元素中的html代码
    - ！！！xss注入风险
```

### 属性节点
```
方式一：
    读取：元素.属性名 （class需要className读取）
    修改：元素.属性名 = 属性值
方式二：
    读取：元素.getAttribute(属性名)
    修改：元素.setAttribute(属性名，属性值)
    删除：元素.removeAttribute(属性值)
```

### 事件
- 在元素属性中设置
- 通过元素的指定属性设置回调函数来绑定事件(一个事件只能绑定一个函数)
- 通过元素addEventListener()绑定事件
```
<button click=""></button>

btn.addEventListtener("click",function(){

})
```
#### 事件对象
##### event
```
- event.target 表示触发事件的对象
```
##### 事件的冒泡
- 事件的冒泡就是指事件的向上传递
- 当元素的某个事件被触发后，其祖先元素的相同事件也会触发
- event.stopPropagation() 取消事件的冒泡
- 事件冒泡和样式无关，与结构相关

### 操作样式
#### 修改样式
- 元素.style.样式名 = 样式值
- 如果样式名有 - ，则使用驼峰
```
element.style.width = "90px";
```

#### 读取样式
- getComputedStyle() 返回生效的样式

#### class
```
element.classList.add()
element.classList.remove()
element.classList.toggle()
element.class.replace() 
```

p161