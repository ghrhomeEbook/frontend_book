## CSS and Sass \(SCSS\)编码规范

### ID and class naming

ID和class\(类\)名总是使用可以反应元素目的和用途的名称，或其他通用名称。代替表象和晦涩难懂的名称。

应该首选具体和反映元素目的的名称，因为这些是最可以理解的，而且发生变化的可能性最小。

通用名称只是多个元素的备用名，他们兄弟元素之间是一样的，没有特别意义。  
区分他们，使他们具有特殊意义，通常需要为“帮手”。

尽管class\(类\)名和ID 的语义化对于计算机解析来说没有什么实际的意义，  
语义化的名称 通常是正确的选择，因为它们所代表的信息含义，不包含表现的限制。

**不推荐**

```
.fw-800 {
  font-weight: 800;
}

.red {
  color: red;
}
```

**推荐**

```
.heavy {
  font-weight: 800;
}

.important {
  color: red;
}
```

### 合理的避免使用ID

一般情况下ID不应该被应用于样式。  
ID的样式不能被复用并且每个页面中你只能使用一次ID。  
使用ID唯一有效的是确定网页或整个站点中的位置。  
尽管如此，你应该始终考虑使用class，而不是id，除非只使用一次。

**不推荐**

```
#content .title {
  font-size: 2em;
}
```

**推荐**

```
.content .title {
  font-size: 2em;
}
```

另一个反对使用ID的观点是含有ID选择器权重很高。

一个只包含一个ID选择器权重高于包含1000个class\(类\)名的选择器，这使得它很奇怪。

```
// 这个选择器权重高于下面的选择器
#content .title {
  color: red;
}

// than this selector!
html body div.content.news-content .title.content-title.important {
  color: blue;
}
```

### CSS选择器中避免标签名

当构建选择器时应该使用清晰， 准确和有语义的class\(类\)名。不要使用标签选择器。 如果你只关心你的class\(类\)名  
，而不是你的代码元素，这样会更容易维护。

从分离的角度考虑,在表现层中不应该分配html标记/语义。  
它可能是一个有序列表需要被改成一个无序列表，或者一个div将被转换成article。  
如果你只使用具有实际意义的class\(类\)名，  
并且不使用元素选择器，那么你只需要改变你的html标记，而不用改动你的CSS。

**不推荐**

```
div.content > header.content-header > h2.title {
  font-size: 2em;
}
```

**推荐**

```
.content > .content-header > .title {
  font-size: 2em;
}
```

### 尽可能的精确

很多前端开发人员写选择器链的时候不使用 直接子选择器（注：直接子选择器和后代选择器的区别）。  
有时，这可能会导致疼痛的设计问题并且有时候可能会很耗性能。  
然而，在任何情况下，这是一个非常不好的做法。  
如果你不写很通用的，需要匹配到DOM末端的选择器， 你应该总是考虑直接子选择器。

考虑下面的DOM:

```
<article class="content news-content">
  <span class="title">News event</span>
  <div class="content-body">
    <div class="title content-title">
      Check this out
    </div>

    <p>This is a news article content</p>

    <div class="teaser">
      <div class="title">Buy this</div>
      <div class="teaser-content">Yey!</div>
    </div>
  </div>
</article>
```

下面的CSS将应用于有title类的全部三个元素。

然后，要解决content类下的title类 和 teaser类下的title类下不同的样式，这将需要更精确的选择器再次重写他们的样式。

**不推荐**

```
.content .title {
  font-size: 2rem;
}
```

**推荐**

```
.content > .title {
  font-size: 2rem;
}

.content > .content-body > .title {
  font-size: 1.5rem;
}

.content > .content-body > .teaser > .title {
  font-size: 1.2rem;
}
```

### 缩写属性

CSS提供了各种缩写属性（如 font 字体）应该尽可能使用，即使在只设置一个值的情况下。

使用缩写属性对于代码效率和可读性是有很有用的。

