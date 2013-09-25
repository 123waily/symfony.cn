---
layout: post
title: Symfony 2.4新改进：限制进程空闲时长
meta_keywords: Symfony 2, Symfony 2.4, 进程
category: news
nav: news
---

翻译自Symfony官方博客。[原文链接](http://symfony.com/blog/new-in-symfony-2-4-limit-a-process-run-with-an-idle-timeout)

从Symfony 2.3起，Process组件的稳定性得到了极大的增强，这里要感谢[Romain Neutron](https://connect.sensiolabs.com/api/alternates/b5f6c549-93c6-4118-a549-cf97f9effd54)同学的辛勤劳动。本文要介绍的是，对于管理运行时间较长的进程十分实用的功能：指定空闲超时时间。

你可以通过setTimeout()方法指定进程的运行超时时间，参数是允许的进程运行的最长时间（秒）：

    $process->setTimout(2 * 3600);

在Symfony 2.4里，你将能通过setIdleTimeout方法来限制空闲时长，参数是进程在终端没有输出任何信息的持续时间（秒）：

    $process->setIdleTimeout(10 * 60);

遇到超时的情况，Process组件会抛出一个`Symfony\Component\Process\Exception\ProcessTimedOutException`异常，你可以用`isGeneralTimemout()`或者`isIdleTimeout()`方法来判断超时的类型。
