# 第三方 js 使用

```bash
$ vue serve App.vue
```

将 [countUp.js](https://github.com/inorganik/countUp.js/) 封装成 vue 组件

ref，如果是 dom 元素，则获取到 dom 元素；如果是组件，则获取到的是组件实例

并不是一个可以用于生产的组件，只是为了简单展示组件封装。生产环境可以参考 [vue-countTo](https://github.com/PanJiaChen/vue-countTo)

---

引用组件步骤：

1. 先引入（import or require）
2. 再注册（组件内 components 选项中注册，或者 Vue.component 方法全局注册）
3. 最后使用 `<my-component></my-component>`