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

已知有字符串foo="get-element-by-id",写一个function将其转化成驼峰表示法“getElementById”

```js
function combo(msg){
    var arr=msg.split("-");//[get,element,by,id]
    for(var i=1;i<arr.lengthl;i++){
        arr[i]=arr[i].charAt(0).toUpperCase()+arr[i].substr(1,arr[i].length-1);//
    }
    masg=arr.join("");//msg="getElementById"
    return msg;
}
```



#### 31、var numberArray=[3,6,2,4,1,5]

1)实现对该数组的倒排，输出[5,1,4,2,6,3]

```js
var numberArray=[3,6,2,4,1,5];
for(var i=numberArray.length-1;i>=0;i--){
    document.write(a[i]+'<br>');
}
```

```js
var numberArray=[3,6,2,4,1,5];
document.write(arr.reverse());
```



2)实现对该数组的降序排列，输出[6,5,4,3,2,1]

```js
var numberArray=[3,6,2,4,1,5];
numberArray.sort(function(x,y){
    return y-x;
});//若return大于0，则y前x后
document.writeln(numberArray);
```

3)升序排列

```js
var numberArray=[3,6,2,4,1,5];
numberArray.sort(function(x,y){
    return x-y;
});//若return大于0，则y前x后
document.writeln(numberArray);
```

#### 32、输出今天得日期，以YYYY-MM-DD方式，比如今天是2014年9月26日，则输出2014-09-26

```js
var d=newDate();
var year=d.getFullYear();
var month=d.getMonth+1;
month=month<10?'0'+month:month;
var day=d.getDate();
day=day<10?'0'+day:day;
alert(year+'-'+month+'-'+day);
```

#### 33、将字符串“<tr><td>{${$name}</td></tr>”中得｛$id｝替换成10，｛$name｝替换成Tony   （使用正则表达式）



```

```

#### 34、为了保证页面输出安全



```js
function escapeHtml(str){
    return str.replace(/[<>"&]/g,function(match){
        switch(match){
            case "<":
                  return "&lt;";
            case ">":
                  return  "&gt;";
            case "&":
                  return  "&amp;";
            case "\":
                  return   "&quot;";
        }
       
    });
}
```

#### 35、foo=foo||bar,这行代码是什么意思，为什么要这样写

短路表达式

if(!foo)foo=bar;//如果foo存在，值不变，否则把bar的值赋给foo

#### 36、下列代码输出什么

```js
var foo=1;
function(){
    console.log(foo);
    var foo=2;
    console.log(foo);
}
//  undefined  和  2
```

函数声明与变量声明会被javascript引擎隐式地提升到当前作用域得顶部，但是只提升名称不会提升赋值部分

#### 37、用js实现随即选取10-100之间得10个数字，存入一个数组，并排序

```js
var iArray=[];
function getRandom(istart,iend){
    var iChoice=iend-istart+1;
    return Math.floor(Math.random()*iChoice+istar);
}
```



