# css标准

### 命名规范

| 前缀 | 代码要求 | 样例 | 注意 |
| :--- | :--- | :--- | :--- |
| zv | 以功能模块名称为class命名 | zv-datepicker，zv-menu-select，zv-list | 为统一，避免驼峰命名 |
| zv | 以代码块为class命名以表示页面结构 | zv-page,zv-content,zv-block,zv-section,zv-panel,zv-table | 代码块体现页面层进关系。例如：zv-page&gt;zv-content&gt;zv-block&gt;zv-section |
| zv | ID命名规范 | id="zv-product-\*" | 页面ID在页面与zv-page同级，以标识页面为主要目的 |
|  |  | id="zv-list-\*" | 需要时可以绑定id值具体代码块,尽量在样式中单独定义到页面css中，copy代码时去掉 |
| zv | 基于最近的父 class 或基本（base） class 作为新 class 的前缀。 | class="zv-panel" class="zv-panel-title" | &lt;div class="zv-panel"&gt;&lt;h3 class="zv-panel-title"&gt;&lt;/h3&gt;&lt;/div&gt; |
| js | 使用 .js-\* class 或者 \#js-\* id 来标识行为（与样式相对） | class="js-swiper" class="js-collapse" | 不要将这些 class 或者 ID 包含到 CSS 文件中 |

### 注：目前Zvalley OS平台采用的是bootstrape命名规范，关注于结构和语义的实现。在实现组件定义时，也推荐实践BEM的命名规范来组织css代码。

（BEM规范由于元素装饰器包含在块装饰器里面B\_\_E\_M, 组织形式更适合于组件的定义）

### 页面层叠示例

### HTML属性顺序

> HTML 属性应当按照以下给出的顺序依次排列，确保代码的易读性。

class,  
id, name  
data-\*  
src, for, type, href, value  
title, alt  
role, aria-\*.

> class 用于标识高度可复用组件，因此应该排在首位。id 用于标识具体组件，应当谨慎使用（例如，页面内的书签），因此排在第二位。

### **class 命名**

> class 名称中只能出现小写字符和破折号（dashe）（不是下划线，也不是驼峰命名法）。
>
> 破折号应当用于相关 class 的命名（类似于命名空间）（例如，.btn 和 .btn-danger）。
>
> 避免过度任意的简写。.btn 代表 button，但是 .s 不能表达任何意思。  
> class 名称应当尽可能短，并且意义明确。  
> 使用有意义的名称。
>
> 使用有组织的或目的明确的名称，不要使用表现形式（presentational）的名称。
>
> 基于最近的父 class 或基本（base） class 作为新 class 的前缀。
>
> 使用 .js-\* class 来标识行为（与样式相对），并且不要将这些 class 包含到 CSS 文件中。  
> 在为 Sass 和 Less 变量命名时也可以参考上面列出的各项规范。



