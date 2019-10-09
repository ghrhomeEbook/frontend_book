## 构建项目目录

目录结构的统一化，可读性，分模块、组件构建，严禁构建杂乱无章，毫无可读性而言的项目目录。

* 了解开发当前项目所需的框架，工具、插件，功能，兼容性，分辨率等问题做好准备工作，做到心中有数。
* 目录结构整齐划一，方便日后的维护和其他同事的阅读。

**PC目录说明：**

-- 环境配置文件，.gitignore,vue.config.js以及package.json放到根目录下。

-- 静态入口页面放在public目录里，注意public目录里的静态资源管理也需要参考文件/资源命名规范。

-- 编译后文件放在dist目录下。

--dist,  node\_modules在.gitignore中配置目录不提交git.

-- src是源码文件夹

-- 所有的其余页面都放到components组件目录下，components目录下的页面全部归类放置，不要直接扔进去完事。  
-- 所有的js插件放到JavaScript目录下，还有package.json文件中安装的依赖。  
-- 所有的图片放置到所属子组件的目录下，static目录下放置固定不动的图片，和默认css文件包。

# 理解项目结构

```
├─.editorconfig
├─.env.development
├─.env.mock
├─.env.production
├─.env.test
├─.gitignore
├─.rancher-pipeline.yml
├─babel.config.js
├─Dockerfile
├─package-lock.json
├─package.json
├─README.md
├─vue.config.js
├─web
|  ├─mail.html
|  ├─images
|  |   └ZVOS-logo.png
├─src
|  ├─App.vue
|  ├─componentRegister.js
|  ├─main.js
|  ├─main_config.js
|  ├─views
|  |   ├─404.vue
|  |   ├─About.vue
|  |   ├─authority.json
|  |   ├─base.vue
|  |   ├─Construction.vue
|  |   ├─Home.vue
|  |   ├─NoAuth.vue
|  |   ├─user-manage
|  |   ├─user-center
|  |   ├─system-manage
|  |   ├─service-management
|  |   ├─quick-start
|  |   ├─product
|  |   ├─portal
|  |   ├─layout-portal
|  |   ├─layout
|  |   ├─equip
|  |   ├─edge
|  |   ├─document
|  |   ├─dev-center
|  |   ├─data-parsing
|  |   ├─component
|  |   ├─auth
|  |   ├─app-studio
|  ├─utils
|  |   ├─services
|  |   |    ├─event_service.js
|  |   |    ├─http_service.js
|  |   |    ├─i18n_service.js
|  |   |    ├─process_data_service.js
|  |   |    ├─token_service.js
|  |   |    └ws_service.js
|  |   ├─plugins
|  |   |    ├─drag_drop_plugin.js
|  |   |    ├─event_bus_plugin.js
|  |   |    ├─http_plugin.js
|  |   |    ├─http_service_plugin.js
|  |   |    └loading_plugin.js
|  |   ├─mixins
|  |   |   ├─paginationMixin
|  |   |   |        ├─index.js
|  |   |   |        └pagination_api.js
|  |   ├─filters
|  |   |    ├─currency.js
|  |   |    ├─date-format.js
|  |   |    ├─index.js
|  |   |    └number.js
|  |   ├─directives
|  |   |     ├─elSelectLoadMore.js
|  |   |     ├─index.js
|  |   |     └scroll_directive.js
|  |   ├─api
|  |   |  ├─base.js
|  |   |  ├─index.js
|  |   |  ├─modules
|  |   |  |    ├─test_module
|  |   |  |    |      ├─text_module_api.js
|  |   |  |    |      ├─mock
|  |   |  |    |      |  └index.js
|  ├─store
|  |   ├─actions.js
|  |   ├─getters.js
|  |   ├─index.js
|  |   ├─mutation-types.js
|  |   ├─mutations.js
|  |   ├─state.js
|  |   ├─modules
|  |   |    ├─appDevCenter.js
|  |   |    ├─appStudio.js
|  |   |    ├─appStudioCenter.js
|  |   |    ├─authority.js
|  |   |    ├─index.js
|  |   |    ├─testPage.js
|  |   |    └userInfo.js
|  ├─static
|  |   ├─sass
|  |   ├─less

|  |   ├─images
|  |   |   ├─icons
|  |   |   ├─app-studio
|  |   ├─fonts
|  |   ├─css
|  ├─router
|  |   ├─index.js
|  |   ├─index_res.js
|  |   ├─routes.js
|  |   ├─module_routes
|  |   |       ├─index.js
|  |   |       ├─module_a.js
|  |   |       ├─module_app_studio.js
|  |   |       ├─module_component.js
|  |   |       ├─module_data_parsing.js
|  |   |       ├─module_device_connect.js
|  |   |       ├─module_dev_center.js
|  |   |       ├─module_document.js
|  |   |       ├─module_edge.js
|  |   |       ├─module_equip.js
|  |   |       ├─module_portal.js
|  |   |       ├─module_product.js
|  |   |       ├─module_quick_start.js
|  |   |       ├─module_service_management.js
|  |   |       ├─module_system_manage.js
|  |   |       ├─module_usercenter.js
|  |   |       └module_user_manage.js
|  ├─mock
|  ├─lang
|  |  ├─component-en.js
|  |  ├─component-zh.js
|  |  ├─en.js
|  |  ├─index.js
|  |  └zh.js
|  ├─components
|  ├─assets
├─public
|   ├─export.html
|   ├─favicon.ico
|   ├─index.html
|   ├─manifest.json
|   ├─sw.js
|   ├─static
|   |   ├─404.js
|   |   ├─404.vue
|   |   ├─images
|   ├─component
├─dist
```



