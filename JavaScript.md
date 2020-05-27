## 前端三要素

    1. HTML（结构）：决而定网页的结构和内容
       2. Css（表现）：设定网页的表现样式
       3. Javascript（行为）：弱文本的脚本语言，由浏览器运行，用于控制网页的行为

​	 

node.js不支持高并发



## 前端框架

1. jQuery（库）
2. angular
3. Vue：建立式的
4. React（虚拟化DOM）
5. Axios



## UI框架

1. Ant-Design
2. ElementUI
3. Bootstrap
4. AmazeUI



Java和JavaScript没有关系， 一个合格的后端人员，必须精通JavaScript



引入JavaScript：

​	内部标签使用：

```javascript
<script>
    alert("Hello World");
</script>
```

​	外部引入：

<script src="js/zhang.js"></script>

## 基本语法

变量类型：

![image-20200519082344453](C:\Users\AVE\AppData\Roaming\Typora\typora-user-images\image-20200519082344453.png)



不能以数字开头但是可以以$ _





#### js不区分小数和整数

​	123 //整数

​	123.1	//浮点数

​	1.123e3	//科学计数法

​	-99	//负数

​	NaN	//no a number

​	Infinity  //表示无限大



#### 字符串

‘abc’    “abc”



#### 布尔值

true      false



#### 逻辑运算

&& 与

|| 或

！非（取反）





#### 比较运算符

=    赋值

==   等于（不管类型，只要值相同，返回true）

===   绝对等于（值和类型一样）



#### 浮点数问题

```
<script>
    console.log((1/3)===(1-2/3));
</script>
```

![image-20200519085820747](C:\Users\AVE\AppData\Roaming\Typora\typora-user-images\image-20200519085820747.png)

尽量避免用浮点数进行计算

![image-20200519090327427](C:\Users\AVE\AppData\Roaming\Typora\typora-user-images\image-20200519090327427.png)

![image-20200519090316104](C:\Users\AVE\AppData\Roaming\Typora\typora-user-images\image-20200519090316104.png)

#### null和undefined

* null   空
* undefined  未定义



#### 数组

java中数组必须是一类相同类型的对象，但是在JavaScript中不是

``` java
 var arr=[1,2,3,4,5,'hello',null,true]

```

![image-20200519100823903](C:\Users\AVE\AppData\Roaming\Typora\typora-user-images\image-20200519100823903.png)

如果取数组下标越界了就会显示undefined



#### 对象

​	对象是大括号，数组是中括号

​	对象之间每个属性之间用都好隔开

``` java
/*对象*/
        // 相当于Java的  person person=new person(1,2,3,4,5,6)
        var person={
            name:"zhang",
            age: 3,
            tags:['js','is','jiaoben']
        }
```

对象的取值：

```java
console.log(person.name,person.age,person.tags);
```

![image-20200519101608453](C:\Users\AVE\AppData\Roaming\Typora\typora-user-images\image-20200519101608453.png)





#### 严格检查

```javascript
/*  局部变量建议是使用let去定义
    严格检查模式，预防JavaScript的随意性产生的问题
    必须卸载JavaScript的第一行
    若没有use strict 则a=1被允许，否则不被允许   */
'use strict';
// a=1;
// 全局变量
// es6 中用let
var i=1;
let a=2;
console.log(a);
console.log(i);
```







##### 注意

* 在js中坚持不要使用==   
* NaN===NaN（false），这个与所有数值都不相等，包括自己
* 只能通过isNaN（NaN）来判断这个数是否为NaN







## 数据类型

#### 字符串

​	正常字符串我们用  单引号’‘ 包起来：console.log('a');

​	注意转意字符   \ 

``` jav
\'
\n
\t
\u4e2d
\X41        Ascll字符
\u#### unicode字符串
```

​	多行字符串编写

``` java
 //tab 上面的
        var msg=   `
                hello
                你好
                哈哈

        `
```



​	模版字符串

```Java
var msg=`hello
        你好
        哈哈
`;
let a="hahah";
let age=3;
let msg1 =`你好呀，${a} +`
console.log(msg);
console.log(msg1);
```



字符串长度

str.length



字符串的不可变性



大小写的转换（是方法，不是属性）

``` java
student.toUpperCase
student.toLowerCase
```





student.indexOf('t')



substring(  [)  )

``` javascript
student.substring（1）  //从一个字符串截取到最后一行个字符
student.substring（1，3）  //从一个字符串截取到第三个
```

if 判断







### 函数

定义函数：

绝对值函数：

