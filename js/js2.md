#### 41、正则表达式构造函数var reg=new RegExp("xxx")与正则表达字面量var reg=//  有什么不同？匹配邮箱的正则表达式？

使用正则表达式构造函数的时候需要转义引号（即\"表示"）,并且还需要双反斜杠表示一个斜杠，使用正则表达字面量的效率更高

```
var regMail=/^([a-zA-Z0-9_-]+@([a-zA-Z0-9_-])+((.[a-zA-Z0-9_-]{2,3}){1,2})$/;
```



#### 42、下面代码输出什么

```js
for(var i=1;i<=3;i++){
    setTimeout(function(){
        console.log(i);
    },0);
};
//输出4   4   4
```

改成输出1 2 3

``` 
for(var i=1;i<=3;i++){
    setTimeout((function(a){//改成立即执行函数
        console.log(i);
    })(i),0);
};
//输出1  2  3
```



#### 43、写一个function清除字符串前后得空格

```js
if(!String.prototype.trim){
    String.prototype.trim=function(){
        return this.replace(/^\s+/,"").replace(/\s+$/,"");
        //  \s匹配空白字符：回车、换行、制表符tab空格
    }
}
//test the function
var str="\t\n test string".trim();
alert(str=="test string");//alerts "true"
```

#### 44、js中callee和caller的作用

arguments.callee获得当前函数的引用

caller是返回一个对函数的引用，该函数调用了当前函数；

callee是返回正在被执行的function函数，也就是所制定的function对象的正文。

问题：如果一对兔子每个月生一对兔子，一对新生兔，从第二个月起就开始生兔子；假定每对兔子都是一雌一雄，试问一对兔子，第n个月能繁殖成多少对兔子？使用callee

````js
var result=[];
function fn(n){//斐波拉契数列
    if(n==1){
        return 1;
       
    }else if(n==2){
        return 1;
    }else{
        if(result[n]){
            return result[n];
        }else{
            //argument.callee()表示fn()
            result[n]=argument.callee(n-1)+arguments.callee(n-2);
            return result[n];
        }
    }
}
````

#### 45、下列哪一条语句会产生运行错误

A、var _变量=NaN;

B、var 0bj=[];

c、var obj=//;

d、var obj={};

答案：B   陷井题，注意这里的B是零开头的，变量不能以数字开头

#### 46 以下两个变量a和b，a+b哪个结果是NaN  

A、var a=undefined,b=NaN;   

B、var a='123',b=NaN;

C、var a=undefined,b=NaN;

D、var a=NaN,b='undefined';