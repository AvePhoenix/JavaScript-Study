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



