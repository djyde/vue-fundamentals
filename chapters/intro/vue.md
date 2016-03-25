# Vue.js

[Vue.js](http://vuejs.org) 是由 [尤小右](https://github.com/yyx990803) 开发的一个专注于视图层的轻量级 MVVM 库，它虽然轻量，但提供了强大的组件系统，有利于模块化、组件化，即使应用变得越来越复杂，也不会增大维护成本，因此足以胜任被用于大型 Web App 的开发。目前国内已经有不少 [企业级应用案例](https://github.com/vuejs/vue/wiki/Projects-Using-Vue.js#enterprise-usage-in-production)，例如淘宝无线、饿了么大数据平台、UC 门户等等。

之所以称为库，意思是它并不是像 AngularJS 这样大而全的框架，相反，Vue.js 小而美，更加灵活，是真正的开箱即用。开始使用 Vue.js，你要做的，仅仅是告诉它，你要在哪个元素中开始使用它。

关于 Vue.js 和其它框架和库的对比，官方文档有比较 [详尽的论述](http://vuejs.org/guide/comparison.html)，这里我选择一些作译述：

- Vue.js 相当灵活，比 Angular 少有主观的解决方案，使得你可以用你喜欢的方式和其它你喜欢的库去进行应用开发，而不是像 Angular 一样，遵循着它的规定去写。这可能是 Angular 和 Vue.js 最主要的区别。
- Vue.js 的性能比 Angular 好，因为 Vue.js 并不使用脏检测。使用 Angular 时，当存在很多监测器的时候，由于这些监测器都需要重新计算，所以会程序变得缓慢。
- 在 Vue.js 中，指令（directives）和组件（components）有明确的区分，指令仅仅包含 DOM 操作，而组件包含自己的视图和数据逻辑，而在 Angular 中两者相当混淆。
- Vue.js 使用的是真实的 DOM，这和 React 用的 Virtual DOM 不同，人们通常认为 Virtual DOM 比一切都快，但 Vue.js 的数据热更新实际上比 React 要更快，并且不需要像 React 一样手动的用 `shouldComponentUpdate` 来优化。
