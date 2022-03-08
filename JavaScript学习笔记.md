JavaScript学习笔记
==================

0、前端知识体系
---------------

想要成为真正的“互联网Java全栈工程师”还有很长的一段路要走，其中前端是绕不开的一门必修课。本阶段课程的主要目的就是带领Java后台程序员认识前端、了解前端、掌握前端，为实现成为“互联网Java全栈工程师”再向前迈进一步。

### 0.1、前端三要素

- HTML（结构）：超文本标记语言（Hyper Text Markup Language），决定网页的结构和内容
- CSS（表现）：层叠样式表（Cascading Style Sheets），设定网页的表现样式。
- JavaScript（行为）：是一种弱类型脚本语言，其源码不需经过编译，而是由浏览器解释运行，用于控制网页的行为

### 0.2、结构层（HTML）

太简单，略

### 0.3、表现层（CSS）

CSS层叠样式表是一门标记语言，并不是编程语言，因此不可以自定义变量，不可以引用等，换句话说就是不具备任何语法支持，它主要缺陷如下：

- 语法不够强大，比如无法嵌套书写，导致模块化开发中需要书写很多重复的选择器；
- 没有变量和合理的样式复用机制，使得逻辑上相关的属性值必须以字面量的形式重复输出，导致难以维护； 这就导致了我们在工作中无端增加了许多工作量。为了解决这个问题，前端开发人员会使用一种称之为【CSS预处理器】的工具,提供CSS缺失的样式层复用机制、减少冗余代码，提高样式代码的可维护性。大大的提高了前端在样式上的开发效率。

#### 什么是CSS预处理器

CSS预处理器定义了一种新的语言，其基本思想是，用一种专门的编程语言，为CSS增加了一些编程的特性，将CSS作为目标生成文件，然后开发者就只需要使用这种语言进行CSS的编码工作。转化成通俗易懂的话来说就是“用一种专门的编程语言，进行Web页面样式设计，再通过编译器转化为正常的CSS文件，以供项目使用”。

##### 常用的CSS预处理器有哪些

- SASS：基于Ruby ，通过服务端处理，功能强大。解析效率高。需要学习Ruby语言，上手难度高于LESS。
- LESS：基于NodeJS，通过客户端处理，使用简单。功能比SASS简单，解析效率也低于SASS，但在实际开发中足够了，所以如果我们后台人员如果需要的话，建议使用LESS。

### 0.4、行为层（JavaScript）

JavaScript一门弱类型脚本语言，其源代码在发往客户端运行之前不需要经过编译，而是将文本格式的字符代码发送给浏览器，由浏览器解释运行。

#### JavaScript框架

- JQuery：大家熟知的JavaScript库，优点就是简化了DOM操作，缺点就是DOM操作太频繁，影响前端性能；在前端眼里使用它仅仅是为了兼容IE6，7，8；
- Angular：Google收购的前端框架，由一群Java程序员开发，其特点是将后台的MVC模式搬到了前端并增加了模块化开发的理念，与微软合作，采用了TypeScript语法开发；对后台程序员友好，对前端程序员不太友好；最大的缺点是版本迭代不合理（如1代–>2 代，除了名字，基本就是两个东西；截止发表博客时已推出了Angular6）
- React：Facebook 出品，一款高性能的JS前端框架；特点是提出了新概念 【虚拟DOM】用于减少真实 DOM 操作，在内存中模拟 DOM操作，有效的提升了前端渲染效率；缺点是使用复杂，因为需要额外学习一门【JSX】语言；
- Vue：一款渐进式 JavaScript 框架，所谓渐进式就是逐步实现新特性的意思，如实现模块化开发、路由、状态管理等新特性。其特点是综合了 Angular（模块化）和React(虚拟 DOM) 的优点；
- Axios：前端通信框架；因为 Vue 的边界很明确，就是为了处理 DOM，所以并不具备通信能力，此时就需要额外使用一个通信框架与服务器交互；当然也可以直接选择使用jQuery 提供的AJAX 通信功能；

