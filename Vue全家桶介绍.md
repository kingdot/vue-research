# vue全家桶都有什么
全家桶，顾名思义，对于开发一个完整的中大型单页面应用项目所必须的所必须的插件和框架。

注：此文章主要讲解vue-cli脚手架开发方式，主要介绍各插件安装方法及其功能特点，不介绍各插件的具体使用方式，具体使用方式详见其他详细介绍文章。

## 一、vue-cli
vue-cli也叫脚手架，官方定义为Vue.js 开发的标准工具！相比scirpt标签引入，脚手架具有如下特点：
- 功能丰富
对 Babel、TypeScript、ESLint、PostCSS、PWA、单元测试和 End-to-end 测试提供开箱即用的支持。
- 易于扩展
它的插件系统可以让社区根据常见需求构建和共享可复用的解决方案。
- 无需 Eject
Vue CLI 完全是可配置的，无需 eject。这样你的项目就可以长期保持更新了。
- CLI 之上的图形化界面
通过配套的图形化界面创建、开发和管理你的项目。
- 即刻创建原型
用单个 Vue 文件即刻实践新的灵感。
- 面向未来
为现代浏览器轻松产出原生的 ES2015 代码，或将你的 Vue 组件构建为原生的 Web Components 组件。

安装
```bash
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```
//安装完成后创建一个项目，vue ui为图形化构建，相对简单（推荐）
```bash
vue create my-project
# OR
vue ui
```

## 二、vueRouter
Vue Router 是 Vue.js 官方的路由管理器。它和 Vue.js 的核心深度集成，让构建单页面应用变得易如反掌。包含的功能有：

- 嵌套的路由/视图表
- 模块化的、基于组件的路由配置
- 路由参数、查询、通配符
- 基于 Vue.js 过渡系统的视图过渡效果
- 细粒度的导航控制
- 带有自动激活的 CSS class 的链接
- HTML5 历史模式或 hash 模式，在 IE9 中自动降级
- 自定义的滚动条行为

vueRouter 安装
```bash
npm install vue-router
//安装后在mainjs引入
import VueRouter from 'vue-router'

Vue.use(VueRouter)
```

## 三、vuex
Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。Vuex 也集成到 Vue 的官方调试工具 devtools extension，提供了诸如零配置的 time-travel 调试、状态快照导入导出等高级调试功能。

什么情况下我应该使用 Vuex？
Vuex 可以帮助我们管理共享状态，并附带了更多的概念和框架。这需要对短期和长期效益进行权衡。

使用Vuex的常见场景：
- 用户登录信息
- 需要跨组件共享的数据
- SSR

如果您不打算开发大型单页应用，使用 Vuex 可能是繁琐冗余的。确实是如此——如果您的应用够简单，您最好不要使用 Vuex。一个简单的 store 模式就足够您所需了。但是，如果您需要构建一个中大型单页应用，您很可能会考虑如何更好地在组件外部管理状态，Vuex 将会成为自然而然的选择。

安装方法
```bash
npm install vuex --save
```

## 四、Axios
Axios 是一个基于 promise 的 HTTP 库，可以用在浏览器和 node.js 中。

特性
- 从浏览器中创建 XMLHttpRequests
- 从 node.js 创建 http 请求
- 支持 Promise API
- 拦截请求和响应
- 转换请求数据和响应数据
- 取消请求
- 自动转换 JSON 数据
- 客户端支持防御 XSRF

安装方法
```bash
npm install axios
```

## 五、搭配UI框架如：iview、vant、elementUI
iview 一套基于 Vue的高质量UI 组件库(分为小程序和pc端等不同版本)；   
vant 轻量、可靠的移动端 Vue 组件库,是有赞开源的一套基于 Vue 2.0 的 Mobile 组件库,旨在更快、更简单地开发基于 Vue 的美观易用的移动站点。   
Ant Design Vue 是 Ant Design 的 Vue 实现，开发和服务于企业级后台产品。   
elementUI 是基于 Vue 2.0 桌面端中后台组件库。
