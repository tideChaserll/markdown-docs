#### js相等性判断
---

###### 在比较两个操作数时，双等号（==）将执行类型转换
> 并且会按照 IEEE 754 标准对 NaN、-0 和 +0 进行特殊处理（故 NaN != NaN，且 -0 == +0）；

> 这种类型转换可能会导致一些意外的结果，因为它并不总是严格按照预期的方式进行

对于NaN的处理：   
- NaN 是一个特殊的值，表示 “不是数字”。按照 IEEE 754 标准，**NaN 不等于任何值，包括它自己**

对 -0 和 +0 的特殊处理:   
- **按照 IEEE 754 标准，在进行相等性比较时，-0 和 +0 被认为是相等的。**   

**对于对于`==` 判断时，对于 NaN, +0, -0 的判断需要警惕**



###### 三等号（===）做的比较与双等号相同（包括对 NaN、-0 和 +0 的特殊处理）

> 但不进行类型转换；如果类型不同，则返回 false；

如下：

```js
console.log('1' === 1) // false
console.log('1' == 1) // true
```

**需要注意的是，是否需要转换类型后去对比**



###### Object.is() 
> 这使它和 === 在除了那些特殊数字值之外的情况具有相同的表现   

**既不进行类型转换，也不对 NaN、-0 和 +0 进行特殊处理**

如下:   

```js
console.log(Object.is(NaN, NaN)) // true
console.log(Object.is(-0, +0)) // false

console.log(Object.is('1' == 1)) // false
```

Object.is 符合人类的直觉, 需要 **类型相等**, **值看起来也相等**, 那就相等