#### UI框架

- Ant-Design：阿里巴巴出品，基于React的UI框架
- ElementUI、iview、ice：饿了么出品，基于Vue的UI框架
- ***BootStrap\***：Teitter推出的一个用于前端开发的开源工具包
- AmazeUI：又叫“妹子UI”，一款HTML5跨屏前端框架

### JavaScript构建工具

- Babel：JS编译工具，主要用于浏览器不支持的ES新特性，比如用于编译TypeScript
- WebPack：模块打包器，主要作用就是打包、压缩、合并及按序加载

注：以上知识点已将WebApp开发所需技能全部梳理完毕

### 0.5、三端同一

#### 混合开发（Hybrid App）

主要目的是实现一套代码三端统一（PC、Android：.apk、iOS：.ipa）并能够调用到设备底层硬件（如：传感器、GPS、摄像头等），打包方式主要有以下两种：

- 云打包：HBuild -> HBuildX，DCloud 出品；API Cloud
- 本地打包： Cordova（前身是 PhoneGap）

#### 微信小程序

 详见微信官网，这里就是介绍一个方便微信小程序UI开发的框架：WebUI

 

1、什么是Javascript
-------------------

### **1.1、概述**

 javaScript是一门世界上最流行的脚本语言 Java，JavaScript 10天 一个合格的后端人员，必须精通JavaScript

### **1.2、历史**

 见百度 
 ECMAScript它可以理解为JavaScript的一个标准 最新版本已经到es6版本~ 但是大部分浏览器还只停留在支持es5代码上！ 开发环境–线上环境，版本不一致

2、快速入门
-----------

### 2.1、引入JavaScript

1、内部标签

```xml
 <!--script标签内，写JavaScript代码-->
    <script>
      alert('hello,world!');
    </script>
 
```

2、外部引入
test.js

```xml
 aert("hello,world");
```

test.html

```xml
  <!--外部引入
         注意：script必须成对出现
     -->
     <script src="js/hj.js"></script>
 
     <!--不用显示定义type，也默认就是javaScript-->
     <script type="text/javascript"></script>
 
```

测试代码

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--script标签内，写JavaScript代码-->
    <!--<script>-->
    <!--    alert('hello,world!');-->
    <!--</script>-->
</head>
<body>

<!--这里也可以存放js代码-->
<!--外部引入
       注意：script必须成对出现
   -->
<script src="js/test.js"></script>

<!--不用显示定义type，也默认就是javaScript-->
<script type="text/javascript"></script>

</body>
</html>
```

### **2.2、基本语法入门**

```xml
 <!DOCTYPE html>
 <html lang="en">
 <head>
     <meta charset="UTF-8">
     <title>Title</title>
 
     <!--JavaScript严格区分大小写-->
     <script>
         // 1. 定义变量   变量类型 变量名 = 变量值
         var score = 1 ;
         //alert(num)
         // 2. 条件控制
 
         if (score > 60 && score < 70){
             alert("60~70");
         }else if(score > 70 && score < 80){
             alert("70~80");
         }else{
             alert("other")
         }
     </script>
 </head>
 <body>
 
 </body>
 </html>
 
```

浏览器必备调试须知：

```xml
//网页控制台输入进行调试
console.log();
```



[![RogTPJ.png](D:\Desktop\RogTPJ.png)](https://imgtu.com/i/RogTPJ)

### 2.3、数据类型

数值，文本，图形，音频，视频

变量 

```xml
 var a
```

**number**

js不区分小数和整数，Number

```xml
 123//整数123
 123.1//浮点数123.1
 1.123e3//科学计数法
 -99//负数
 NaN //not a number
 Infinity // 表示无限大
```

**字符串**
‘abc’ “abc”

**布尔值**
true，false

**逻辑运算**

```xml
 && 两个都为真，结果为真
 || 一个为真，结果为真
 !   真即假，假即真
