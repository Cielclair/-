# 第10章 DOM

## 10.1 节点层次

### 10.1.1 Node 类型

### 10.1.2 Document 类型

在浏览器中，`document` 对象是 `HTMLDocument` （继承自 `Document` 类型）的一个实例，表示整个 HTML 页面。

而且，`document` 对象是 `window` 对象的一个属性，因此可以将其作为全局对象来访问。

#### 4. 特殊集合

除了属性和方法，`document` 对象还有一些特殊的集合。这些集合都是 `HTMLCollection` 对象，为访问文档常用的部分提供了快捷方式，包括

- `document.anchors`

  > 包含文档中所有带 `name` 特性的 `<a>` 元素

- `document.forms`

  > 包含文档中所有 `<form>` 元素，与 `document.getElementsByTagName("form")` 得到的结果相同

- `document.images`

  > 包含文档中所有 `<img>` 元素，与 `document.getElementsByTagName("img")` 得到的结果相同

- `document.links`

  > 包含文档中所有带 `href` 特性的 `<a>` 元素

这个特殊集合始终都可以通过 `HTMLDocument` 对象访问到，而且，与 `HTMLDocument` 对象类似，集合中的项也会随着当前文档内容的更新而更新。

### 10.1.3 Element 类型

#### 1. HTML 元素

所有 HTML 元素都是由 `HTMLElement` 或者其更具体的子类型来表示的。

#### 2. 取得特性

`getAttribute()`

#### 3. 设置特性

`setAttribute()`

#### 4. attributes 属性

#### 5. 创建元素

`document.createElement()`

#### 6. 元素的子节点

元素也支持 `getElementsByTagName()` 方法

### 10.1.4 Text 类型

### 10.1.5 Comment 类型

## 10.2 DOM操作技术

### 10.2.1 动态脚本

### 10.2.2 动态样式

### 10.2.3 操作表格

### 10.2.4 使用 NodeList

## 10/3 小结

DOM 操作往往是 JavaScript 程序中开销最大的部分，因而访问 NodeList 导致的问题为最多。NodeList 对象都是“动态的”，这就意味着每次访问 NodeList 对象，都会运行一次查询。有鉴于此，最好的办法就是尽量减少 DOM 的操作。