``` javascript
function abs(x){
     if(x>=0){
                return x;
            }else
            {
                return -x;
            }
}
```

在return之后不能换行，浏览器默认会在换行的return后面添加；这样就是默认返回一个空

函数执行到return就结束，如果没有执行return函数执行完也会返回一个结果，undefined

定义方式2：

``` javascript
var abs=function(x){
     if(x>=0){
                return x;
            }else
            {
                return -x;
            }
}
```

function(x){......}这是一个匿名函数，但是可以吧函数执行的结果赋值给abs，通过abs可以调用函数

 ### 调用函数

```javascript
console.log(abs(10));
abs(10)；//10
abs(-10);//10
```

参数问题JavaScript可以传任意参数，也可以什么都不传参数

```javascript
 function abs(x){/*
     arguments.length*/
     //手动抛出异常来判断是否有参数
     if (typeof x!=="number"){
         throw '不是数字';
     }
     if(x>=0){
         return x;
     }else
     {
         return -x;
     }
 }
/* va
```

```
arguments是js赠送免费的关键词
代表传递进来的所有参数，是一个数组
 'use strict';
        var abs=function (x) {
            console.log("x=>"+x);
            for (let i=0 ;i<arguments.length;i++) {
                console.log(arguments[i]);
            }

        }
```

问题：arguments回包含所有的参数，有时候我们想使用多余的参数进行附加操作，需要排除已有参数



rest

获取出了已经定义参数之外的内所有参数

```javascript
//以前
function aaa(a,b){
    console,log(a);
    console,log(b);
    
    if (arguments.length>2){
        for (var i=0;i<arguments/length;i++){
            
        }
    }
   
}
//现在
function aaa(a,b,...rest){
    console,log(a);
    console,log(b);
    console,log(rest);
}
```

rest参数只能放在最后面，必须要用...标识



### 变量的作用域

```javascript
function qj() {
    var x=1;
    x+=1;

}
x+=2;//会报错，未定义
```

在函数体内声明，函数外或另一个函数内不能用（即使名字相同也不冲突），如果想用则涉及到闭包

内部函数可以访问外部函数的成员，反之不可以，

如果内部函数内部变量与外部变量，重名

```javascript
function qj1() {
    var x=1;
    function qj1() {
        var x = "a";
        console.log(x);//outer    1
    }
    console.log(x);//inner    a

}
```

函数查找变量从滋生函数开始，有内向外查找

全局变量，绑定在全聚德windows

JavaScript只有一个全局作用域，任何函数也可以看作变量，在函数中没有找到就会向外查找，如果在全局作用域没有找到就会报错

规范：由于我们所有的全局变量都会绑定在windos上，如果不同的js文件，使用了相同的全局变量就会冲突，

```JavaScript
//唯一全局变量
var app={};

//定义全局变量
app.name='zhang';
app.add=function (a,b) {
    return a+b;
}
```

把自己的代码全部放入自己定义的为宜空间名字中，降低全局命名冲突，（将自己定义的变量绑定在非windos上）



#### 局部变量域let

```javascript
function aaa() {
    for (var i = 0; i <100 ; i++) {
        console.log(i);
    }
    console.log(i+1);//输出：101   i出了作用域还能使用
}
aaa();
function aaaa() {
    for (let i = 0; i <100 ; i++) {
        console.log(i);
    }
    console.log(i+1);//报错，i出了作用域之外不能使用
}
```

let关键字解决局部变量冲突问题，建议使用let定义局部变量



#### const

只要用全部大写字母命名的变量就叫做常量//可变，所以引入const

```javascript
const PI=3.14//只读变量
PI='123';//报错，
```



### 方法

方法就是将函数放在对象里面，对象只有两个东西，属性和方法

```javascript
var app={
    name:zhang,
    age:1998,
    age:function () {
        var now=new Date().getFullYear();
        return now-this.age;
    }
}
//属性调用：app.name
//方法：（一定要带括号）app.age()
```

写法2

```javascript
function getage () {
    var now=new Date().getFullYear();
    return now-this.age;
}
var app={
    name:'zhang',
    age:1998,
    ag1:getage
}
```

拆开上面的代码，可以直接调用APP.age1()可以

歹势直接调用getage（）不可用，this.name在对象中，单独点用的话调用的是window所以this.name未定义

this是无法指向的，默认只想调用他的那个对象；



#### apply

在js中可以控制this的指向