```

**比较运算符** ！！！重要！

```
 =
 1，"1"
 == 等于（类型不一样，值一样，也会判断为true）
 === 绝对等于（类型一样，值一样，结果为true）
```

这是一个JS的缺陷，坚持不要使用 == 比较
须知：

- NaN === NaN，这个与所有的数值都不相等，包括自己
- 只能通过isNaN（NaN）来判断这个数是否是NaN

**浮点数问题**

```
 console.log((1/3) === (1-2/3))
```

尽量避免使用浮点数进行运算，存在精度问题！

```
 Math.abs(1/3-(1-2/3))<0.00000001
```

**数组**
Java的数组必须是相同类型的对象~，JS中不需要这样

```
 //保证代码的可读性，尽量使用[]
 var arr = [1,2,3,4,5,'hello',null,true];
 //第二种定义方法
 new Array(1,2,3,4,5,'hello');
```

取数字下标：如果越界了，就会 报undefined

```
 undefined
```

**对象**
对象是大括号，数组是中括号

> 每个属性之间使用逗号隔开，最后一个属性不需要逗号

```xml
 // Person person = new Person(1,2,3,4,5);
 
 var person = {
     name:'Tom',
     age:3,
     tags:['js','java','web','...']
 }
 
```

**取对象值**

```xml
 person.name
 > "Tom"
 person.age
 > 3
```

### **2.4、严格检查格式**use strict

[![RoWRKI.png](D:\Desktop\RoWRKI.png)](https://imgtu.com/i/RoWRKI)

```xml
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <!--
  前提：IDEA需要设置支持ES6语法
      'use strict';严格检查模式，预防JavaScript的随意性导致产生的一些问题
      必须写在JavaScript的第一行！
      局部变量建议都使用let去定义~
  -->
  <script>
    'use strict';
    //局部变量
    let i=1
    //ES6 let
  </script>
</head>
<body>

</body>
</html>
 
```

3、数据类型
-----------

### 3.1、字符串

#### 1、正常字符串我们使用 单引号，或者双引号包裹

#### 2、注意转义字符 \

```xml
 \'
 \n
 \t
 \u4e2d    \u##### Unicode字符
 
 \x41    Ascall字符
```

#### 3、多行字符串编写

```xml
 //tab 上面 esc下面
         var msg =
             `hello
             world
             你好呀
             nihao
             `
```

#### 4、模板字符串

```xml
 //tab 上面 esc下面
 let name = 'Tom';
 let age = 3;
 var msg = `你好，${name}`
