#### js 数据结构之BigInt
---
> js 是 动态弱类型语言

- 静态类型在编译时期时，就能可靠地发现类型错误。因此通常能增进最终程序的可靠性。
- 动态类型使元编程更为强大，且更易于使用。

弱类型意指一个语言可以隐式的转换类型（或直接转型）, 如下会将2转为字符串类型   
```js
let a = '1'
let b = 2
let c = a + b
```
> 所以有一个明显的误区，python实际上是动态强类型语言，因为python的不同类型进行运算符计算时，会出现TypeError错误

##### bigint类型
- 在 JavaScript 中，n是 BigInt 类型的后缀。当你看到数字后面跟着n，如1n和2n，这表示它们是 BigInt 类型的数值。

```js
const x = BigInt(Number.MAX_SAFE_INTEGER)
console.log(x + 1n === x + 2n)  // false

// 因为是js最大整数，所以+1后溢出，导致结果不等
// 所以用bigint是最安全的
console.log(Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2)
console.log(Number.MAX_SAFE_INTEGER + 1, Number.MAX_SAFE_INTEGER, Number.MAX_SAFE_INTEGER + 2)
```

