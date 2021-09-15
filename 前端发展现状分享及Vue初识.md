# JavaScript核心浅谈

## 两种构成
> JavaScript（浏览器端） = ECMAScript（语法核心） + BOM（浏览器对象模型） + DOM（文档对象模型）   
JavaScript（Nodejs端） = ECMAScript（语法核心） + ServerSideApi（文件/网络等）

## 执行模型
> 为了保证页面渲染的正确性，js采用单线程+事件循环的执行模型来运行JavaScript代码。

1. 预解析，先从上到下去全局作用域里扫描所有变量的定义（使用var声明的）以及函数的声明，并且把这些声明提升到这个作用域的最顶层。
```javascript
console.log(aa); // undefined
console.log(test); // f test(){}

var aa = 1;

function test(){
  console.log('hi')
}

// let 声明的不会提升
console.log(bb); // bb is not defined
let bb = 1;

```
2. 开始从上到下依次执行同步代码（单线程），遇到异步代码根据其类型分别加入到MacroTask和MicroTask队列（）
```javascript
let ab = [0,1]
console.log(ab)
setTimeout(()=>{console.log('i am macroTask')}, 0); // 加入MacroTask
new Promise((resolve, reject)=>{
  console.log([1,2,3,4,5,6].map(f=>f*f));
  resolve();
}).then(()=>{console.log('i am microTask')}); // 加入MicroTask
```
3. 同步代码执行完毕后首先会清空MicroTask队列，然后再去清空MacroTask队列。

## 基于原型链的函数（类）继承模型

### 原型存在的目的就是为了方便实现属性的继承

```javascript
var will = new Person("Will", 28);
var wilber = new Person("Wilber", 27);
```
![](https://images2015.cnblogs.com/blog/593627/201510/593627-20151030202438622-536991068.png)

### 原型链

1. 对于所有的对象，都有 `__proto__` 属性，且该属性指向该对象对应构造函数的原型对象   
2. 对于函数对象，除了 `__proto__` 属性之外，还有 `prototype` 属性，指向该函数的原型对象
3. 由于原型对象本身也是个对象，也有 `__proto__` 属性，指向其构造函数的原型对象，原型由`__proto__`层层连接起来的就构成了原型链。
![](https://images2015.cnblogs.com/blog/593627/201510/593627-20151030202435591-481237570.png)

```
function A(name, age){
  this.name = name;
  this.age = age;
  this.tall = '180cm';
}
A.prototype.funcA = function(){
  console.log(this.name + this.age)
}

function B(name, age, sex){
  A.apply(this, [...arguments].slice(0,2));
  this.sex = sex;
}
//B.prototype.__proto__ = A.prototype // 不建议使用
Object.setPrototypeOf(B.prototype, A.prototype)


let aa = new A('parent', 40);
let bb = new B('child', 18, 'male');
console.log(bb, bb.funcA())

```


举例：toString()方法的查找过程，length

## 基于作用域链和原型链的变量查找模型





