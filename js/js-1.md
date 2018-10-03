#### 21、js的数据类型

基本数据类型：string,boolean,number,undefined,object,null

引用数据类型：object(Array,Date,RegExp,Function)

如何判断变量为数组数据类型

1、slice方法

2、obj  instanceof Array 在某些IE版本中不正确

3、ES5中Array.isArray(),

toString.call常用于判断数组、正则这些复杂类型

```js
toString.call(18);  //"[object Number]"
toString.call("");//"[object String]"
toString.call(/[0-9]{10}/);//"[object RegExp]"
```



```js
if(typeof Array.isArray==="undefined"){
    Array.isArray=function(arg){
        return Object.prototype.toString.call(arg)==="[object Array]"
    };
}
```

#### 已经知道ID的input输入框，希望获取这个输入框的输入值，怎么做？

```js
document.getElementById("ID").value
```



#### 23、希望获取到页面中所有的checkbox怎么做

```js
var domList=document.getElementByTagName('input');
var checkBoxList=[];
var len=domList.length;
while(len--){
    if(domList[len].type=='checkbox'){
    checkBoxList.push(domList[len]);
        
    }
}
```

#### 24、设置一个已知ID的DIV的html内容为xxxx,字体颜色设置为黑色

```js
var dom=document.getElementById('ID');
dom.innerHTML="xxxx";
dom.style.color="#000";
```

#### 25、当一个DOM被点击的时候，我们希望执行一个函数，应该怎么做

```
<div onclick="test()"></div>

xx.onclick=test

addEventListener(xxx,'click',test)

```

#### 26、

```js 
var a;
alert(typeof a);//undefined
alert(b);//如果下面定义了b,变量提升，打印10       如果后面没有定义b,报错
var b=10;
alert(typeof b);//"number"
```

注意：未声明的变量报错，声明了未赋值的变量为undefined

#### 27、

null表示一个空指针对象，这个值就是null，typeof检测会返回object

```
var a=null;
alert(typeof a);//object

```

#### 28、

```js
var undefined;
undefined==null;//true   相等但是不恒等===
1==true;//true
2==true;//false
0==false;//true
0=='';//true
NaN==NaN;//false
[]==false;//true
[]==![];//true
```

```
var foo="11"+2-"1";
console.log(foo);
console.log(typeof foo);
```

#### 29、考察引用数据类型

```js
var a=new Object();
a.value=1;
b=a;
b.value=2;
alert(a.value);//2
```

#### 30、已知数组 var stringArray=["this","is","baidu","campus"],alert出“this is baidu campus”

```
alert(stringArray.join(" "));
```



#### 31、