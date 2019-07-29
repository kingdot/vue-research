# 前端发展现状分享及Vue初识

> 2019-07-28 王点

## 一、前端发展简史（主要）

![](https://note.youdao.com/yws/api/personal/file/229A1D40959D4D2CAA0D08AFD82864A0?method=download&shareKey=24aa8a727c8f93b65da235933950d7ce)

`ECMAScript` 是 `ECMA` 发布的语法规范，可以有各种实现：`JavaScript` 是其实现之一，`ActionScript`（Adobe开发）也是其实现之一。

## 二、现在的前端跟以前比最大的变化是？

### 1. 速度变快了：

![](https://note.youdao.com/yws/api/personal/file/6A41E0433D664652ACA18EB1FDAB0365?method=download&shareKey=389aca22c38b3b1afc95ad7e65a61275)

[2009年V8引入JIT，JavaScript执行速度提升20~50倍](https://cloud.tencent.com/developer/article/1089927)

[V8十年，从农场诞生的星球最强 JS 引擎（又提升了近4倍）](https://v8project.blogspot.com/2018/09/10-years.html) 

### 2. 朝着模块化，工程化，标准化演进：

[NodeJs的出现，使npm生态繁荣](http://www.modulecounts.com/)

[NPM 2018 年回顾与 2019 年预测](https://www.infoq.cn/article/CuSLOXWJaP*MUAGAoayR)

### 3. SPA流行，MVVM兴起：

![](https://note.youdao.com/yws/api/personal/file/01A663EA8FD8457AB9D2004632AB7485?method=download&shareKey=edfb3039002ca3f3daa2da4fba5b44aa)

`Angular`、`React`、`Vue` 三分天下，`jQuery` 逐渐退出历史舞台

## 三、现在的前端能肝（干）什么？

1. 各种酷炫网站

2. 微信小程序/小游戏，支付宝小程序/小游戏

3. 安卓，iOS应用

4. 桌面应用（windows应用程序）

5. 服务端程序

6. 机器学习

7. 操作系统与嵌入式

8. … …

## 四、工欲善其事必先利其器

![](https://note.youdao.com/yws/api/personal/file/FDD15990D39447C9BB81188F1BEE1F10?method=download&shareKey=3520103cd62eead8b098404f75ed9915)

## 五、框架能给我们带来什么？

1. 对于 `HTML` 来说：

    告别繁琐的 `dom` 操作，向 `html` 文件中满屏的 `id` 说再见，向 `getElementByXXX`，`querySelector(…)` 说再见，向 `$(“xxx”).xx(XXX)` 说再见

2. 对于 `CSS` 来说；

    大胆使用最新的 `css3` 特性，不使用任何 `JS` 动画库即可轻松制作狂拽酷炫X炸天的特效。

3. 对于 `JS` 来说：

    使用面向未来的 `ECMAscript6+` 语法编写程序：

    - 标准的模块化定义，让代码不再混乱，不再污染全局作用域

    - 全新的变量声明方式：`let`，`const`，告别函数作用域 `var`

    - 好用的`class`，`extends`，`constructor`，更加“面向对象”

    - 使用 `Promise` 或者 `Async/Await` 解决异步问题，告别恐怖的回调地狱

    - 超好用的模板字符串，不再需要各种“+，\n”号拼接 `html`

4. 对于 `自动化程度` 来说：

    使用全新的基于 `Node.js` 的构建工具，为前端工程化赋能。

    `webpack`，`grunt`，`gulp` 类似于 `Java` 世界里面的 `maven`，`gradle`，提供诸如以下的功能：

    - 依赖管理

    - 单元测试

    - 热更新

    - 自动化打包

    - 代码混淆，压缩优化

    - 一键部署

讲了这么多使用框架的好处，但口说无凭，我们接下来做个框架使用率的小调研~

## 六、框架都有谁在用？

1. **Angular**：常应用于内部管理系统，OA平台等

2. **React**：facebook，知乎，优酷，滴滴，美团，拼多多，抖音... ...

3. **Vue**：GitLab,  哔哩哔哩,  爱奇艺，简书，掘金，蘑菇街，今日头条，招商银行校园招聘... ...

![](https://note.youdao.com/yws/api/personal/file/3829BB8E70E14DA7957C4F13D741018F?method=download&shareKey=00f2008a199da01dbaff26ee6ceb4535)

当然，我也在用( ' – ' )

考虑到学习曲线是否陡峭和是否允许渐进性升级，最后决定我们这次选择使用 `Vue`，因此接下来，我们一起走进 `Vue` 的世界看一看~

## 七、Vue初识

最开始听说 `Vue` 之后，并没有马上去了解它有什么高明的设计和好用的特性，而是打开了 "全球最大的同性交友网站 GitHub"，看了下它的 `Star` 数量：

![](https://note.youdao.com/yws/api/personal/file/AA1E3897693647C09E9597F647359956?method=download&shareKey=a86c115bb2e878daee74c09707a51c30)

可能有些朋友不太了解 14w+ `Star` 意味着什么，为了便于大家理解，我们来看下 "统治 Java 领域多年的王者 Spring" 系列的 `Star` 数目：

![](https://note.youdao.com/yws/api/personal/file/FCD7783A256047D58263CAE50F2FD44D?method=download&shareKey=e216a66356a618901b88750b5902c4e9)

相信你们此刻肯定和我一样，是这个表情 ⬇

![](https://note.youdao.com/yws/api/personal/file/11AD58B2DE72416086891251A04E3F07?method=download&shareKey=d6a89528962367e3a9e920d3b9fb3b47)

OK，废话不多说，既然 `Vue` 受到这么多人的认可，我们接下来就一起看看大名鼎鼎的 `Vue` 到底有什么独到之处~

## 八、Vue创新之处

1. 允许渐进式升级

2. 巧妙地设计了一套响应式系统来实现MVVM，实现精准的变更检测

    ```
    ~v1.x    Object.defineProperty(obj, "key", {
                enumerable: true,
                configurable: true,
                writable: false,
                get: function(){...},
                set: function(){...}
            });

    v2.0~   Proxy  代理对某个对象的所有操作
    ```

3. 吸收了 `Angular` 的模板语法和 `React` 的虚拟 `DOM`，集众家之所长

4. 独创 **单文件组件**，实现业务松耦合，组件强内聚

篇幅有限，具体怎么通过 `Vue` 开发项目，官方文档给的很详细，这里就不再赘述啦~

当然，`Vue` 还有很多其他优秀的设计，大家有兴趣的话也可以自行探索~

## 九、项目整合开发方案调研

### 采用单页面模式开发还是保留传统的多页面？

| - | 单页面应用 | 多页面应用 |
| :----:| :----: | :----: |
| 组成 | 一个外壳页面和多个页面组件组成 | 多个完整页面构成 |
| 资源共用（css, js） | 共用，只需在外壳部位加载 | 不共用，每个页面都需引入 |
| 刷新方式 | 页面局部刷新或更改 | 整页刷新 |
| 页面跳转后公共资源是否重新加载 | 否 | 是 |
| url模式 | a.com/#/pageone | a.com/pageone.html |
| 用户体验 | 各页面间的切换快，用户体验良好	页面间的切换加载缓慢，流畅度不够，用户体验比较差，特别是移动设备 |
| 转场动画 | 容易实现 | 无法实现 |
| 数据传递 | 容易 | 依赖url传参，cookie, localStorage等 |
| 搜索引擎优化 | 需要单独方案，实现较为困难，不利于SEO检索，可利用服务器端渲染（SSR）优化 | 实现方法简易，利用SEO优化 |
| 适用范围 | 高要求的体验度，追求页面的流畅性的应用，特别是移动端应用 | 适应于高度要求支持搜索引擎的应用 |
| 开发难度 | 高一些，需要专门的框架来降低开发难度 | 低一些，框架选择容易 |

### 使用基于NodeJs的构建工具开发还是使用传统的ES5开发？

1. 不使用构建工具

- 全局定义 (Global definitions) 强制要求每个 `component` 中的命名不得重复

- 字符串模板 (String templates) 缺乏语法高亮，在 `HTML` 有多行的时候，需要用到丑陋的

- 不支持 CSS (No CSS support) 意味着当 `HTML` 和 `JavaScript` 组件化时，`CSS` 明显被遗漏

- 没有构建步骤 (No build step) 限制只能使用 `HTML` 和 `ES5 JavaScript`, 而不能使用预处理器，如 `Pug` (formerly Jade) 和 `Babel`

2. 使用构建工具

- 要学习 `ES6` 的内容和其他配套的知识，有一定学习成本

## 十、要解决的一些问题

1. 打包出的目录结构跟原项目保持一致，从而复用静态资源（图片，公共样式）

2. 原项目路由不受影响（后端需要对单页面和多页面做不同的适配调整）

3. 如果是单页面方案，需进行页面首次加载提速优化

4. 测试页面加载性能

## 写在最后

> 学习一门新技术，最好的方法就是把它用起来~

## 谢谢大家!