```javascript
 function getage () {
            var now=new Date().getFullYear();
            return now-this.age;
        }
        var app={
            name:'zhang',
            age:1998,
            ag1:getage
        };
        var app1={
            name:'qing',
            age:1998,
            ag1:getage
        };

        getage.apply(app,[]) //this指向app对象，参数为空
        getage.apply(app1,[])// 不需要改变getage函数，只需要改变getage.apply指定的对象即可
```





### 内部对象

#### 标准对象

``` JavaScript
typeof 123
"number"
typeof '123'
"string"
typeof true
"boolean"
typeof NaN
"number"
typeof []
"object"
typeof {}
"object"
typeof Math.abs
"function"
typeof undefined
"undefined"
```



#### Data

#### 基本使用

```javascript
var now =new Date();
now.getFullYear();//年
now.getMonth();//月
now.getDate();//日
now.getHours();//时
now.getMinutes();//分
now.getSeconds();//秒
now.getTime();//时间戳
```

#### 转换

```JavaScript
now.toLocaleDateString();//调用方法
now.toGMTString()
```



### JOSN

早期所有的数据传输习惯使用Xml文件，

JOSN是一种轻量级的数据交换格式，**简洁和清晰地层次结构**使JOSN成为理想的**数据交换语言**，**易于人阅读和编写，同时也易于机器解析和生成，并有效的提升网络传输效率**



在js中一切皆为对象，任何js支持的类型都可以用JOSN来表示（number，string）

格式：

* ｛｝代表对象
* 【】代表数组
* key:value  代表键值对



JSON字符串和js对象的转换

``` javascript
//对象
        var user={
            name:"zhang",
            age:13,
            sex:"男"
        }
        console.log(user)
       /* {name: "zhang", age: 13, sex: "男"}
        //普通对象*/

       
       
        // 对象转换称JSON字符串
        var jsonUser=JSON.stringify(user)
        console.log(jsonUser)
        /*{"name":"zhang","age":13,"sex":"男"}
        //JSON对象
*/

        //JSON  字符串转化为对象,参数为JSON字符串
        var obj=JSON.parse('{"name":"zhang","age":13,"sex":"男"}')
        console.log(obj)
        /*{name: "zhang", age: 13, sex: "男"}*/
```



JSON和js的区别

``` javascript
var obj={a:'hello',b:'bello'}
var josn='{"a":"hello","b":"bello"}'
```



用java生成和解析，前段只需要去调用





### AJAK

* 原生js写法 xhr异步请求
* jQuey封装好的方法
* axios请求



### 面向对象编程

面向对象：（js有些区别）

* 类：模版，对象的抽象

* 对象：具体事例，类的实现

原型（讲一个对象作为另一个对象的模版类似于java中的继承，将一个对象的原型指向某个对象）：

```javascript
var Student={
    name:"zhang",
    age:13,
    sex:"男",
   run:function () {
       console.log(this.name+"run....");
   }
};
var xiaoming={
    name:"xiaoming"
}
var Bird={
    fly: function () {
        console.log(this.name+"fly....");
    }
}
// 此时xiaoming和user没有关系，并且小明中没有run方法   当xiaoming.run（）时，报错
xiaoming.__proto__=Student;//原型
// 此时xiaoming和user关联，xiaoming.run（）不报错    输出：xiaomingrun.....
xiaoming.__proto__ =Bird;
```

#### class继承

class关键字：es6出现

定义一个类的属性方法

```JavaScript
/*    以前定义的类
        function Student(name) {
            this.name=name;

        }
        Student.prototype.hello=function(){
            alert('heloo world;')
        }
        */

        //现在定义一个Student类：
class Student{
    constructor(name) {
        this.name=name;
    }
    hello(){
        alert('Hello')
    }
}


var xiaoming=new Student("xiaoming")
xiaoming.hello()
```

#### 继承

```JavaScript
class Student{
    constructor(name) {
        this.name=name;
    }
    hello(){
        alert('Hello')
    }
}
class xiaostudent extends Student{
    constructor(name,grade) {
        super(name);
        this.grade=grade;
    }
    mygrade(){
        alert('我是一名小学生');
    }

}


var xiaoming=new Student("xiaoming");
var xiaohong=new xiaostudent("xiaohong");
xiaohong.mygrade();
xiaoming.hello();
```

本质：查看对象原型；

原型链，指向object

____proto____

object的原型停止查找，但是还是有原型



### 操作BOM对象（重点）

js和浏览器的关系

js的诞生就是为了能在浏览器中运行

B/S  BOM浏览器对象模型

* IE 6~11
* chrome
* Safari
* FireFox(linux默认)

#### window

