# 类型

## typeof Undeclared
```javascript
var a
typeof a // undefined
typeof b // undefined
```
- 可能产生的问题：以为全局命名空间中不存在变量，新命名变量最终导致冲突。理论虽然提倡将所有东西都封装到模块/局部命名空间中，但不切实际。
## NaN != NaN
```javascript
// ES6中用Number.isNaN()
// 非ES6的polyfill方法
if(!Number.isNaN){
    Number.isNaN = function (n) {
        return n !== n //利用NaN的非自反性质
    }
}
```
## 引用赋值