```

#### 5、字符串长度

```xml
str.length
```

![image-20210819162905625](D:\Desktop\image-20210819162905625.png)

#### 6、字符串的可变性，不可变

![在这里插入图片描述](D:\Desktop\20200508110738649.png)

#### 7、大小写转换

```xml
//注意，这里是方法，不是属性了
student.toUpperCase();
student.toLowerCase();
```

#### 8、student.indexof(‘t’)

#### 9、substring，从0开始

```xml
[)
student.substring(1)//从第一个字符串截取到最后一个字符串
student.substring(1,3)//[1,3)
```

### 3.2、数组

Array可以包含任意的数据类型

```xml
var arr = [1,2,3,4,5,6];//通过下标取值和赋值
arr[下标]
```

#### 1、长度

```xml
arr.length
```

注意：假如给arr.lennth赋值，数组大小就会发生变化~，如果赋值过小，元素就会丢失

#### 2、indexOf，

通过元素获得下标索引

```xml
arr.indexOf(2) //1
```

字符串的"1"和数字 1 是不同的

#### **3、slice（）**

截取Array的一部分，返回的一个新数组，类似于String中substring

#### **4、push()，pop()尾部**

```xml
push：压入到尾部一个元素
pop：弹出尾部的一个元素
```

#### **5、unshift(),shift() 头部**

```xml
unshift：压入到头部一个元素
shift：弹出头部的一个元素
12
```

#### 6、排序sort()

```xml
(3)["B","C","A"]
arr.sort()-->["A","B","C"]
```

#### 7、元素反转reverse()

```xml
(3)["A","B","C"]
arr.reverse()-->["C","B","A"]
```

#### **8、concat()**

![在这里插入图片描述](D:\Desktop\20200508153119816.png)

注意：concat()并没有修改数组，只是会返回一个新的数组

#### 9、连接符join

打印拼接数组，使用特定的字符串连接
![在这里插入图片描述](D:\Desktop\20200508153243846.png)

#### 10、多维数组

![在这里插入图片描述](D:\Desktop\20200508153447514.png)

数组：存储数据（如何存，如何取，方法都可以自己实现！）

### 3.3、对象

若干个键值对

```xml
var 对象名 = {
	属性名：属性值，
	属性名：属性值，
	属性名：属性值
}
//定义了一个person对象，它有四个属性
var person = {
	name:"Tom",
	age:3,
	email:"123456798@QQ.com",
	score:66
}
```

Js中对象，{…}表示一个对象，建制对描述属性xxx：xxx，多个属性之间用逗号隔开，最后一个属性不加逗号！ JavaScript中的所有的键都是字符串，值是任意对象！ 1、对象赋值

#### 1、对象赋值

![在这里插入图片描述](D:\Desktop\20200508155833832.png)
2、使用一个不存在的对象属性，不会报错！

#### undefined

![在这里插入图片描述](D:\Desktop\20200508155917394.png)

3、动态的删减属性，通过delete删除对象的属性

#### delete![在这里插入图片描述](D:\Desktop\20200508160429505.png)

4、动态的添加，直接给新的属性添加值即可
![在这里插入图片描述](D:\Desktop\20200508160409465.png)
5、判断属性值是否在这个对象中！

#### xxx in xxx

![在这里插入图片描述](D:\Desktop\20200508160704412.png)
6、判断一个属性是否是这个对象自身拥有的

#### hasOwnProperty()

![在这里插入图片描述](D:\Desktop\20200508160950801.png)

### 3.4、流程控制

#### i f判断

![在这里插入图片描述](D:\Desktop\20200508161158507.png)

#### while循环，避免程序死循环

![在这里插入图片描述](D:\Desktop\20200508161549241.png)

#### for循环

![在这里插入图片描述](D:\Desktop\20200508161625832.png)

#### forEach循环

> ES5.1特性

 

![在这里插入图片描述](D:\Desktop\20200508162100917.png)

#### for …in-------下标

#### ![在这里插入图片描述](D:\Desktop\20200508162209421.png)

### 3.5、Map和Set

 

> ES6的新特性~

 

#### Map

![在这里插入图片描述](D:\Desktop\20200508163109596.png)

#### Set：无序不重复的集合

![在这里插入图片描述](D:\Desktop\20200508163211654.png)

### 3.6、iterator

> es6新特性

 

作业：使用iterator来遍历迭代我们Map，Set！
遍历数组
![在这里插入图片描述](D:\Desktop\2020050816410825.png)

#### 遍历Map

![在这里插入图片描述](D:\Desktop\20200508164125573.png)

#### 遍历set

![在这里插入图片描述](D:\Desktop\20200508164144469.png)

4、函数
-------

### 4.1、定义函数

#### 定义方式一

绝对值函数
![在这里插入图片描述](D:\Desktop\2020050818170197.png)
一旦执行到return代表函数结束，返回结果！
如果没有执行return，函数执行完也会返回结果，结果就是undefined

#### 定义方式二

![在这里插入图片描述](D:\Desktop\20200508182120582.png)
function(x){…}这是一个匿名函数。但是可以吧结果赋值给abs，通过abs就可以调用函数！
方式一和方式二等价！

#### 调用函数

```
abs(10)//10
abs(-10) //10
```

参数问题：javaScript可以传任意个参数，也可以不传递参数~
参数进来是否存在问题？
假设不存在参数，如何规避？
![在这里插入图片描述](D:\Desktop\20200508182908571.png)

#### arguments

arguments是一个JS免费赠送的关键字；
代表，传递进来的所有参数，是一个数组！
![在这里插入图片描述](D:\Desktop\20200508183337762.png)
问题：arguments包含所有的参数，我们有时候想使用多余的参数来进行附加操作。需要排除已有参数~

#### **rest**

以前：

![在这里插入图片描述](D:\Desktop\20200508183752806.png)

ES6引入的新特性，获取除了已经定义的参数之外的所有参数~…
![在这里插入图片描述](D:\Desktop\20200508183918899.png)
rest参数只能写在最后面，必须用`…`标识。

### 4.2、变量的作用域

在javascript中，var定义变量实际是有作用域的。
假设在函数体重声明，则在函数体外不可以使用~（闭包）
![在这里插入图片描述](D:\Desktop\202005081843310.png)
如果两个函数使用了相同的变量名，只要在函数内部就不冲突
![在这里插入图片描述](D:\Desktop\20200508213017794.png)
内部函数可以访问外部函数的成员，反之则不行
![在这里插入图片描述](D:\Desktop\2020050821304022.png)

假设，内部函数变量和外部函数变量，重名！
![在这里插入图片描述](D:\Desktop\20200508214742767.png)
假设在JavaScript中，函数查找变量从自身函数开始~， 由“内”向“外”查找，假设外部存在这个同名的函数变量，则内部函数会屏蔽外部函数的变量。

> 提升变量的作用域

#### 提升变量的作用域

![在这里插入图片描述](D:\Desktop\20200508215241301.png)
结果：x undefined
说明：js执行引擎，自动提升了y的声明，但是不会提升变量y的赋值；
![在这里插入图片描述](D:\Desktop\20200508215909640.png)
这个是在javascript建立之初就存在的特性。 养成规范：所有 的变量定义都放在函数的头部，不要乱放，便于代码维护；
![在这里插入图片描述](D:\Desktop\2020050822470141.png)

> 全局变量

 

![在这里插入图片描述](D:\Desktop\20200508224905458.png)

#### 全局对象window

![在这里插入图片描述](D:\Desktop\20200508225326543.png)

 

alert() 这个函数本身也是一个`window`的变量；
![在这里插入图片描述](D:\Desktop\20200508225810801.png)
javascript实际上只有一个全局作用域，任何变量（函数也可以视为变量)，假设没有在函数作用范围内找到，就会向外查找，如果在全局作用域都没有找到，就会报错 Refrence

> 规范

由于我们的所有变量都会绑定到window上，。如果不同的js文件，使用了相同的全局变量，就会产生冲突—>如何减少这样的冲突？

#### 唯一全局变量

 

![在这里插入图片描述](D:\Desktop\20200508230620266.png)
把自己的代码全部放入自己定义的唯一空间名字中，降低全局命名冲突问题~
jQuery中就是使用的该方法：jQuery.name，简便写法：**$()**

> 局部作用域 let

![在这里插入图片描述](D:\Desktop\20200508231056855.png)
ES6的let关键字，解决了局部作用域冲突的问题！

#### let关键字

![在这里插入图片描述](D:\Desktop\20200508231207856.png)
建议大家都用let去定义局部作用域的变量；

> 常量  const

在ES6之前，怎么定义常量：只有用全部大写字母命名的变量就是常量；建议不要修改这样的值。
![在这里插入图片描述](D:\Desktop\20200508231525623.png)
在ES6引入了

#### 常量关键字 const

![在这里插入图片描述](D:\Desktop\20200508232049107.png)

### 4.3、方法

> 定义方法

 

方法就是把函数放在对象的里面，对象只有两个东西：属性和方法

```java
<script>
  var zty={
    name: '张天泳',
    birth: 2002,
    //方法
    age: function (){
      //今年-出生
      var now = new Date().getFullYear();
      return now-this.birth;
    }
  }
  // 属性
  zty.name;
  // 方法
  zty.age();
