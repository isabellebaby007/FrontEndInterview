# js部分
#### 1、js的typeof返回哪些数据类型

object       number     function     boolean    undefined   string 

```js
typeof null;  //object
typeof isNaN;  //
typeof isNaN(123);
typeof [];  //object
Array.isARRAY();
toString.call([]);  //[object Array]
var arr=[]; 
arr.constructor; //Array
```

#### 2、列举3种强制类型转换和2种隐式类型转换

强制：  parseInt   ,     parseFloat,    Number()

隐式类型转换：  ==

```js
1=='1';//true
null==undefined;//true
```

#### 3、split()和join()的区别

split:   切割成数组的形式

join：将数组转成字符串

```js
var str="How are you doing today?";  
document.write(str.split(" ")+"<br/>"); //How,are,you,doing,today?
document.write(strsplit("")+"<br/>");//H,o,w, ,a,r,e, ,y,o,u, ,d,o,i,n,g, ,t,o,d,a,y,?
document.write(str.split(" ",3));//How,are,you


var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr.join("."));//George.John.Thomas

```

#### 4、数组方法pop(),push(),unshift(),shift()

push()  :   尾部添加        pop()  :尾部删除

unshift()   头部添加        shift（） 头部删除

#### 5、传统事件绑定和普通事件的区别

普通添加事件的方法：

普通添加事件得方法不支持添加多个事件，后面得绑定会覆盖前面得绑定；不支持DOM事件流

```js
var btn=document.getElementById("hello");
btn.onclick=function(){
    alert(1);
}
btn.onclick=function(){
    alert(2);
}
//只会alert  2
```

事件绑定方式添加事件的方法：

所有得绑定会一次触发；支持DOM事件流；进行事件绑定传参不需要on前缀

事件捕获->目标元素阶段->事件冒泡阶段

```js
var btn=document.getElementById("hello");
btn.addEventListener("click",function(){
    alert(1);
},false);
btn.addEventListener("click",function(){alert(2)},false); //false表示在事件捕获阶段   true表示在事件冒泡阶段
//先alert   1再alert  2
```

#### 6、IE和DOM事件流得区别



