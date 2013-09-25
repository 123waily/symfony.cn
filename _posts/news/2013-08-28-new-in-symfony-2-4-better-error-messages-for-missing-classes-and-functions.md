---
layout: post
title: Symfony 2.4新改进：优化了找不到类或方法时的提示信息
meta_keywords: Symfony 2, Symfony 2.4, 错误
meta_description: Symfony 2.4 新改进：优化了找不到类或方法时的提示信息
category: news
nav: news
---

翻译自Symfony官方博客。[阅读原文](http://symfony.com/blog/new-in-symfony-2-4-better-error-messages-for-missing-classes-and-functions)

虽然改善代码调试（debug）体验很有可能成为Symfony社区的月经话题，但Symfony的每一个新版本确实都使代码调试（debug）更加轻松。而这一次得到改进的是找不到类或方法时的提示信息。

当PHP因为找不到某个类而怒抛错误的时候，你就必须乖乖去找问题出在哪里：可能是拼写错误，忘了use命名空间，或者忘了安装某个依赖包。

相比PHP自带的错误信息，Symfony 2.4（开发环境下）的报错更有指向性，提示了如何解决问题，比如，当你调用了Request类但是忘了use它的命名空间，你就会看到以下信息：

> Attempted to load class 'Request' from the global namespace in
> foo.php line 12. Did you forget a use statement for this class?
> Perhaps you need to add
> 'use Symfony\Component\HttpFoundation\Request' at the top of
> this file?
>
> （foo.php第12行代码尝试从全局命名空间里加载'Request'。您是不是忘了使用use语句呢亲？或许你应该在文件头部添加use Symfony\Component\HttpFoundation\Request'哦亲）

相关PR：[#8553](https://github.com/symfony/symfony/pull/8553)
