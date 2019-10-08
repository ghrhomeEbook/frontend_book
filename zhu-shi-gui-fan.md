## 注释

* **编码时一定注意写好注释，页面结构和样式的动态变化和添加，打好注释，便于后台同事套页面时候的阅读。**

* **尤其Js，做到主要代码、方法、参数的行行注释说明，便于其他同事了解你做此功能的思路，避免代码的冗余，造成性能问题，尽量做到高内聚低耦合。**

* **代码示例**

```
<!-- HTML推荐注释，左右各空一个空格，注释说明，单行 -->
<!--<div class="sell"></div>-->

<!-- HTML推荐注释，注释符号一上一下覆盖整个要注释的区块，多行注释 -->
<!--
<div class="sell">
    <p>多行注释</p>
    <p>多行注释</p>
    <p>多行注释</p>
    <p>多行注释</p>
</div>
-->

/* CSS推荐注释，左右各空一个空格，区块注释说明 */
.sell {
    /*background: #000;*/
}

/* CSS推荐注释，注释符号一上一下覆盖整个要注释的区块，多行注释 */
/*
.sell p {
    background: #000;
    font-size: 12px;
}
*/
```

### JS单行注释

双斜线后，必须跟一个空格；

缩进与下一行代码保持一致；

可位于一个代码行的末尾，与代码间隔一个空格。

```
if (condition) {
    // if you made it here, then all security checks passed
    allowed();
}

let name = 'ZValleyOS'; // one space after code
```

### JS多行注释

最少三行, '\*'后跟一个空格，具体参照右边的写法；

建议在以下情况下使用：

* 难于理解的代码段
* 可能存在错误的代码段
* 浏览器特殊的HACK代码
* 业务逻辑强相关的代码

```
/**
 * one space after '*'
 */
var x = 1;
```

### JS文档注释

各类标签@param, @method等请参考[usejsdoc](http://usejsdoc.org/)和[JSDoc Guide](http://yuri4ever.github.io/jsdoc/)；

建议在以下情况下使用：

* 所有常量
* 所有函数
* 所有类

```
**
 * @func
 * @desc 一个带参数的函数
 * @param {string} a - 参数a
 * @param {number} b=1 - 参数b默认值为1
 * @param {string} c=1 - 参数c有两种支持的取值</br>1—表示x</br>2—表示xx
 * @param {object} d - 参数d为一个对象
 * @param {string} d.e - 参数d的e属性
 * @param {string} d.f - 参数d的f属性
 * @param {object[]} g - 参数g为一个对象数组
 * @param {string} g.h - 参数g数组中一项的h属性
 * @param {string} g.i - 参数g数组中一项的i属性
 * @param {string} [j] - 参数j是一个可选参数
 */
function foo(a, b, c, d, g, j) {
    ...
}
```

* **代码示例**

```
/** 
* 函数说明 
* @关键字 
*/

/**
 * 合并Grid的行
 * @param {Grid} grid 需要合并的Grid
 * @param {Array} cols 需要合并列的Index(序号)数组；从0开始计数，序号也包含。
 * @param {Boolean} isAllSome 是否2个tr的cols必须完成一样才能进行合并。true：完成一样；false(默认)：不完全一样
 * @return void
 * @author barry
 */
function mergeCells(grid, cols, isAllSome) {
    // Do Something
}
```



