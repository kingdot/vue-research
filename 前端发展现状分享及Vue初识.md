# JavaScript概览

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
2. 开始从上到下依次执行同步代码，遇到异步代码根据其类型分别加入到MacroTask和MicroTask队列
```javascript
let ab = [0,1]
console.log(ab)
setTimeout(()=>{console.log('i am macroTask')}, 0); // 加入MacroTask
new Promise((resolve, reject)=>{
  console.log([1,2,3,4,5,6].map(f=>f*f));
}).then(()=>{console.log('i am microTask')}); // 加入MicroTask
```
3. 
