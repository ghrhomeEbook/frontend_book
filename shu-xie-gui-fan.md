## 代码规范

#### **书写规范**：增强语义化，增强阅读性。

**1、只用小写字母**

* 所有的代码都用小写字母：适用于元素名，属性，属性值（除了文本和 CDATA ）， 选择器，特性，特性值（除了字符串）。

**2、增强语义**

* 根据HTML各个元素的用途而去使用它们。

* 使用元素 \(有时候错称其为“标签”\) 要知道为什么去使用它们和是否正确。 例如，用heading元素构造标题， p 元素构造段落, a 元素构造锚点等。

* 根据HTML各个元素的用途而去使用是很重要的，它涉及到文档的可访问性、重用和代码效率等问题。

* **禁止用行内元素包裹块级标签，最好不要在p标签内嵌套别的标签**

**3、关注点分离**

* **将表现和行为分开**

* 严格保持结构 （标记），表现 （样式），和行为 （脚本）分离, 并尽量让这三者之间的交互保持最低限度。

* 确保文档和模板只包含HTML结构， 把所有表现都放到样式表里，把所有行为都放到脚本里。

* 此外，尽量使脚本和样式表在文档与模板中有最小接触面积，即减少外链。

* 将表现和行为分开维护是很重要滴，因为更改HTML文档结构和模板会比更新样式表和脚本更花费成本。

**4、type属性**

* **在样式表和脚本的标签中忽略 type 属性**

* 在样式表（除非不用 CSS）和脚本（除非不用 JavaScript）的标签中 不写 type 属性。

* HTML5默认 type 为 text/css 和 text/javascript 类型，所以没必要指定。即便是老浏览器也是支持的。

#### 格式规范：禁止看到参差不齐的格式。

**1、HTML格式**

* **每个块元素、列表元素或表格元素都独占一行，每个子元素都相对于父元素进行缩进。**

* 独立元素的样式，将块元素、列表元素或表格元素都放在新行。

* 另外，需要缩进块元素、列表元素或表格元素的子元素。

**2、CSS格式**

* 声明顺序

  这是一个选择器内书写CSS属性顺序的大致轮廓。这是为了保证更好的可读性和可扫描重要。

  作为最佳实践，我们应该遵循以下顺序（应该按照下表的顺序）：

  1. 结构性属性：
     1. display
     2. position, left, top, right etc.
     3. overflow, float, clear etc.
     4. margin, padding
  2. 表现性属性：
     1. background, border etc.
     2. font, text

* 忽略浏览器的特定前缀排序，但多浏览器特定的某个CSS属性前缀应相对保持排序（例如-moz前缀在-webkit前面）。

* **代码块内容缩进，它能够提高层次结构的清晰度。**

```
@media screen, projection {
   html {
       background: #fff;
       color: #ccc;
   }
}
```

* **声明完结，所有声明都要用“;”结尾。**

```
/* 不推荐 */
 .test {
     display: block;
     height: 100px
 }
 /* 推荐 */
 .test {
     display: block;
     height: 100px;
}
```

**选择器和声明分行，每个选择器和声明都要独立新行。**

```
/* 不推荐 */
  a:focus, a:active {
      position: relative;
      top: 1px;
  }
  /* 推荐 */
  h1,
  h2,
  h3 {
     font-weight: normal;
     line-height: 1.2;
  }
```

**规则分行，每个规则独立一行，两个规则之间隔行**

```
html {
     background: #fff;
 }

 body {
     margin: auto;
     width: 50%;
 }
```

#### 

#### **命名规范：**严禁特简化命名。

**1、ID和class的命名**

* **为ID和class取通用且有意义的名字。**

* 应该从ID和class的名字上就能看出这元素是干嘛用的，而不是表象或模糊不清的命名。

* 应该优先虑以这元素具体目来进行命名，这样他就最容易理解，减少更新。

* 通用名称可以加在兄弟元素都不特殊或没有个别意义的元素上，可以起名类似“helpers”这样的泛。

* 使用功能性或通用的名字会减少不必要的文档或模板修改。

* **代码示例**