window代表浏览器窗口

window.alert(1)
undefined
window.innerHeight
478
window.innerWidth
1338
window.outerWidth
1352



##### navtor

封装了浏览器的信息

``` javascript
navigator.appVersion
"5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.106 Safari/537.36"
navigator.userAgent
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.106 Safari/537.36"
navigator.platform
"Win32"
```

大多数时候不会使用navigator对象，应为会被人人为修改，不建议使用这些属性来判断和编写代码

##### screen

控制屏幕：

``` JavaScript
screen.width
1536
```

##### location（重要）

lacotion代表当前页面的URL信息

``` JavaScript
host: "www.baidu.com"
href: "https://www.baidu.com/"
protocol: "https:"
reload: ƒ reload()//刷新网页
//设置新的地址
location.assign('https:******')
```



##### document

document代表当前页面，ＨＴＭＬＤＯＭ文档树，通过这个改变当前页面

```JavaScript
<dl id="">
    <dt>java</dt>
    <dt>javase</dt>
    <dt>javaee</dt>
</dl>
<script>
    var dl=document.getElementById('app')
</script>
```

获取文档树节点，

可以获取网页的cookie

劫持cookie原理：

www.qq.com

``` javas
 <script src="aa.js">
    </script>
    <!--恶意人员，获取你cookie发送到他的服务器，，比如，陶宝和天猫，两个网页都打开，但是只要把一个登入另一个也自动登入-->
```

服务器可以设置cookie：httpOnly



##### hostory(不建议使用)

history.forward  //前进
ƒ forward() { [native code] }
history.back  //后退
ƒ back() { [native code] }



### 操作DOM

文档对象模型

核心：浏览器网页就是一个DOM的树形结构

* 更新：更新DOM节点
* 遍历：得到DOM节点
* 删除：删除DOM节点
* 添加：添加DOM节点

要操作一个DOM节点（p，div，ul）必须先获得

#### 获得DOM节点

```JavaScript
<div id="father">
    <h1>标题1</h1>
    <p class="p1">p1</p>
    <p class="p2">p2</p>
</div>

    <script>
        //对应css选择器
       var h1= document.getElementsByTagName('h1');
       var p1= document.getElementById('p1');
       var p2= document.getElementsByClassName('p2');
        var father= document.getElementById('father');
        var clildrens=father.children//获取父节点中的所有子接点
        //father.firstchild
```

这是原生代码，以后会尽可能用jQuery（）

#### 更新节点

```JavaScript
<div id="id1">

</div>
<script>
    var id1=document.getElementById('id1');
    id1.innerText='abc'//属性使用字符串包裹
    id1.style.color='red'
    id1.style.fontSize='200px'
    id1.style.padding='2em'
```

操作文本

* innerText修改文本值
* innerHTML=‘<stron g>123</strong>’解析HTML文本标签

####　删除节点

步骤：现货去父节点，然后同过父节点和删除自己

```ＪａｖａＳｃｒｉｐｔ
<div id="father">
    <h1>标题1</h1>
    <p class="p1">p1</p>
    <p class="p2">p2</p>
</div>

<script>
     var　self=document.getElementById('p1');
      var father=p1.parentElement
      father.removeChild(p1)
    </script>
    //删除是一个动态的过程
    father.removeChild(father.ｃｈｉｒｌｄ［０］)
```

注意，删除多个节点的时候，children是在时刻变化的



### 插入节点

我们获得了某个DOM节点，假设这个DOM节点是空的，我们通过innerHTML就可以增加一个元素，但是这个DOM节点已经存在元素了，我们就需要添加一个追加

##### 追加

```JavaScript
<p id="js">javascript</p>
<div id="list">
    <h1>标题1</h1>
    <p class="p1">p1</p>
    <p class="p2">p2</p>
</div>

<script>
        var js=document.getElementById('js')
    var list=document.getElementById('list')
    list.append(js)//追加
</script>
```

##### 创建一个新的标签出插入

```JavaScript
var newP=document.createElement('p')//创建一个p标签
newP.id='newP'
newP.innerText='hello world'
/*将心得P标签加入到list中*/
list.append(newP)
```





``` java 
insert
   
```





### 操作表单（验证）

表单是form  DOM树

1. 文本框		text
2. 下拉框        select
3. 复选框 checkbox，单选框 radio
4. 隐藏域
5. 密码框

