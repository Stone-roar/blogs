# this的指向
this的指向取决于函数的父作用域环境。
**个人理解**：this指向其调用者的所属对象，即其父对象。



### 例1.1

```typescript
const text = "window";
const obj = {
    text:"对象",
    func:function () {
        const text = "函数";
        console.log(this.text); //"对象"
        console.log(this); //obj
    }
};
obj.func();
```
### 例1.2

```typescript
const text = "window";
const obj = {
    text:"对象",
        book:{
            text:"书中文字",
            func:function () {
                const text = "函数";
                console.log(this.text); //"书中文字"
                console.log(this); //book
            }
        }   
};
obj.book.func();
```
### 例1.3
- 函数func的所有者book没有text属性，故为`undefined`。

```typescript
const text = "window";
const obj = {
    text:"对象",
        book:{
            name:"《西游记》",
            func:function () {
                const text = "函数";
                console.log(this.text); //undefined
                console.log(this); //book
            }
        }   
};
obj.book.func();
```
### 例1.4
- 变量`temp`属于全局对象[global]，当函数被赋给变量`temp`后，由temp调用时，this指向全局对象[global]。

```typescript
const text = "window";
const obj = {
    text:"对象",
        book:{
            text:"书中文字",
            func:function () {
                const text = "函数";
                console.log(this.text); //undefined
                console.log(this); //Object [global]
            }
        }   
};
const temp = obj.book.func;
temp();
```
### 例1.5
- 被嵌套的函数独立调用时，this默认指向全局对象window。

```typescript
const text = "window";
const obj = {
    text:"对象",
    func:function () {
        const text = "函数";
		function test() {
        console.log(this.text); //undefined
        console.log(this); //Object [global]
		};
		test();
    }
};
obj.func();
```
### 例1.6
- IIFE（立即调用函数表达式）自执行函数,this指向全局对象。
```typescript
(function () {
	console.log(this); //Object [global]
})();
```

```typescript
const text = "window";
const obj = {
    text:"对象",
    func:function () {
        const text = "函数";
		(function () {
        console.log(this.text); //undefined
        console.log(this); //Object [global]
		})();
    }
};
obj.func();
```


### 例1.6

```typescript
function func(){
    this.text = "函数";
}
const temp = new func();
console.log(temp.text); //函数
```

### 例1.7
```typescript
function func(){
    this.text = "函数";
}
const temp = new func();
console.log(temp.text); //函数
```
