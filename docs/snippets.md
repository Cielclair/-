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