</script>
```

this.代表什么？拆开上main的代码看看

```java
var zty={
  name: '张天泳',
  birth: 2002,
  //方法
  age1: getAge,
  age: function (){
    //今年-出生
    var now = new Date().getFullYear();
    return now-this.birth;
  }
}
// 属性
zty.name;
// 方法
zty.age();
function getAge(){
  //今年-出生
  var now = new Date().getFullYear();
  return now-this.birth;
}
```

**this是无法指向的，是默认指向调用它的那个对象的；**

****

> apply

在js中可以控制this指向
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200508233222629.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

 

5、内部对象
-----------

 

> 标准对象

 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200508233500524.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

 

### 5.1、Date

**基本使用**
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020050823390552.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)
转换
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200508233954136.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

### 5.2、JSON

> > JSON是什么

 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200508234238700.png)
 在javascript中，一切皆为对象，任何js支持的类型都可以用JSON表示
 格式

- 对象都用{}
- 数组都用[]
- 所有的键值对 都是用key:value

JSON字符串和js对象转化
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200508234804502.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)
 很多人搞不清楚，JSON和JS对象的区别

```java
var 对象={name: "张天泳", age: 18, sex: "男"}
var JSON={"name":"张天泳","age":18,"sex":"男"}
```

### 5.3、AJAX

- 原生的js写法 xhr异步请求
- jQuery封装好的方法$(#name).
- ajax("")axios请求

6、面向对象编程
---------------

原型对象 javascript、java、c#------面向对象；但是javascript有些区别！

- 类：模板
- 对象：具体实例

在javascript中，需要大家转换一下思维方式！ 原型： 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509210303742.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509210627825.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

> class集继承

class关键字，是在ES6引入的
1、定义一个类、属性、方法
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509210756344.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)
2、继承

```java
 <script>
     //ES6之后========================
     //定义一个学生的类
     class Student{
         constructor(name){
             this.name = name;
         }
         hello(){
             alert('hello');
         }
 }
 
     class XiaoStudent extends Student{
         constructor(name,grade){
             super(name);
             this.grade = grade;
         }
         myGrade(){
             alert('我是一名小学生');
         }
     }
 
     var xiaoming = new Student("xiaoming");
     var xiaohong = new XiaoStudent("xiaohong",1);
 </script>
 
