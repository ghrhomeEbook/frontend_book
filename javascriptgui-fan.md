# Vue项目开发与规范--es6语法规范篇

#### 平台项目主要采用Vue相关技术栈开发，在js规范上推荐使用ES6相关语法及最佳实践，同时推荐仔细阅读Vue编码风格指南，以期作为编码的风格参考。

ES6（ECMAScript2015）实际上是一种新的 JavaScript 规范，包含了一些很棒的新特性，可以更加方便地实现很多复杂的操作。

推荐代码中优先使用以下新特性：

* Default Parameters in ES6（默认参数）
* Template Literals in ES6（模板文本）
* Multi-line Strings in ES6（多行字符串）
* Destructuring Assignment in ES6（解构赋值）
* Enhanced Object Literals in ES6（增强的对象文本）
* Arrow Functions in ES6（箭头函数）
* Promises in ES6
* Block-Scoped Constructs Let and Const（块作用域构造 Let and Const）
* Classes in ES6（类）
* Modules in ES6（模块）

## 代码复杂度判断（计算决策点） {#代码复杂度判断（计算决策点）}

针对任意的一段代码，局外人无法轻易从业务上分析其风险性，但是通过静态检测和代码复杂度判断可以给出一些参考。关于代码复杂度衡量，有助于我们判断风险高的代码，然后针对性处理，重构, 提高代码的可维护性。

基本概念：

1. 圈复杂度：这就是大家常规理解的圈复杂度啦，它是通过程序流中的不同代码路径数计算得来。数值越高，流程越复杂，风险也越高
2. 继承深度：从顶层基类到当前类的继承深度
3. 类耦合：通过参数、局部变量、返回类型、方法调用、泛型或模板实例化、基类、接口实现、在外部类型上定义的字段以及特性修饰来衡量与一个类的耦合程度
4. 代码行数：代码中的大概行数。

前端代码可以参考以下简单规则来计算：

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

##  {#css-命名规范}

**Hack \#1: Swap variables 交换变量**

使用 Array Destructuring 交换值

```
let a = 'world', b = 'hello'
[a, b] = [b, a]
console.log(a) // -> hello
console.log(b) // -> world
// Yes, it's magic

```

**Hack \#2 : Async/Await with Destructuring**

下面这段代码可以同时发起两个异步请求，把请求结果分别附到 user 和 account 中

```
const [user, account] = await Promise.all([
  fetch('/user'),
  fetch('/account')
])
```

**Hack \#3 :  Debugging**

```
const a = 5, b = 6, c = 7
console.log({ a, b, c })
// outputs this nice object:
// {
//    a: 5,
//    b: 6,
//    c: 7
// }
```

**Hack \#4 : One liners**

更紧凑的数组操作语法

```
// Find max value
const max = (arr) => Math.max(...arr);
max([123, 321, 32]) // outputs: 321
// Sum array
const sum = (arr) => arr.reduce((a, b) => (a + b), 0)
sum([1, 2, 3, 4]) // output: 10

```

**Hack \#5 :  Array concatenation**

展开运算符可以用来代替 concat

```
const one = ['a', 'b', 'c']
const two = ['d', 'e', 'f']
const three = ['g', 'h', 'i']
// Old way #1
const result = one.concat(two, three)
// Old way #2
const result = [].concat(one, two, three)
// New
const result = [...one, ...two, ...three]
```

**Hack \#6 : Cloning**

```
const obj = { ...oldObj }
const arr = [ ...oldArr ]
```

**Hack \#7 : Named parameters 参数命名**

```
const getStuffNotBad = (id, force, verbose) => {
  ...do stuff
}
const getStuffAwesome = ({ id, name, force, verbose }) => {
  ...do stuff
}
// Somewhere else in the codebase... WTF is true, true?
getStuffNotBad(150, true, true)
// Somewhere else in the codebase... I ❤ JS!!!
getStuffAwesome({ id: 150, force: true, verbose: true })
```

  


