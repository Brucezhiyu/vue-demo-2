# 《浅析Vue》
1. Vue的两个版本
2. 如何使用template和render
3. 如何用codesandbox.io 写Vue代码
---
## Vue的两个版本
1. 完整版：vue.js
2. 完整版(生产环境)：vue.min.js
3. 只包含运行时版：vue.runtime.js
4. 只包含运行时版(生产环境)：vue.runtime.min.js
##### 完整版：同时包含编译器和运行时的版本。
##### 编译器：用来将模板字符串编译成为 JavaScript 渲染函数的代码。
##### 运行时：用来创建 Vue 实例、渲染并处理虚拟 DOM 等的代码。基本上就是除去编译器的其它一切。
tips: UMD版本可以通过引入script 标签直接引入，详情见bootcdn.cn。

---
## 如何使用template和render
使用template，如果你需要在客户端编译模板 (比如传入一个字符串给 template 选项，或挂载到一个元素上并以其 DOM 内部的 HTML 作为模板)，就将需要加上编译器,即使用运行时版+编辑器，即完整版。
```js
// 需要编译器
new Vue({
  template: '<div>{{ hi }}</div>'
})
```
使用render，即只包含运行时版
```js
// 不需要编译器
new Vue({
  render (h) {
    return h('div', this.hi)
  }
})
```

---
## 如何用codesandbox.io 写Vue代码
进入codesandbox.io——>creat sandbox——>选择Vue,即可更改并及时预览代码，下载代码。