# Snippets

> Hey I'm trying to make a point here. --- Barney Stinson the guy's awesome



- 用**中括号**来访问对象内部的属性时，**键值**需要是字符串字面值。

```javascript
var obj = {
  a: "hello world",
  b: 42
}

var b = "a";

obj[b]; // "hello world"
obj["b"]; // 42
```



- 函数用作对象的方法时，运用点号或方括号形式的**属性存取符**从对象读取方法，再在后面跟上用圆括号包围的参数，方法内的 `this` 关键字会被动态绑定到调用该方法的对象。

```javascript
let o = {
  a: 1,
  b() {
    console.log(this.a);
  }
};

o["b"](); // 1
```





- 内置对象 `String` 实际上是一个内置函数，可以当作构造函数来使用，从而可以构造一个对应子类型的新对象。

```javascript
var strPrimitive = "I am a string";
typeof strPrimitive; // "string"
strPrimitive instanceof String; // false

var strObject = new String("I am a string");
typeof strObject; // "object"
strObject instanceof String; // true
```

> 原始值 `"I am a string"` 并不是一个对象，它只是一个字面量，并且是一个不可变的值。如果要在这个字面量上执行一些操作，比如获取长度、访问其中某个字符等，需要将其转换为 `String` 对象。



## 作用域

- 为变量显示声明块作用域，并对变量进行本地绑定是非常有用的工具

```javascript

```



- 作用域气泡的结构和互相之间的位置关系给引擎提供了足够的位置信息，引擎用这些信息来查找标识符的位置。

```javascript
function foo(a) {
  var b = a * 2;
  function bar(c) {
    console.log(a, b, c);
  }
  bar (b * 3);
}

foo(2) // 2, 4, 12
```

在这个代码片段中，**引擎**执行 `console.log(..)` 的声明，并查找 `a`、`b` 和 `c` 三个变量的引用。

它首先从最内部的作用域，也就是 `bar(..)` 函数的作用域气泡开始查找。**-->** 引擎无法在这里找到 `a`，因此会去上一级到所嵌套的 `foo(..)` 的作用域中继续查找。**-->** 在这里找到了 `a`，因此引擎使用了这个引用。

对 `b` 来讲也是一样的。而对 `c` 来说，引擎在 `bar(..)` 中就找到了它。



?> 作用域查找会在找到第一个匹配的标识符时停止。

> 在多层的嵌套作用域中可以定义同名的标识符，这叫作“遮蔽效应”（内部的标识符“遮蔽”了外部的标识符）。抛开遮蔽效应，作用域查找始终从运行时所处的最内部作用域开始，逐级向外或者说向上进行，直到遇见第一个匹配的标识符为止。

