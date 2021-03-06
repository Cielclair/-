# 第8章 BOM

ECMAScript是JavaScript的核心，但如果要在Web中使用JavaScript，那么BOM（浏览器对象模型）则无疑才是真正的核心。**BOM提供了很多对象，用于访问浏览器的功能**，这些功能与任何网页内容无关。这些对象在浏览器中得以存在，很大程度上是由于它们提供了与浏览器的互操作性。

## 8.1 window对象

BOM 的核心对象是 `window`，它表示**浏览器的一个实例**。

在浏览器中，`window` 对象有双重角色，它

- 既是通过 JavaScript 访问浏览器窗口的一个接口，

- 又是 ECMAScript 规定的 Global 对象。

  > 这意味着在网页中定义的任何一个对象、变量和函数，都以 `window` 作为其 Global 对象，因此有权访问 `parseInt()` 等方法。

### 8.1.1 全局作用域

### 8.1.2 窗口关系及框架

### 8.1.3 窗口位置

### 8.1.4 窗口大小

### 8.1.5 导航和打开窗口

### 8.1.6 间歇调用和超时调用

JavaScript是单线程语言，但它允许通过设置**超时值**和**间歇时间值**来调度代码在特定的时刻执行。

调用 `setTimeout()` 之后，该方法会返回一个数值ID，表示超时调用。这个超时调用ID是计划执行代码的唯一标识符，可以通过它来取消超时调用。

> 在使用超时调用时，没有必要跟踪超时调用ID，因为每次执行代码之后，如果不再设置另一次超时调用，调用就会自行停止。

取消间歇调用的重要性要远远高于取消超时调用，因为在不加干涉的情况下，间歇调用将会一直执行到页面卸载。

调用 `setInterval()` 方法同样也会返回一个间歇调用ID，该ID可用于在将来某个时刻取消间歇调用，可以使用 `clearInterval()` 方法并传入相应的间歇调用ID。

?> 一般认为，使用超时调用来模拟间歇调用是一种最佳模式。

在开发环境下，很少使用真正的间歇调用，原因是后一个间歇调用可能会在前一个间歇调用结束之前启动。

### 8.1.7 系统对话框

## 8.2 location对象

## 8.3 navigator对象

## 8.4 screen对象

## 8.5 history对象