```

本质：查看对象原型
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509211811667.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

 

> 原型链

 

*proto*:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509212115371.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

7、操作BOM对象（重点）
----------------------

> 浏览器介绍

javascript和浏览器关系？
BOM：浏览器对象模型

- IE6~11
- Chrome
- Safari
- FireFox
- Opera

三方

- QQ浏览器
- 360浏览器

> window

window代表浏览器窗口

### window ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509224733766.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

> Navigator（不建议使用）

Navigator封装了浏览器的信息

### Navigator（不建议使用） ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509225010877.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

大多数时候，我们不会使用navigator对象，因为会被认为修改!
不建议使用这些属性来判断和编写代码

> screen

代表屏幕尺寸

### screen

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509225316614.png)

> location(重要)

### *location(重要)***

location代表当前页面的URL信息
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509225614305.png)

> document（内容DOM）

### document（内容DOM）

document代表当前的页面，HTML DOM文档树
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509225911170.png)
获取具体的文档树节点
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509225947396.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

### 获取cookie

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509230037645.png)
劫持cookie原理
[www.taobao.com](http://www.cnblogs.com/www.taobao.com)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020050923025532.png)
服务器端可以设置cookie为**httpOnly**

> history（不建议使用 ）

history代表浏览器的历史记录

### history ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509230639949.png)

8、操作DOM对象（重点）
----------------------

DOM：文档对象模型

> 核心

浏览器网页就是一个Dom树形结构！

- 更新：更新Dom节点
- 遍历Dom节点：得到Dom节点
- 删除：删除一个Dom节点
- 添加：添加一个新的节点

要操作一个Dom节点，就必须要先获得这个Dom节点

> 获得Dom节点

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509231806822.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

这是原生代码，之后我们尽量都使用jQuery()

> 更新节点

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509232232560.png)
操作文本
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509232256674.png)
操作css
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509232439513.png)

> 删除节点

删除节点的步骤：先获取父节点，再通过父节点删除自己
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509232903448.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

注意：删除多个节点的时候，children是在时刻变化的，删除节点的时候一定要注意。

> 插入节点

我们获得了某个Dom节点，假设这个dom节点是空的，我们通过innerHTML就可以增加一个元素了，但是这个Dom节点已经存在元素了，我们就不能这么干了！会产生覆盖

追加
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200509233556254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020050923363290.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3Bhbl9oMTk5NQ==,size_16,color_FFFFFF,t_70)

> 创建一个新的标签

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>

<p id="j">JavaScript</p>
<div id="list">
  <p id="j1">javase</p>
  <p id="j2">javame</p>
  <p id="j3">javaee</p>
</div>
<script>
  let j=document.getElementById('j');
      list=document.getElementById('list');
  list.appendChild(j);//追加元素，将已经存在的节点更改位置

  //通过js新建一个节点
  let newp = document.createElement('p');//创建一个p标签
  newp.setAttribute('id','newp');//等价于 newp.id='j4';
  newp.innerText='Hello,zty!';
  list.appendChild(newp);

  //创建一个标签节点
  let myscript=document.createElement('script');
  myscript.setAttribute('type','text/javascript');
   list.appendChild(myscript);

  //可以创建一个style标签
  let myStyle = document.createElement('style');//创建了一个空style标签
  myStyle.setAttribute('type','text/css');
  myStyle.innerHTML = 'body{background-color:chartreuse;}';//设置标签内容

  document.getElementsByTagName('head')[0].appendChild(myStyle);
</script>
</body>
</html>
```

