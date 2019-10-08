# 文件/资源命名

在 web 项目中，所有的文件名应该都遵循同一命名约定。以可读性而言，减号（-）是用来分隔文件名的不二之选。同时它也是常见的 URL 分隔符（i.e.`//example.com/blog/my-blog-entry`or`//s.example.com/images/big-black-background.jpg`），所以理所当然的，减号应该也是用来分隔资源名称的好选择。

请确保文件命名总是以字母开头而不是数字。而以特殊字符开头命名的文件，一般都有特殊的含义与用处（比如 compass\[1\]中的下划线就是用来标记跳过直接编译的文件用的）。

资源的字母名称必须全为小写，这是因为在某些对大小写字母敏感的操作系统中，当文件通过工具压缩混淆后，或者人为修改过后，大小写不同而导致引用文件不同的错误，很难被发现。

还有一些情况下，需要对文件增加前后缀或特定的扩展名（比如 .min.js, .min.css），抑或一串前缀（比如`3fa89b.main.min.css`）。这种情况下，建议使用点分隔符来区分这些在文件名中带有清晰意义的元数据。

### 项目命名

全部采用小写方式， 以下划线分隔。

例：my\_project\_name

### 目录命名

参照项目命名规则；

有复数结构时，要采用复数命名法。

例：scripts, styles, images, data\_models

### JS文件命名

参照项目命名规则。

例：account\_model.js

### CSS, SCSS文件命名

参照项目命名规则。

例：retina\_sprites.scss

### HTML文件命名

参照项目命名规则。

例：error\_report.html



**不推荐**

```
MyScript.js
myCamelCaseName.css
i_love_underscores.html
1001-scripts.js
my-file-min.css
```

**推荐**

```
my_script.js
my_camel_case_name.css
i_love_underscores.html
thousand_and_one_scripts.js
my_file.min.css
```

### 图片规范：

命名应用

```
header_btn.gif
header_btn2.gif
```

> 页面元素类图片均放入`img`文件夹,测试用图片放于`img/testimg`文件夹，psd源图放入`img/psdimg`文件夹。
>
> 图片格式仅限于`gif`、`png`、`jpg`等。
>
> * 用`png`图片做图片时, 要求图片格式为`png-8`格式
> * 背景图片请尽可能使用`sprite`技术, 减小`http`请求。

### 不要指定引入资源所带的具体协议。

当引入图片或其他媒体文件，还有样式和脚本时，URLs 所指向的具体路径，不要指定协议部分（`http:`,`https:`），除非这两者协议都不可用。

不指定协议使得 URL 从绝对的获取路径转变为相对的，在请求资源协议无法确定时非常好用，而且还能为文件大小节省几个字节。

**不推荐**

```
<script src="http://cdn.com/foundation.min.js"></script>
```

**推荐**

```
<script src="//cdn.com/foundation.min.js"></script>
```

**不推荐**

```
.example {
  background: url(http://static.example.com/images/bg.jpg);
}
```

推荐

```
.example {
  background: url(//static.example.com/images/bg.jpg);
}
```

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



