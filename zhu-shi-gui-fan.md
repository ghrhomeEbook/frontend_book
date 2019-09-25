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

// Js推荐注释，注释符号与注释说明之间空一个空格，单行
// var sellEle = document.querySelector('.sell');

// Js推荐注释，注释符号一上一下覆盖整个要注释的区块，多行注释
/*
var sellEle = document.querySelector('.sell');
console.log(sellEle);
*/
```

**函数\(方法\)注释**

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