> insertBefore

```xml
  //在前面插入一个节点
  var j2 = document.getElementById('j2');
  var j = document.getElementById('j');
  var list = document.getElementById('list');
  //要包含的节点.insertBefore(newNode,targetNode)
  list.insertBefore(j,j2);
```

> ### **https://cdn.bootcss.com/blueimp-md5/2.10.0/js/md5.min.js**

9、操作表单form***
------------------

> 表单是什么？form-----DOM树

- 文本框----text
- 下拉框----select
- 单选框----radio
- 多选框----checkbox
- 隐藏域----hidden
- 密码框----password
- …

表单的目的提交信息

> 获得要提交的信息

```xml
<body>
    <form action = "post">
        <p>
            <span>用户名：</span><input type="text" id = "username" />
        </p>
        <!--多选框的值就是定义好的value-->
        <p>
            <span>性别：</span>
            <input type = "radio" name = "sex" value = "man" id = "boy"/>男
           	<input type = "radio" name = "sex" value = "woman" id = "girl"/>女
        </p>
    </form>
    <script>
    	var input_text = document.getElementById("username");
        var boy_radio = document.getElementById("boy");
        var girl_radio = document.getElementById("girl");
        //得到输入框的值
        input_text.value 
        //修改输入框的值
        input_text.value  = "value";
        
        //对于单选框，多选框等等固定的值，boy_radio.value只能取到当前的值
        boy_radio.checked;//查看返回的结果，是否为true，如果为true，则被选中。
        girl_radio.checked = true;//赋值
        
    </script>
</body>
```

提交表单。md5加密密码，表单优化

### onsubmit = "return check()"

### onclick

### md5加密

