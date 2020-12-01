## this、call、apply、bind 异同

相同点：

1、bind、call`和`apply`的第一个参数`thisArg`，都是`func`运行时指定的`this（改变 this 指向）

2、call`和`apply在非严格模式下，则指定为 null 或 undefined 时会自动替换为指向全局对象、值为原始值(数字，字符串，布尔值)的`this`会指向该原始值的自动包装对象。

不同点：

1、call 和 apply 改变 this 指向后，立即执行函数；而 bind 不会立即执行，只会返回一个函数

2、`apply`只接收两个参数，第二个参数可以是数组也可以是类数组，其实也可以是对象，后续的参数忽略不计。`call`接收第二个及以后一系列的参数。

## call 实现

```javascript
Function.prototype.call2 = function(context) {
  // 改变this , 注意context 为 null | undefined 的情况
  // 非严格模式下，则指定为 null 或 undefined 时会自动替换为指向全局对象
  var context = context || window;
  context.fn = this; // 实例绑定到上下文
  
  // 获取参数
  var args = [];
  for(var i = 1, len = arguments.length; i < len; i++) {
      args.push('arguments[' + i + ']');
  }
  // 立即执行函数
  // var result = eval('context.fn(' + args +')');
  var result = context.fn(...args);

  delete context.fn
  return result;
}
```

## apply 实现

```
Function.prototype.apply2 = function(context, arr) {
  // 改变this
  // 如果这个函数处于非严格模式下，则指定为null和undefined的this值会自动指向全局对象(浏览器中就是window对象, node就是global)，
  // 同时值为原始值(数字，字符串，布尔值)的this会指向该原始值的自动包装对象。
  var context = context == null ? window : Object(context);
  context.fn = this; // 实例绑定到上下文

  var result;
  if (!arr) {
      result = context.fn();
  } else {
    // ?? arr 已经是一个数组，为什么还需要循环
    var args = [];
    for (var i = 0, len = arr.length; i < len; i++) {
        args.push('arr[' + i + ']');
    }
      result = eval('context.fn(' + args + ')')
  }
  delete context.fn
  return result;
}

```



## Bind 实现

```
Function.prototype.bind2 = function (context) {

    if (typeof this !== "function") {
      throw new Error("Function.prototype.bind - what is trying to be bound is not callable");
    }

    var self = this; // 考虑到绑定函数可能是有返回值的
    // 获取参数
    var args = Array.prototype.slice.call(arguments, 1);

    var fNOP = function () {};

    // 在 bind 的时候，只传一部分参数，在执行返回的函数的时候，再传另外的参数 
    var fBound = function () {
        // 这个时候的arguments是指bind返回的函数传入的参数
        var bindArgs = Array.prototype.slice.call(arguments);
        return self.apply(this instanceof fNOP ? this : context, args.concat(bindArgs));
    }

    // 一个绑定函数也能使用new操作符创建对象：这种行为就像把原函数当成构造器。
    // 提供的 this 值被忽略，同时调用时的参数被提供给模拟函数。
    fNOP.prototype = this.prototype;
    fBound.prototype = new fNOP();
    return fBound;

}
```

