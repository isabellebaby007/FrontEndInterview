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

ie9以前：  attachEvent/detachEvent：进行事件类型传参需要带上on前缀；这种方式只支持事件冒泡，不支持事件捕获

#### 6、IE和DOM事件流的区别

1、执行顺序不一样

2、参数不一样

3、事件加不加on

4、this指向问题

#### 7、IE和标准下有哪些兼容性得写法

```js
var ev=ev||window.event
document.documentElement.clientWidth||document.body.clientWidth
var target=ev.srcElement||ev.target
```

#### 8、call和apply的区别

apply:调用一个对象的方法，用另一个对象替换当前对象。例如：B.apply(A, arguments);即A对象应用B对象的方法。

call:调用一个对象的一个方法，用另一个对象替换当前对象。例如：B.call(A, args1,args2);即A对象调用B对象的方法。

相同点：方法功能一样，第一个参数的作用一样

不同点：传入的列表形式不一样：

- call可以传入多个参数；

- apply只能传入两个参数，所以其第二个参数往往是作为数组形式传入

  意义：实现多重继承

  ​

```js
toString.call([],1,2,3)
toString.apply([],[1,2,3])
Object.call(this,obj1,obj2,obj3)
Object.apply(this,arguments)
```

```js
var scopeTest = (function(){ //考察了 this 的含义
window.a=2;
function fn(b){
this.b = b;
console.log(this.a);
}
var obj = {a:4,fn:fn};
fn();
obj.fn();
fn.call(obj);fn.call(null);
fn.apply(obj);fn.apply(null);
var fninstance = new fn(8);
console.log(fninstance.b);
})();

```



```js
function fruits() {} 
fruits.prototype = {
color:"red",
say: function() {console.log(this.color);}
}
var apple = new fruits();
 
apple.say();
var banana = {color:"yellow"};
apple.say.call(banana);
apple.say.apply(banana);

```



#### 9、b继承a的方法

function b(){}

b.prototype=new a;

#### 10、js this指针、闭包、作用域

#### 11、事件委托是什么

addEventListener/attachEvent

利用事件冒泡的原理，让自己所触发的事件，让他的父元素代替执行

#### 12、闭包是什么，有什么特性，对页面有什么影响

闭包：能够读取其他函数内部变量的函数

缺点：滥用闭包会造成内存泄露，因为闭包引用到的包裹函数中定义的变量不会释放，所以在必要时候，应该及时释放这个闭包函数。

https://zhuanlan.zhihu.com/p/22486908





