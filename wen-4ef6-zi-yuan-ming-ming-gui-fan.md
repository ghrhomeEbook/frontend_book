# VUE工程目录/文件名命名约定

* 公共组件、指令、过滤器（多于三个文件以上的引用）分别放在src目录下的components、directives、filters
* 以使用场景命名Vue的页面文件
* 当页面文件具有私有组件、指令、过滤器时，则建立一个与页面同名的目录，页面文件更名为index.vue，将页面与相关的依赖文件放在一起
* 目录由全小写的名词、动名词或分词命名，由两个以上的词组成，以-分隔
* Vue文件统一以大驼峰命名法命名，仅各模块的入口文件index.vue采用小写
* 测试文件一律以测试目标文件名.spec.js命名
* 资源文件一律以小写字符命名，由两个以上词组成以-分隔

举例

* components

  ```
          Silder.vue

          ImageInput.vue
  ```

* login

  ```
         index.vue

         Form.vue

         Login.vue
  ```



