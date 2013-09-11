---
layout: post
title: Symfony 2.4 新改进：限制进程空闲时间
meta_keywords: Symfony, Symfony 2.4, 进程
meta_description: Symfony 2.4 添加了对空闲进程进行限制的功能
category: news
active_nav: news
---

从Symfony 2.3起，Process组件的稳定性得到了极大的增强，这里要感谢
[Romain Neutron](https://connect.sensiolabs.com/api/alternates/b5f6c549-93c6-4118-a549-cf97f9effd54)同学的辛勤劳动。不过今天，我想介绍一个对
于跑长时间允许的进程特别有帮助的新功能，指定空闲超时时间。

目前，你可以通过setTimeout()方法指定一个进程的运行超时时间，参数
是进程能够允许的最长时间（秒）

    $process->setTimout(2 * 3600);

而在Symfony 2.4，你还能通过setIdleTimeout方法来限制空闲时长，参数
是进程在终端没有输出任何信息的持续时间（秒）

    $process->setIdleTimeout(10 * 60);

当超时的时候，Process组件会抛出一个
`Symfony\Component\Process\Exception\ProcessTimedOutException`异常，
你能通过`isGeneralTimemout()`或者`isIdleTimeout()`方法来判断超时的
类型。
