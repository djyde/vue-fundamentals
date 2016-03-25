# MVVM 初探

MVVM 是 Model-View-ViewModel 的简称，顾名思义，ViewModel 实际上把 View 和 Model 联系在一起，当 Model 发生变化的时候，会通过双向数据绑定，把变化反映到 View 中。

ViewModel 极大地提高了开发的效率，因为双向绑定远远地降低了开发者手动管理 DOM State 的必要性。在这里可以举一个非常简单的例子：

```html
<img src="foo.png" id="pic"/>
<button onclick="hide()">click me</button>

<script>
  var hide = function(){
    document.querySelector('#pic').style.display = 'none'; // 核心操作
  }
</script>
```

以上是用原生 JavaScript DOM 操作实现的点击按钮隐藏一张图片，下面是 Vue.js 实现：

```html
<div id="app">
  <img src="foo.png" id="pic", v-show="isShow"/>
  <button @click="hide">click me</button>
</div>

<script>
  var app = new Vue({
  el: '#app',
    data: {
      isShow: true
    },
    methods: {
      hide: function(){
        this.isShow = false; // 核心操作
      }
    }
  })
</script>
```

这样看上去，好像用原生 DOM 实现的代码量要比用框架少得多，当然了，如果整一个网站只需要实现几个像这样的功能，手写 DOM 也未尝不可，使用框架或库反而就成了画蛇添足。但是，在大多的情况下，在我们开发稍微复杂一点的网站时，DOM 操作就远远不止这样了。

因此，这两个实现之间的区别，并非体现在代码量上，而是整个开发思维的变化。对比两个实现的核心操作，前者的思路是拿到 DOM，然后根据需求（这里的图片的隐藏）再去操作、修改 DOM。而后者则是通过 v-show 指令 (directive) 绑定数据 isShow，开发者只需要**决定元素是否显示**，DOM 操作交给 Vue.js。


