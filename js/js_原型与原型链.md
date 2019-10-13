js中万物皆对象，但是需要区分普通对象和函数对象，只有函数对象才有**prototype**属性，但所有对象都有__proto__属性

```javascript
function A(){
}
var B = new A;

B.__proto__== A.prototype; 
B.constructor == A;
A.prototype.constuctor = A;
```

A.prototype是A的原型对象，A是构造函数，B是A的实例，原型对象（A.prototype）是构造函数（A）的一个实例。