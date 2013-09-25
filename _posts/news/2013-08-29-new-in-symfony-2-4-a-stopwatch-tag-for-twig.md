---
layout: post
title: Symfony 2.4新功能：Twig的计时器标签
meta_keywords: Symfony 2, Symfony 2.4, twig
category: news
nav: news
---

翻译自Symfony官方博客。[阅读原文](http://symfony.com/blog/new-in-symfony-2-4-a-stopwatch-tag-for-twig)

想了解渲染模板时，各部分分别用了多少时间？没问题，Symfony 2.4新增了twig的“计时器”标签，你可以用它在模板的任何位置记录渲染耗时，然后在分析器（Profiler）的时间轴（Timeline）里查看。

    {% raw %}
    {% stopwatch "foo" %}
        ... 需要计时的部分
    {% endstopwatch %}
    {% endraw %}

如果你在模板里重复使用计时器名称，相应的渲染耗时会合并显示。

此标签由Twig Bridge提供，你也可以在基于Silex的应用里使用。

相关PR：[#8719](https://github.com/symfony/symfony/pull/8719)
