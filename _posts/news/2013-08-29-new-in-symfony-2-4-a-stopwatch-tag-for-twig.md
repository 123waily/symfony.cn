---
layout: post
title: Symfony 2.4 新功能：Twig的秒表标签
meta_keywords: Symfony, Symfony 2.4, twig
meta_description: Symfony 2.4 将发布Twig秒表标签的新功能，用于查看性能
category: news
nav: news
---

PR [#8719](https://github.com/symfony/symfony/pull/8719)

想在渲染模板某个部分的时候察看渲染用时？没有问题，Symfony 2.4将支持twig的
“秒表”标签，您可以用它在模板的任何位置记录渲染时间，此时间将会记录在分析器
里，并且会现实在“timeline”一栏里（译者注：分析器在dev模式里的debug栏里，秒
表的图标）

    {% raw %}
    {% stopwatch "foo" %}
        ... some things that gets timed
    {% endstopwatch %}
    {% endraw %}

您可以多次使用同一个名字，这样可以让同一个名字的时间放在一条时间轴里显示。

此标签由Twig Bridge提供，您也可以将其用在Silex写的应用程序里。
