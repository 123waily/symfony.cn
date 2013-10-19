---
layout: post
title: Symfony 2.4.0 Beta 1 发布
meta_keywords: symfony, symfony 2.4
meta_description: Symfony新的版本即将发布
category: news
active_nav: news
---

[原文地址](http://symfony.com/blog/symfony-2-4-0-beta-1-released)

在我们第一个[长期支持版本](http://symfony.com/blog/symfony-2-3-0-the-first-lts-is-now-available)发布了以后，社区开始努力开发2.4版本。
本来我打算让2.4只做为过度版本，却发现在开发阶段出现许多巨大革新。如果你不是天天关注我们的进展，那么请一定要关注这里，
我会在接下来的几周把主要的功能分享给大家。

经过370+多个PR所带来的1000+代码提交量，2.4版本目前已经到了功能完结阶段，接下来的两个月我们将细调新功能，并且补上相应的文档。

此次的新版本我们将向后兼容到2.3版本，所以测试新版相当容易，你只需要修改一下composer.json里面的版本号
（如果是基于Standard Edition的项目，请先看看composer的[diff](https://github.com/symfony/symfony-standard/compare/v2.3.0...v2.4.0-BETA1#diff-10)，或者是看看[Standard Edition框架的变化](https://github.com/symfony/symfony-standard/compare/v2.3.0...v2.4.0-BETA1)）

如果你想单独测试，请使用composer创建一个新项目：

```shell
$ php composer.phar create-project symfony/framework-standard-edition somewhere/ 2.4.0-BETA1
````

或者下载基于Standard Edition的现成项目：
[TGZ](http://symfony.com/download?v=Symfony_Standard_Vendors_2.4.0-BETA1.tgz)，
[ZIP](http://symfony.com/download?v=Symfony_Standard_Vendors_2.4.0-BETA1.zip)

如果发现向后不兼容问题，请在[这里](https://github.com/symfony/symfony/issues)提出。
