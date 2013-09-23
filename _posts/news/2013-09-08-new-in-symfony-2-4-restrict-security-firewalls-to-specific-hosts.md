---
layout: post
title: Symfony 2.4 新改进：给指定的host配置防火墙
meta_keywords: Symfony, Symfony 2.4, 进程
meta_description: Symfony 2.4 添加了对指定host配置防火墙的功能
category: news
active_nav: news
---

从Symfony 2.2起，路由规则开始支持对指定host的配置。而Symfony 2.4则开始支持对指定host的防火墙配置。

在配置防火墙时，你可以利用正则来限制某些URL，比如 ^/admin/:

    admin:
        pattern: ^/admin
        http_basic: true

如果你想限制整个admin.example.com怎么办？这在Symfony 2.4中可以轻易做到：

    host:
        pattern: ^/
        host:    admin\.example\.com
        http_basic: true

简单强力！
