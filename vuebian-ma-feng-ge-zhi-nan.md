# Vue风格指南命名规范整理

## A组：必要的

组件名应为多个单词，避免与HTML相冲突

data必须是一个带返回值的函数

prop定义应该尽量详细，包括类型等

v-for必须配合key使用

v-for和v-if永远不要在一个元素上

为组件样式设置作用域

（1）当 style 标签有 scoped 属性时，它的 CSS 只作用于当前组件中的元素。无scoped为全局样式。

[https://vue-loader-v14.vuejs.org/zh-cn/features/scoped-css.html](https://vue-loader-v14.vuejs.org/zh-cn/features/scoped-css.html)

（2）CSS Module：当 style标签有 module，打开 CSS Modules 模式，生成的 CSS 对象将为组件注入一个名叫 $ style 的计算属性，你可以在你的模块中使用动态 class 绑定：class="$ style.red"，还可以设置 module 属性来为它们定义注入后计算属性的名称，module=‘a’，$ a.red

[https://vue-loader-v14.vuejs.org/zh-cn/features/css-modules.html](https://vue-loader-v14.vuejs.org/zh-cn/features/css-modules.html)

自定义的私有属性使用 $\_ 前缀。并附带一个命名空间

## B组：强烈推荐



尽量把每个组件拆分成组件文件

单文件组件的文件名：所有单词全部大写/全部小写横线连接

基础组件：应用特定样式和约定的基础组件 \(也就是展示类的、无逻辑的或无状态的组件\) 应该全部以一个特定的前缀开头，比如 Base、App 或 V。例如：BaseButton，AppTable

只应该拥有单个活跃实例的组件应该以 The 前缀命名，以示其唯一性。这类组件在每个页面只用一次，不接受任何prop，为应用定制。TheSidebar.vue

紧密耦合的组件名，和父组件紧密耦合的子组件应该以父组件名作为前缀命名。只在父组件的场景下有意义。例如：TodoList.vue；\|- TodoListItem.vue；\|- TodoListItemButton.vue

组件名应该以高级别的 \(通常是一般化描述的\) 单词开头，以描述性的修饰词结尾。SearchButtonClear

JS中的组件名：PascalCase命名法，所有单词首字母全部大写，DOM模板HTML中采用kebab-case命名

组件名应该倾向于完整单词而不是缩写。

在声明 prop 的时候，其命名应该始终使用 camelCase，而在模板和 JSX 中应该始终使用 kebab-case。

多个特性的元素应该分多行撰写，每个特性一行。

组件模板应该只包含简单的表达式，复杂的表达式则应该重构为计算属性或方法。复杂表达式可以重构到计算属性computed:{ XXXX : function \(\) {} }，复杂的计算属性可以分割为简单的计算属性。多个XXX：function（）{}

指令缩写：用 : 表示 v-bind: 和用 @ 表示 v-on:，要么都用要么都不用