```
/* 不推荐: 无意义 不易理解 */
#yee-1901 {}

/* 推荐: 通用 */
#login {}
.video {}
```

**2、ID和class命名风格**

* 非必要的情况下，ID和class的名称应尽量简短。

* 简要传达ID或class是关于什么的。

* 通过这种方式，似的代码易懂且高效。

* **代码示例**

```
/* 不推荐 */
#navigation {}
.atr {}
/* 推荐 */
#nav {}
.author {}
```

**3、类型选择器**

* **避免使用CSS类型选择器。**

* 非必要的情况下不要使用元素标签名和ID或class进行组合。

* 出于性能上的考虑避免使用父辈节点做选择器 performance reasons.

* **代码示例**

```
/* 不推荐 */
ul#example {}
div.error {}
/* 推荐 */
#example {}
.error {}
```

**4、属性缩写**

* **写属性值的时候尽量使用缩写。**

* CSS很多属性都支持缩写shorthand （例如 font ） 尽量使用缩写，甚至只设置一个值。

* 使用缩写可以提高代码的效率和方便理解。

```
/* 不推荐 */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
/* 推荐 */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

**5、0和单位，省略0后面的单位，省略0开头小数点前面的0。**

```
.test {
    margin: 0;
    padding: 0;
    font-size: .8em;
}
```

**6、ID和class命名的定界符**

* **选择器前面加上特殊应用标识的前缀（可选）。**

* **大型项目中最好在ID或class名字前加上这种标识性前缀（命名空间），使用短破折号链接。**

* **使用命名空间可以防止命名冲突，方便维护，比如在搜索和替换操作上。**

* **ID和class名字有多单词组合的用短破折号“-”分开。**

* **代码示例**

```
/* 不推荐：“demo”和“image”中间没加“-” */
.demoimage {}

/* 不推荐：用下划线“_”是屌丝的风格 */
.error_status {}

/* 不推荐：用驼峰命名是屌丝的风格 */
.errorStatus {}

/* 推荐 */
#video-id {}
.ads-sample {}
```

#### **Js语法规范（重点）：**严格按照此中语言的语法要求进行编码。

**1、变量**

* **驼峰式命名，驼峰式命名法由小\(大\)写字母开始，后续每个单词首字母都大写。**

* 命名方法：小驼峰式命名法。

* 命名规范：前缀应当是名词。\(函数的名字前缀为动词，以此区分变量和函数\)。

* 命名建议：尽量在变量名字中体现所属类型，如:length、count等表示数字类型；而包含name、title表示为字符串类型。

```
// 好的命名方式
var maxCount = 10;
var tableTitle = 'LoginTable';

// 不好的命名方式
var setCount = 10;
var getTitle = 'LoginTable';
```

**2、函数**

* 命名方法：小驼峰式命名法。

* 命名规范：前缀应当为动词。

* 命名建议：可使用常见动词约定

```
// 是否可阅读
function canRead() {
    return true;
}

// 获取名称
function getName() {
    return this.name;
}
```

**3、常量**

* 命名方法：名称全部大写。

* 命名规范：使用大写字母和下划线来组合命名，下划线用以分割单词。

```
var MAX_COUNT = 10;
var URL = 'http://www.baidu.com';
```

**4、构造函数**

* 介绍：在JS中，构造函数也属于函数的一种，只不过采用new 运算符创建对象。

* 命名方法：大驼峰式命名法，首字母大写。

* 命名规范：前缀为名称。

```
function Student(name) {
    this.name = name;
}

var st = new Student('tom');
```

**5、类的成员**

* **类的成员包含：**

* 公共属性和方法：跟变量和函数的命名一样。

* 私有属性和方法：前缀为\_\(下划线\)，后面跟公共属性和方法一样的命名方式。

```
function Student(name) {
    var _name = name; // 私有成员

    // 公共方法
    this.getName = function () {
        return _name;
    }

    // 公共方式
    this.setName = function (value) {
        _name = value;
    }
}
var st = new Student('tom');
st.setName('jerry');
console.log(st.getName()); // => jerry：输出_name私有变量的值
```

## 三、注释

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