```xml
<!DOCTYPE html>
<html lang = "en">
<head>
  <meta charset = "UTF-8">
  <title>Title</title>
  <!--MD5加密工具类-->
  <script src = "https://cdn.bootcss.com/blueimp-md5/2.10.0/js/md5.min.js">

  </script>
</head>
<body>
<!--表达绑定提交事件
    οnsubmit= 绑定一个提交检测的函数，true，false
    将这个结果返回给表单，使用onsubmit接收
-->
<form action = "https://www.baidu.com" method = "post" onsubmit = "return check()">
  <p>
    <span>用户名：</span><input type="text" id = "username" name = "username"/>
  </p>
  <p>
    <span>密码：</span><input type="password" id = "password" />
  </p>
  <input type = "hidden" id = "md5-password" name = "password">

  <!--绑定事件 onclick 被点击-->
  <button type = "submit">提交</button>

</form>

<script>
  function check(){
    alert(1);
    var username = document.getElementById("username");
    var pwd = document.getElementById("password");
    var md5pwd = document.getElementById("md5-password");
    //MD5算法
    //pwd.value = md5(pwd,value);
    md5pwd.value = md5(pwd.value);
    //可以校验判断表单内容，true就是通过提交，false就是阻止提交
    return true;

  }
</script>

</body>
</html>
```

10、jQuery
----------

javaScript和jQuery的关系？

jQuery库，里面存在大量的JavaScript函数

> 获取jQuery

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020051021540896.png)

### **公式：$(selector).action()\******\***

```xml
 <!DOCTYPE html>
 <html lang = "en">
     <head>
         <meta charset = "UTF-8">
         <title>Title</title>
         <script src="lib/jquery-3.6.0.js"></script>
     </head>
     <body>
         <a href="" id = "test-jquery">点我</a>
         <script>
             //选择器就是css选择器
             $('#test-jquery').click(function(){
                 alert('hello,jQuery!');
             });
         </script>
     </body>
 </html>
 
```

> 选择器

```xml
 //原生js，选择器少，麻烦不好记
 //标签
 document.getElementByTagName();
 //id
 document.getElementById();
 //class
 document.getElementByClassName();
 
 //jQuery css中的选择器它全部都能用！
 $('p').click();//标签选择器
 $('#id1').click();//id选择器
 $('.class1').click;//class选择器
```

### 文档工具站：http://jquery.cuishifeng.cn/

> 事件

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
  <script src="lib/jquery-3.6.0.js"></script>
  <!--   鼠标事件、键盘事件，其他事件
   mousedown()(jQuery)----按下
   mouseenter()(jQuery)
   mouseleave()(jQuery)
   mousemove()(jQuery)----移动
   mouseout()(jQuery)
   mouseover()(jQuery)
   mouseup()(jQuery)-->
  <style>
    #divMove{
      width:500px;
      height:500px;
      border:1px solid red;
    }
  </style>
</head>
<body>
<!--要求：获取鼠标当前的一个坐标-->
mouse：<span id = "mouseMove"></span>
<div id = "divMove">
  在这里移动鼠标试试
</div>
<script>
  //当网页元素加载完毕之后，响应事件
  //$(document).ready(function(){})
  $(function(){
    $('#divMove').mousemove(function(e){
      $('#mouseMove').text('x:'+e.pageX+"y:"+e.pageY)
    })
  });
</script>

</body>
</html>
 
```

> 操作DOM

操作DOM

节点文本操作

```xml
 $('#test-ul li[name=python]').text();//获得值
 $('#test-ul li[name=python]').text('设置值');//设置值
 $('#test-ul').html();//获得值
 $('#test-ul').html('<strong>123</strong>');//设置值
```

CSS的操作

```xml
$('#test-ul li[name=python]').css({"color","red"});
```

元素的显示和隐藏，：本质display:none

```xml
 $('#test-ul li[name=python]').show();
 $('#test-ul li[name=python]').hide();
```

娱乐测试

```xml
 $(window).width()
 $(window).height()
 $('#test-ul li[name=python]').toggle();
```

未来ajax()；

```xml
 $('#form').ajax()
 
 $.ajax({url:"test.html",context:document.body,success:function(){
     $(this).addClass("done");
 }})
 
```

> 小技巧

1、如何巩固JS（看jQuery源码，看游戏源码！

2、巩固HTML、CSS（扒网站，全部down下来，然后对应修改看效果~）a