```html
<form action="post">
    <p>
    <span>用户名：</span> <input type="text" id="username">
    </p>
    <p>
        <span>性别：</span>
        <input type="radio" name="sex" value="boy" id="boy">男
        <input type="radio" name="sex" value="gril" id="gril">女
    </p>
</form>

<script>
    var username=document.getElementById('username')
    var boy1=document.getElementById('boy')
    var gril=document.getElementById('gril')
    /*
    * 对于多选框和单选框等固定的值，.value只能获取当前值，而不能判断是否被选中
    * */
    function look() {
        console.log(boy1.checked)
        console.log(gril.checked)

        //得到输入框得值
        console.log(username.value)
    }
    //如果要修改选框的值
    function changecheck(){
        boy1.checked=true;
    }

    //修改值
    function change(){
        username.value='123'
        console.log(username.value)
    }
</script>
```

#### 表单提交

```html
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--MD5工具库-->
    <script src="https://cdn.bootcdn.net/ajax/libs/blueimp-md5/2.16.0/js/md5.min.js"></script>
</head>
<body>
<!--
    
    表单绑定提交事件
    通过onsubmit这个绑定提交检测的函数，true，false
    讲这个结果返回给表单，使用onsubmit接收



-->
<form action="https://www.baidu.com" method="post" onsubmit="return aaa()">
    <p>
        <span>用户名：</span> <input type="text" id="username" name="username" required><!--//required非空-->
    </p>
   <!-- <p>
        <span>密码：</span> <input type="password" id="pwd" name="password" required>&lt;!&ndash;//required非空&ndash;&gt;

    </p>-->
    <p>
        <span>密码：</span> <input type="password" id="input-pwd" required>&lt;!&ndash;//required非空&ndash;&gt;

    </p>
    <input type="hidden" id="md5-password" name="password">
    <!--绑定onclick时间，别点击的时候-->
<!--    <button type="button" onclick="aaa()"  >提交</button>-->
    <input type="submit">
</form>
<script>
    function aaa() {
        var username=document.getElementById('username')
        var pwd=document.getElementById('input-password')
        var md5pwd=document.getElementById('md5-password')
        md5pwd.value=md5(pwd.value)
        return false
        
        
        /*console.log(username.value)
        console.log(pwd.value)
        //MD5算法
        pwd.value=md5(pwd.value)
        console.log(pwd.value)
        // pwd.value='123456'*/
       
        
        return true;//可以校验判断表单提交内容true通过，false阻止


    }
</script>
```





### jQuery

js

jQuery库：存在大量js函数的库

获取：

```html
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://code.jquery.com/jquery-3.4.1.min.js"></script><!--在线导入-->
</head>
<body>

<!--公式：$(selector(选择器).action()-->
<a href="" id="test-jQuery">点我</a>
<script>
    //选择器就是css中的选择器
    $('#test-jQuery').click(function(){
        alert('hello jQuery')
    })
</script>
```

选择器

```html
<script>
    /*
    * //原生js，选择器少，麻烦不好记
    * 
    * 标签
    *document.getElementsByTagName()
    * 
    * id
    * document.getElementById()
    * 
    * 类
    * document.getElementsByClassName()
    * 
    * 
    * jQuery   css中的选择器都可以用
    * $('p').click()//标签选择器
    * $('#id').click()//id选择器
    * $('.class').click()//类选择器
    * 
    * 
    * */
    
    
    
    
</script>
```



使用文档工具站；



##### 事件

鼠标事件

键盘事件

其他事件

```html
<!--获取鼠标当前的坐标-->
mouse: <span id="mouseMove"></span>
    <div id="divMove">
        在这里移动鼠标试试
    </div>

<script>
    //当网页元素加载完毕之后，响应时间
    $(function () {
        $('#divMove').mousemove(function (e) {

           $('#mouseMove').text('X:' + e.pageX + 'Y:' +e.pageY)

        })



    })
```





### 操作DOM(节点文本操作)

```html
<ul id="test-ul">
    <li class="java">java</li>
    <li name="js">javascript</li>
</ul>



<script>
    // document.getElementById()   原声代码
    console.log($('#test-ul li[name=js]').text())
    console.log($('#test-ul').html())

</script>
```

$('#test-ul li[name=js]').text(）//获得值

$('#test-ul li[name=js]').text(‘设置值’）//设置值

$('#test-ul').html()//获得值

$('#test-ul').html(‘<strong> 123<strong > ’)//设置值

##### css操作

```html
$('#test-ul li[name=js]').css("color","red")
```

##### 元素的显示和隐藏（本质display：none）

```html
$('#test-ul li[name=js]').hide()//隐藏
 $('#test-ul li[name=js]').show()//显示
```