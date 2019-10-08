# 理解页面结构

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