**不推荐**

```
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```

**推荐**

```
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

### 0 和 单位

省略“0”值后面的单位。不要在0值后面使用单位，除非有值。

**不推荐**

```
padding-bottom: 0px;
margin: 0em;
```

**推荐**

```
padding-bottom: 0;
margin: 0;
```

### 十六进制表示法

在可能的情况下，使用3个字符的十六进制表示法。  
颜色值允许这样表示，  
3个字符的十六进制表示法更简短。

始终使用小写的十六进制数字。

**不推荐**

```
color: #FF33AA;
```

**推荐**

```
color: #f3a;
```

### ID 和 Class（类） 名的分隔符

使用连字符（中划线）分隔ID和Class（类）名中的单词。为了增强课理解性，在选择器中不要使用除了连字符（中划线）以为的任何字符（包括没有）来连接单词和缩写。

另外，作为该标准，预设属性选择器能识别连字符（中划线）作为单词`[attribute|=value]`的分隔符，  
所以最好的坚持使用连字符作为分隔符。

**不推荐**

```
.demoimage {}
.error_status {}
```

**推荐**

```
#video-id {}
.ads-sample {}
```

### Hacks

避免用户代理检测以及CSS“hacks” – 首先尝试不同的方法。通过用户代理检测或特殊的CSS滤镜，变通的方法和 hacks 很容易解决样式差异。为了达到并保持一个有效的和可管理的代码库，这两种方法都应该被认为是最后的手段。换句话说，从长远来看，用户代理检测和hacks  
会伤害项目，作为项目往往应该采取阻力最小的途径。也就是说，轻易允许使用用户代理检测和hacks 以后将过于频繁。

---

### 声明顺序

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

**不推荐**

```
.box {
  font-family: 'Arial', sans-serif;
  border: 3px solid #ddd;
  left: 30%;
  position: absolute;
  text-transform: uppercase;
  background-color: #eee;
  right: 30%;
  isplay: block;
  font-size: 1.5rem;
  overflow: hidden;
  padding: 1em;
  margin: 1em;
}
```

**推荐**

```
.box {
  display: block;
  position: absolute;
  left: 30%;
  right: 30%;
  overflow: hidden;
  margin: 1em;
  padding: 1em;
  background-color: #eee;
  border: 3px solid #ddd;
  font-family: 'Arial', sans-serif;
  font-size: 1.5rem;
  text-transform: uppercase;
}
```

### 声明结束

为了保证一致性和可扩展性，每个声明应该用分号结束，每个声明换行。

**不推荐**

```
.test {
  display: block; height: 100px
}
```

**推荐**

```
.test {
  display: block;
  height: 100px;
}
```

### 属性名结束

属性名的冒号后使用一个空格。出于一致性的原因，  
属性和值（但属性和冒号之间没有空格）的之间始终使用一个空格。

**不推荐**

```
h3 {
  font-weight:bold;
}
```

**推荐**

```
h3 {
  font-weight: bold;
}
```

### 选择器和声明分离

每个选择器和属性声明总是使用新的一行。

**不推荐**

```
a:focus, a:active {
  position: relative; top: 1px;
}
```

**推荐**

```
h1,
h2,
h3 {
  font-weight: normal;
  line-height: 1.2;
}
```

### 规则分隔

规则之间始终有一个空行（双换行符）分隔。

**推荐**

```
html {
  background: #fff;
}

body {
  margin: auto;
  width: 50%;
}
```

### CSS引号

属性选择器或属性值用双引号（””），而不是单引号（”）括起来。  
URI值（url\(\)）不要使用引号。

**不推荐**

```
@import url('//cdn.com/foundation.css');

html {
  font-family: 'open sans', arial, sans-serif;
}

