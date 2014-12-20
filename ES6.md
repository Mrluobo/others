#ES6学习笔记
`node --harmony --use-strict app.js`   node中启用ES6
`let` 块级变量声明。ES6规定另外，ES6也规定，函数本身的作用域，在其所在的块级作用域之内。
```javascript
function f(){console.log("outside")}
(function(){
 {
  function f(){console.log("inside")}
 }
 f(); //结果为outside
})()
```
`const`声明常量，一旦声明不可改变。
字符串扩展
`codePointAt()`,类似于`charCodeAt()`
`contains()`返回布尔值，表示是否找到了参数字符串
`startsWith()`:返回布尔值，表示是否在源字符串的头部
`endWith()`返回布尔值，表示是否在末尾。
`repeat(n)`返回一个新字符串，表示将元字符串重复N次
数值扩展
`Number.isFinite()`判断参数是否为数值，类型必须为`number`
`isFinite()`判断参数是否能转换为数值，`'25'`此类格式也可。
`isNaN()`和`Number.isNaN()`同上。
`parseInt()`和`parseFloat()`移植到`Number`对象上，行为不变。
`Number.isInteger()`是否为整数。
`Number.isSafeInteger()`是否为安全整数`-2^53~2^53`
`Math`对象扩展
`Math.trunc()`去除小数的小数部分。
数组扩展
`Array.from()`将类数组对象和可遍历对象转换为数组。
`Array.of()`将一组值转换为数组。
数组实例的`find`和`findIndex()`参数为一个回调函数，`find()`返回第一个回调函数返回为`true`的元素，否则返回`undefined`，`findeIndex()`返回第一个符合条件的位置，否则返回-1，回调格式`function(value,index,arr){}`
数组实例的`fill()`用于初始化数组，使用给定值填充调用数组，如果已有参数则抹去原有。
数组实例的`entries()`,`keys()`,`values()`为遍历方法。返回一个遍历器供`for()`循环调用。
对象扩展
`Object.assign()`将源对象的所有可枚举属性复制到目标对象中，至少两个参数，第一个为目标对象，如果属性已存在则覆盖。