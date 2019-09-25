# Vue项目开发与规范--es6语法规范篇

## 简介

ECMAScript 6 简称 ES6，是 JavaScript 语言的下一代标准，已经在2015年6月正式发布了。它的目标是使得 JavaScript 语言可以用来编写复杂的大型应用程序，成为企业级开发语言。

ECMAScript 和 JavaScript 的关系：前者是后者的语法规格，后者是前者的一种实现.

* let const

* 解构赋值

* 正则的扩展

* 字符串的扩展

* 数值的扩展
* 数组的扩展
* 函数的扩展
* 对象的扩展
* Symbol
* set和map以及和数组对象的对比
* Proxy和Reflect
* Class
* Promise
* Iterator
* genertaor函数
* Decorator

## 代码复杂度判断（计算决策点） {#代码复杂度判断（计算决策点）}

* 从 1 开始，一直往下通过函数
* 一旦遇到 if while for else 或者带有循环的高阶函数，比如 forEach map 等就加 1
* 给 case 语句中的每一种情况都加 1

```
function fun(arr, n) {
  let len = arr.length;
  for (let i = 0; i < len; i++) {
    if (arr[i] == n) {
      // todo...
    } else {
      // todo...
    }
  }
} //决策点为 3
```

| 数量区间 |  度量结果 |
| :--- | :--- |
| 0-5 | 这个函数可能还不错 |
| 6-10 | 得想办法简化这个函数了 |
| 10+ | 把这个函数的某一部分拆分成另一个函数并调用他 |

## [\#](https://122687220.github.io/web_doc/common/standard.html#css-%E5%91%BD%E5%90%8D%E8%A7%84%E8%8C%83)css 命名规范 {#css-命名规范}