body:after {
  content: 'pause';
}
```

**推荐**

```
@import url(//cdn.com/foundation.css);

html {
  font-family: "open sans", arial, sans-serif;
}

body:after {
  content: "pause";
}
```

### 选择器嵌套 \(SCSS\)

在Sass中你可以嵌套选择器，这可以使代码变得更清洁和可读。嵌套所有的选择器，但尽量避免嵌套没有任何内容的选择器。  
如果你需要指定一些子元素的样式属性，而父元素将不什么样式属性，  
可以使用常规的CSS选择器链。  
这将防止您的脚本看起来过于复杂。

**不推荐**

```
// Not a good example by not making use of nesting at all
.content {
  display: block;
}

.content > .news-article > .title {
  font-size: 1.2em;
}
```

**不推荐**

```
// Using nesting is better but not in all cases
// Avoid nesting when there is no attributes and use selector chains instead
.content {
  display: block;

  > .news-article {
    > .title {
      font-size: 1.2em;
    }
  }
}
```

**推荐**

```
// This example takes the best approach while nesting but use selector chains where possible
.content {
  display: block;

  > .news-article > .title {
    font-size: 1.2em;
  }
}
```

### 嵌套中引入 空行 \(SCSS\)

嵌套选择器和CSS属性之间空一行。

**不推荐**

```
.content {
  display: block;
  > .news-article {
    background-color: #eee;
    > .title {
      font-size: 1.2em;
    }
    > .article-footnote {
      font-size: 0.8em;
    }
  }
}
```

**推荐**

```
.content {
  display: block;

  > .news-article {
    background-color: #eee;

    > .title {
      font-size: 1.2em;
    }

    > .article-footnote {
      font-size: 0.8em;
    }
  }
}
```

### 上下文媒体查询\(SCSS\)

在Sass中，当你嵌套你的选择器时也可以使用上下文媒体查询。  
在Sass中，你可以在任何给定的嵌套层次中使用媒体查询。  
由此生成的CSS将被转换，这样的媒体查询将包裹选择器的形式呈现。

这技术非常方便，  
有助于保持媒体查询属于的上下文。

第一种方法这可以让你先写你的手机样式，然后在任何你需要的地方  
用上下文媒体查询以提供桌面样式。

**不推荐**

```
// This mobile first example looks like plain CSS where the whole structure of SCSS is repeated
// on the bottom in a media query. This is error prone and makes maintenance harder as it's not so easy to relate
// the content in the media query to the content in the upper part (mobile style)

.content-page {
  font-size: 1.2rem;

  > .main {
    background-color: whitesmoke;

    > .latest-news {
      padding: 1rem;

      > .news-article {
        padding: 1rem;

        > .title {
          font-size: 2rem;
        }
      }
    }

    > .content {
      margin-top: 2rem;
      padding: 1rem;
    }
  }

  > .page-footer {
    margin-top: 2rem;
    font-size: 1rem;
  }
}

@media screen and (min-width: 641px) {
  .content-page {
    font-size: 1rem;

    > .main > .latest-news > .news-article > .title {
      font-size: 3rem;
    }

    > .page-footer {
      font-size: 0.8rem;
    }
  }
}
```

**推荐**

```
// This is the same example as above but here we use contextual media queries in order to put the different styles
// for different media into the right context.

.content-page {
  font-size: 1.2rem;

  @media screen and (min-width: 641px) {
    font-size: 1rem;
  }

  > .main {
    background-color: whitesmoke;

    > .latest-news {
      padding: 1rem;

      > .news-article {
        padding: 1rem;

        > .title {
          font-size: 2rem;

          @media screen and (min-width: 641px) {
            font-size: 3rem;
          }
        }
      }
    }

    > .content {
      margin-top: 2rem;
      padding: 1rem;
    }
  }

  > .page-footer {
    margin-top: 2rem;
    font-size: 1rem;

    @media screen and (min-width: 641px) {
      font-size: 0.8rem;
    }
  }
}
```

### 嵌套顺序和父级选择器\(SCSS\)

当使用Sass的嵌套功能的时候，  
重要的是有一个明确的嵌套顺序，  
以下内容是一个SCSS块应具有的顺序。

1. 当前选择器的样式属性
2. 父级选择器的伪类选择器 \(:first-letter, :hover, :active etc\)
3. 伪类元素 \(:before and :after\)
4. 父级选择器的声明样式 \(.selected, .active, .enlarged etc.\)
5. 用Sass的上下文媒体查询
6. 子选择器作为最后的部分

The following example should illustrate how this ordering will achieve a clear structure while making use of the Sass parent selector.

**Recommended**

```
.product-teaser {
  // 1. Style attributes
  display: inline-block;
  padding: 1rem;
  background-color: whitesmoke;
  color: grey;

  // 2. Pseudo selectors with parent selector
  &:hover {
    color: black;
  }

  // 3. Pseudo elements with parent selector
  &:before {
    content: "";
    display: block;
    border-top: 1px solid grey;
  }

  &:after {
    content: "";
    display: block;
    border-top: 1px solid grey;
  }

  // 4. State classes with parent selector
  &.active {
    background-color: pink;
    color: red;

    // 4.2. Pseuso selector in state class selector
    &:hover {
      color: darkred;
    }
  }

  // 5. Contextual media queries
  @media screen and (max-width: 640px) {
    display: block;
    font-size: 2em;
  }

  // 6. Sub selectors
  > .content > .title {
    font-size: 1.2em;

    // 6.5. Contextual media queries in sub selector
    @media screen and (max-width: 640px) {
      letter-spacing: 0.2em;
      text-transform: uppercase;
    }
  }
}
```



# css\_补充规范

```
/*这部分内容是给css导入时使用的原则，尽量用link
```

```
<!-- Use link elements -->
<link rel="stylesheet" href="core.css">

不要使用 @import
与 <link> 标签相比，@import 指令要慢很多，不光增加了额外的请求次数，还会导致不可预料的问题。替代办法有以下几种：

使用多个 <link> 元素
通过 Sass 或 Less 类似的 CSS 预处理器将多个 CSS 文件编译为一个文件
通过 Rails、Jekyll 或其他系统中提供过 CSS 文件合并功能
*/


/* Good CSS
对于属性值或颜色参数，省略小于 1 的小数前面的 0 （例如，.5 代替 0.5；-.5px 代替 -0.5px）。

所有声明语句都应当以分号结尾。最后一条声明语句后面的分号是可选的，但是，如果省略这个分号，你的代码可能更易出错。

不要在 rgb()、rgba()、hsl()、hsla() 或 rect() 值的内部的逗号后面插入空格。这样利于从多个属性值（既加逗号也加空格）中区分多个颜色值（只加逗号，不加空格）

避免为 0 值指定单位，例如，用 margin: 0; 代替 margin: 0px;
```

```
 .selector,
.selector-secondary,
.selector[type="text"] {
    padding: 15px;
    margin-bottom: 15px;
    background-color: rgba(0,0,0,.5);
    box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

> ```
> /*Positioning声明顺序相关的属性声明应当归为一组，并按照下面的顺序排列：
>
> Positioning
> Box model
> Typographic
> Visual
>
> 由于定位（positioning）可以从正常的文档流中移除元素，并且还能覆盖盒模型（box
> model）相关的样式，因此排在首位。盒模型排在第二位，因为它决定了组件的尺寸和位置。
>
> 其他属性只是影响组件的内部（inside）或者是不影响前两组属性，因此排在后面。
> */
> ```

```
.declaration-order {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 100;

    /* Box-model */
    display: block;
    float: right;
    width: 100px;
    height: 100px;

    /* Typography */
    font: normal 13px "Helvetica Neue", sans-serif;
    line-height: 1.5;
    color: #333;
    text-align: center;

    /* Visual */
    background-color: #f5f5f5;
    border: 1px solid #e5e5e5;
    border-radius: 3px;

    /* Misc */
    opacity: 1;
}
```











