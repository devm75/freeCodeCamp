---
id: 587d7db2367417b2b2512b8c
title: 使用 IIFE 创建一个模块
challengeType: 1
forumTopicId: 301332
---

# --description--

一个`自执行函数表达式`（`IIFE`）通常用于将相关功能分组到单个对象或者是`模块`中。例如，先前的挑战中定义了一个混合类：

```js
function glideMixin(obj) {
  obj.glide = function() {
    console.log("Gliding on the water");
  };
}
function flyMixin(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  };
}
```

我们可以将这些`mixins`分成以下模块：

```js
let motionModule = (function () {
  return {
    glideMixin: function(obj) {
      obj.glide = function() {
        console.log("Gliding on the water");
      };
    },
    flyMixin: function(obj) {
      obj.fly = function() {
        console.log("Flying, wooosh!");
      };
    }
  }
})(); // 末尾的两个括号导致函数被立即调用
```

注意：一个`自执行函数表达式`（`IIFE`）返回了一个`motionModule`对象。返回的这个对象包含了作为对象属性的所有`mixin`行为。 `模块`模式的优点是，所有的运动行为都可以打包成一个对象，然后由代码的其他部分使用。下面是一个使用它的例子：

```js
motionModule.glideMixin(duck);
duck.glide();
```

# --instructions--

创建一个名为`funModule`的`模块`，将这两个`mixins`：`isCuteMixin`和`singMixin`包装起来。`funModule`应该返回一个对象。

# --hints--

`funModule`应该被定义并返回一个对象。

```js
assert(typeof funModule === 'object');
```

`funModule.isCuteMixin`应该访问一个函数。

```js
assert(typeof funModule.isCuteMixin === 'function');
```

`funModule.singMixin`应该访问一个函数。

```js
assert(typeof funModule.singMixin === 'function');
```

# --solutions--

