# CSS编码规范

**CSS格式**

* **依字母顺序进行声明。**

* 都按字母顺序声明，很容易记住和维护。

* 忽略浏览器的特定前缀排序，但多浏览器特定的某个CSS属性前缀应相对保持排序（例如-moz前缀在-webkit前面）。

* **代码块内容缩进，它能够提高层次结构的清晰度。**

```
@media screen, projection {
   html {
       background: #fff;
       color: #444;
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

/* 不推荐: 表达不具体 */
.button-green {}
.clear {}

/* 推荐: 明确详细 */
#gallery {}
#login {}
.video {}

/* 推荐: 通用 */
.aux {}
.alt {}
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



