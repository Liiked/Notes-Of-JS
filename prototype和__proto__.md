## 定义
### prototype （显式原型 explicit prototype property）
- 每一个函数在创建之后都会拥有一个名为prototype的属性，这个属性指向函数的原型对象。
```javascript
function foo () {}
foo()
console.dir(foo)

// {
//     arguments: null,
//     caller: null,
//     length: 0,
//     name: "foo",
//     prototype: {
//         constructor: ƒ, // foo
//         __proto__: Object
//     },
//     __proto__: ƒ () // native code 
// }

```
- 注意：通过Function.prototype.bind方法构造出来的函数是个例外，它没有prototype属性。
### \_\_proto__ （隐式原型 implicit prototype link）
- JavaScript中任意对象都有一个内置属性[[prototype]]，在ES5之前没有标准的方法访问这个内置属性，但是大多数浏览器都支持通过__proto__来访问。ES5中有了对于这个内置属性标准的Get方法Object.getPrototypeOf()。
```javascript
var a = {}
console.dir(a)
// {
//     __proto__: Object
// }
```
- 注意：Object.prototype 这个对象是个例外，它的__proto__值为null。
## 关系
- \__proto__指向**创建**这个对象的函数(constructor)的prototype
## 作用
### prototype
- 用来实现基于原型的继承与属性的共享
### __proto__
- 构成原型链，同样用于实现基于原型的继承。