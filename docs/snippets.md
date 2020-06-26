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

