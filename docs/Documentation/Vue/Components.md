# Components

**一个组件的 `data` 选项必须是一个函数**，因此每个实例可以维护一份被返回对象的独立的拷贝：

```javascript
data: function () {
  return {
    count: 0
  }
}
```

如果 Vue 没有这条规则，对一个实例的操作就可能会影响到*其它所有实例*







## keep-alive

`<keep-alive>` 包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们。和 `<transition>` 相似，`<keep-alive>` 是一个抽象组件：它自身不会渲染一个 DOM 元素，也不会出现在组件的父组件链中。

当组件在 `<keep-alive>` 内被切换，它的 `activated` 和 `deactivated` 这两个生命周期钩子函数将会被对应执行。

主要用于保留组件状态或避免重新渲染。



> keep-alive是Vue提供的一个抽象组件，用来对组件进行缓存，从而节省性能，在页面渲染完毕后不会被渲染成一个DOM元素。



