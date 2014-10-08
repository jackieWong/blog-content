Title: JS Note
Date: 2014-07-10
Tages: JavaScript, Note
Category: Web

** Web Deveslop**

| html | css| javascript |
| ----- | ---- | ----------- |
| content | layout | interface |

## HTML

### HTML Elements

- start tag <>

- end tag </>

- content in between 

example:

	<p>This is a paragraph.</p>

	
### HTML Attribute

- elements can have attribute

- elements provide more information about elements 

- attribute are always specified in start tag <>

- attribute appears like: name="value"

example:

	<a href ="http://www.w3schools.com">This is a link</a>
	
## CSS

### Insert CSS
-externel css

-internel css
	
	<head>
		<style>
		</style>
	</head>

-inline css
	<p style="color:sienna; margin-left:20px;">This is a paragraph.</p>
	
	<p style="color:sienna; margin-left:20px;">This is a paragraph.</p>
	
	
**Styles define how to display HTML elements.**


**Syntax:**

	selector Declaration	Declaration
	h1		{color:blue; 	font-size:12px;}

**Element selector**
	
	p { color:red; text-align:center;}

**id selector** 

	#id1 {}
	#id2 {}
	
**class selector**

	.class1{}
	
**class selector with specifice element tag**
	
	p.class{}

**group selector**
	
	h1 p {}
	
	
### 	Cascading Order

1. Browser default
2. External style sheet
3. Internal style sheet(in the head session)
4. Inline style(inside an HTML element)

   ** inline style has the highest priority.**
   
   
## DOM


The DOM Programming Interface
DOM编程接口，DOM可以动态的被javascript被访问。

The HTML DOM can be accessed with JavaScript (and with other programming languages).

In the DOM, all HTML elements are defined as objects.
在DOM模型中，所有的HTML element都是Object.编程接口就这些Object的属性和方法。

The programming interface is the properties and methods of each object.

A property is a value that you can get or set (like changing the content of an HTML element).

A method is an action you can do (like add or deleting an HTML element).



document.getElementById() is a method.
innerHTML is property.
### DOM document object

![image](http://www.w3schools.com/js/pic_htmltree.gif)

document object代表的是整个web页面，是其他所有HTML Element 的宿主
访问页面中元素的时，首先需要访问到document对象

![image](http://www.w3schools.com/js/pic_navigate.gif)

### DOM interface  

Finding HTML Element:

	document.getElementById()
	document.getElementByTagName()
	document.getElementByClassName()  //not supported by ie 5 6 7
	
Changing HTML Elements:
	
	element.innerHTML=
	element.attribute=
	element.setAttribute(attribute,value)
	element.style.property=
	
Adding and Deleting Elements
	
	document.createElement()
	document.removeChild()
	document.appendChild()
	document.replaceChild()
	document.write(text)
	
Adding Event Handlers
	
	document.getElementById(id).onclick = function(){}

DOM标准

   
## JavaScript


### JS Statements
exec by browser.
	
	document.getElementByID("demo").innerHTML = "Hello World";

### js variable
	var x = 5, y = "5";
	
### js Data Types

动态类型语言，一个变量可以存放不同类型的数据。

**String**

	var name = 'Wstnap'
	var name = "Wstnap"
	
**Number**

	var x1 = 34.00
	var x2 = 34
	var y = 123e5
	var x = 123e-5
	
**Booleans**

	var x = true;
	var y = false;
	
**Arrays**

	var cars = [1, 2.0, "BMW"]

**Objects**

	var persion = {firstName:"John", lastName:"Doe", age:50,
	eyeColor:"blue"}

**undefined and null**

一个变量定义了未初始化为undefined
；null清空变量的内容


**typeof**

	typeof [1,2] //object
	typeof {firstName:"sheng",lastName:"wang"}	//object
	typeof "string"	//string
	typeof false;	//boolean
	
**new操作符用来声明Object**

	var x = new String();
	var y = new Number();
	var z = new Boolean();
	
### Objects
以键值对的形式
	
	{firstName : "sheng",
	lastName : "wang"
	fullName : function() { return firstName + " " + lastName;}
	}

### Function
Parameters is the **name** listed in the function declaration
Argument is the **name** listed in the invokation

1.主动调用

2.事件发生

### 作用域
**Glbal Variable:**
	在所有函数外部的变量未全局变量。
	使用之前未声明的变量属于Global变量，即使是存在于函数内部。
	
**global variable是java script的环境变量**
**all global variable都是属于windows对象的**


### String

String可以被当作数组使用：
	"john"[0]
String也可作为类型使用：
	"john".length
	
### String Method
var str = "Please locate where it is ?"

从零开始计算，如果没有找到返回－1

**indexOf & lastIndexOf**

var posistion = str.indexOf("locate");
var position2 = str.lastIndexOf("locate");

**search**

var potision3 = str.search("locate");

**slice (左闭右开区间)**

var position = str.find("locate");
var newString = str.slice(position+"locate".length, str.length)
-1代表字符的结尾最后一个，最后一个字符所以（0，－1）**并不包含最后一个字符**
**第二个参数是字符串末尾的索引**

**substr**

也是返回子序列
str.substr(startIndex, strLength);

**不同的是substr是第二个参数是字符串长度**

**replace**

取代str中的第一个字符串为第二个字符串
str.replace("abc","d")
**不一定要求相同**
	
**toUpperCae toLowerCase**

str.toUpperCase()
str.toLowerCase()
	
	
### Change HTML

- HTML element的内容可以直接用innerHTML属性进行访问
- HTML element的属性也看可以通过对应的attribute来访问
	
example1:change content
	
	<h1 id = "header">Older Header</h1>
	
	<script>
		var element = document.getElementById("header");
		element.innerHTML = "New Header";
	</script>
example2: change attribute

	<image id = "myImage" src = "smiley.gif">
	
	<script>
		document.getElementById("myImage").src = "landscape.jpg";
	</script>
	

### Change CSS

	<p id="p1">Hello World!</p>
	
	<script>
		document.getElementById("p2").style.color = "blue";
		document.getElementById("p2").stype.fontFamily = "Arial";
		document.getElementByID("p2").style.fontSize = "large"
	</script>
	
	
## HTML DOM Events

DOM allow JavaScript to react to HTML events,event is also an attribute of HTML Element.

**input对象的消息**
	
	<input type="text" onchange="myFunction()"/>
	
	<script>
		function myFunction(){
			var x = document.getElementById("fname");
			x.value = x.value.toUpperCase();
		}
	</script>

**Mouse 事件**

- onmouseover
- onmouseout
- onmousedown
- onmouseup


**Add EventHandler**

可以为一个元素添加多个EventHandler,按添加顺序进行处理

	x.addEventListener();
	x.removeEventListener();
	
window对象也可以添加event
	
	addEventListener("eventType",function, false|true);
	//false使用event bubbling，消息最先被内层处理
	//true使用event capture消息最先被外层元素处理
	
兼容性考虑：
	
	var x = document.getElementById("myBtn");
	if (x.addEventListener) {
    	x.addEventListener("click", myFunction);
	} else if (x.attachEvent) {
    	x.attachEvent("onclick", myFunction);
	}
	






