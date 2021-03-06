---
id: 587d7db0367417b2b2512b82
title: 了解原型链
challengeType: 1
forumTopicId: 301329
---

# --description--

JavaScript 中所有的对象（除了少数例外）都有自己的`原型`。而且，对象的`原型`本身也是一个对象。

```js
function Bird(name) {
  this.name = name;
}

typeof Bird.prototype; // => object
```

正因为`原型`是一个对象，所以`原型`对象也有它自己的`原型`！这样看来的话，`Bird.prototype`的`原型`就是`Object.prototype`：

```js
Object.prototype.isPrototypeOf(Bird.prototype);
// 返回 true
```

这有什么作用呢？你可能还记得我们在上一个挑战中学到的`hasOwnProperty`方法：

```js
let duck = new Bird("Donald");
duck.hasOwnProperty("name"); // => true
```

`hasOwnProperty`是定义在`Object.prototype`上的一个方法，尽管在`Bird.prototype`和`duck`上并没有定义该方法，但是我们依然可以在这两个对象上访问到。这就是一个`原型`链。 在这个`原型`链中，`Bird`构造函数是`父级`，`duck`是`子级`。`Object`则是`Bird`构造函数和`duck`实例共同的`父级`。 `Object`是 JavaScript 中所有对象的`父级`，也就是原型链的最顶层。因此，所有对象都可以访问`hasOwnProperty`方法。

# --instructions--

修改以下代码使其展示出正确的原型链。

# --hints--

你的代码应该展示`Object.prototype`是`Dog.prototype`的原型。

```js
assert(/Object\.prototype\.isPrototypeOf/.test(code));
```

# --solutions--

