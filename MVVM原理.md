## 一、概念介绍

`MVVM` 是 `Model-View-ViewModel` 的简写。它本质上就是 `MVC` （Model-View- Controller）的改进版，即模型-视图-视图模型。

【模型】指的是js生成的或者来自后端的数据，【视图】指的是所看到的页面，【视图模型】mvvm模式的核心，它是连接view和model的桥梁。

![](https://img2018.cnblogs.com/blog/1621187/201903/1621187-20190318205433983-1935700508.jpg)

VM有两个方向：
- 将【模型】转化成【视图】，即将后端传递的数据转化成所看到的页面。实现的方式是：数据绑定。
- 将【视图】转化成【模型】，即将所看到的页面转化成后端的数据。实现的方式是：DOM 事件监听。这两个方向都实现的，我们称之为数据的双向绑定。

## 二、Vue的VM实现

### M => V
在编译模板的过程中，对data中出现在模板中的变量进行响应式处理，即拦截set方法。当数据改变时，VM即可知道，随后触发视图更新；
```javascript
// ~v1.x    
Object.defineProperty(obj, "key", {
    enumerable: true,
    configurable: true,
    writable: false,
    get: function(){...},
    set: function(){...}
});

// v2.0~   
Proxy  代理对某个对象的所有操作
```
### V => M
使用事件监听，获取到V的改变，进而使用V的值更新M。

## 三、React的VM实现

### M => V
设计了一个setState()方法，用于在M发生改变或者主动想要更新视图时使用。

### V => M
使用事件监听，获取到V的最新值，由是否调用setState()决定视图是否更新。

```javascript
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }
 
  componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }
 
  componentWillUnmount() {
    clearInterval(this.timerID);
  }
 
  tick() {
    this.setState({
      date: new Date()
    });
  }
  handleClick(){
    this.componentWillUnmount()
  }
 
  render() {
    return (
      <div>
        <h1 onClick="()=>this.handleClick()">Hello, world!</h1>
        <h2>现在是 {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}
 
ReactDOM.render(
  <Clock />,
  document.getElementById('example')
);
```

## 四、Angular的VM实现

### M => V
第一屏渲染完毕的时候，所有同步代码已经全部执行完毕，剩下有可能引起页面变化的就是异步行为，angular覆写所有可能使数据发生变化的api（异步api），比如事件监听、网络请求等，因此所有会改变数据的操作都会被angular捕获到，然后angular用新值去通知视图更新。

### V => M
一般视图的改变是因为用户触发了操作事件，而这部分行为也会被angular捕获到，因此V => M实际上也会被转化 V => M => V

## 五、总结
在MVVM的框架下视图和模型是不能直接通信的。它们通过ViewModel来通信，ViewModel通常要实现一个observer观察者，当数据发生变化，ViewModel能够监听到数据的这种变化，然后通知到对应的视图做自动更新，而当用户操作视图，ViewModel也能监听到视图的变化，然后通知数据做改动，这实际上就实现了数据的双向绑定。并且MVVM中的View 和 ViewModel可以互相通信。
