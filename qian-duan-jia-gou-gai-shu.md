# 前端架构概述

![](/assets/前端研发体系.png)前端研发体系，是围绕上图五个方面构建的。

上面两个是跟后端和运维发布相关的，一个痛点集中在API的规范上，另外一个需要在前端构建工具中，考虑比如版本管理，集成发布。

下方的三个构建，研发工具， 技术栈是研发体系的基础。也就是前端定义中的框架部分。

前端架构从以下四个层面出发设计：

系统层面，即前端与整个系统的关系，如与后台服务如何通讯，与第三方系统如何集成

应用层面，即应用外部的整体架构，如多个应用之间如何共享组件、如何通信等

模块层面，即应用内部的模块架构，如代码的模块化、数据和状态的管理等

代码层面，即从代码实施及规范上来保障架构实施

![](/assets/前端工程.png)

系统层面，应用各层面，模块层面再ZValley OS框架指南中详细说明，

本份前端规范更多的是从代码层面对前端开发形成一个风格指南。保证团队开发成员的沟通不失真， 代码可维护， 可交付。

![](/assets/前端架构2.png)

前端架构如上图

* 使用构建工具箱完成项目的创建开发和发布流程

* 中间层封装减少开发复杂度

* 模块松耦合

* 统一的Restful API接口调用规范


