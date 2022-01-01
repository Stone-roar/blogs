## 一、this的默认绑定
### 1.web全局环境下的this指向window
```typescript
console.log(this); // window
```
### 2.函数独立调用
非严格模式下，函数内部的this指向window
严格模式下，为undefined
```typescript
function fn() {
    console.log(this);
}
fn(); // window
window.fn();
```
```typescript
'use strict'
function fn() {
    console.log(this);
}
fn(); // undefined
```
### 3.被嵌套的函数独立调用时，this默认指向window
```typescript
var obj = {
    a: 2,
    foo: function() {
        function test() {
            console.log(this); // window
        }
        test();
    }
}
obj.foo();
```
### 4.IIFE自执行函数
```typescript
(function() {
    console.log(this); // window
})()
```
```typescript
var obj2 = {
    foo: function() {
        (function () {
            console.log(this); // window
        })()
    }
}
obj2.foo()
```
### 5.闭包中this默认指向window
```typescript
var obj3 = {
    a: 2,
    foo: function() {
        console.log(this); // obj3
        var c = this.a; // 2
        return function test() {
            console.log(this); // window
            return c;
        }
    }
}
var fn = obj3.foo();
console.log(fn()); // 2
```
## 二、隐式绑定
### 1.当函数当做方法使用时，this指向直接对象
```typescript
function foo() {
    console.log(this); // obj4
}
var obj4 = {
    foo: foo
}
obj4.foo(); 
```
```typescript
function foo() {
    console.log(this); // obj5
}
var obj4 = {
    foo: foo,
    obj5: {
        a:1,
        foo: foo
    }
}
obj4.obj5.foo(); 
```
```typescript
function foo1() {
    console.log(this); // obj6
}
var obj6 = {
    a: 2,
    foo: foo1
}
var bar = obj6.foo(); // 在这就已经执行了方法
 ```

## 三、隐式丢失
### 1.被隐式绑定的函数丢失了绑定对象，从而默认绑定到window

```typescript
function foo1() {
    console.log(this); // window
}
var obj6 = {
    a: 2,
    foo: foo1
}
var bar = obj6.foo; // 在这并未执行方法
bar(); // 在这执行了方法
```
### 2.参数传递
```typescript
function foo3(){
    console.log(this);
}
function bar1(fn) {
    // 默认赋值 fn = obj7.foo
    fn(); // window
}
var obj7 = {
    a: 1,
    foo: foo3
}
bar1(obj7.foo);
```

### 3.setTimeout() 和 setInterval() 第一个参数的回调函数中的this 默认指向window
```typescript
setTimeout(function() {
    console.log(this); // window 
}, 0)
```

## 四、显示绑定
### 1、call和apply
```typescript
var obj = {
    a:1
}
function foo() {
    console.log(this);
}
foo.call(obj); //obj
foo.apply(obj); //obj
```
### 2、bind
```typescript
var obj = {
    a:1
}
function foo() {
    console.log(this); // obj
}
var fn = foo.bind(obj);
fn();
```

```typescript
var obj = {
    a:1
}
function foo() {
    console.log(this);
var fn = function() {
    foo.call(obj);
};
fn(); // obj
setTimeout(fn, 0); // obj
fn.call(window); // obj
```

### 3.数组的forEach(fn,对象)
```typescript
function fn(el) {
    console.log(el);
    console.log(this); // window
}
var arr = [1,2,3];
arr.forEach(fn);
```
```typescript
function fn(el) {
    console.log(el);
    console.log(this); // obj
}
var obj = {
    a:2
}
arr.forEach(fn,obj);
```
## 五、new绑定
### 1.new关键字来执行函数，相当于构造函数来实例化对象，则this指向当前实例化的对象
```typescript
function Fn() {
    console.log(this); // Fn{}
}
var fn = new Fn();
```
## 六、优先级
new绑定 > 显示绑定 > 隐式绑定 > 默认绑定 

```typescript
function fn1(b) {
    this.a = b;
    console.log(this); 
}
var obj = {c:2};
var bar = fn1.bind(obj);
bar(4); // obj
 
var baz = new bar(3); // fn1 {}
console.log(baz.a); // 3，因为new的优先级比bind更高
```

## 七、箭头函数
### 1.箭头函数中的this指向外层函数（非箭头函数）的作用域中的this指向。
所有绑定规则不适应箭头函数。

```typescript
function foo () {
    console.log(this); // obj
    var test = () => {
        console.log(this); // obj
    }
    test();
}
var obj = {
    a: 1,
    foo: foo
}
obj.foo();
```

### 2.默认绑定规则（独立调用对箭头函数）无效
```typescript
function foo () {
    console.log(this); // obj
    // 箭头函数
    var test = () => {
        console.log(this); // obj
    }
    return test;
}
var obj = {
    a:1,
    foo: foo
}
obj.foo()();
```

```typescript
function foo () {
    console.log(this); // obj
    // 普通函数
    var test = function(){
        console.log(this); // window
    }
    return test;
}
var obj = {
    a:1,
    foo: foo
}
obj.foo()();
```

## 3.显示绑定无效

```typescript
function foo () {
    console.log(this); // window
    var test = () => {
        console.log(this); // window
    }
    return test;
}
var obj2 = {
    a:2
}
var bar = foo().call(obj2)
```

## 4.隐式绑定无效

```typescript
var foo = () => {
    console.log(this); // window
}
var obj4 = {
    foo: foo
}
obj4.foo(); 
```

## 5.箭头函数不允许作为构造函数
