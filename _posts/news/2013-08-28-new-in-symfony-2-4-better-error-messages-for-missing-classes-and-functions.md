---
layout: post
title: Symfony 2.4 新改进： 找不到类或者方法的错误信息
meta_keywords: Symfony, Symfony 2.4, 错误
meta_description: Symfony 2.4 将改善类或方法无法找到的错误信息
category: news
active_nav: news
---

虽然改进debug体验很有可能变成Symfony社区的月经话题，但的确每一个
Symfony的新版本都会让debug变得更加的容易。 而这一次的改进是关于
找不到类和方法的。

每当PHP因找不到某个类而怒抛错误的时候，你就必须乖乖去找问题所在。
原因有可能是拼写错误，或者忘了use命名空间，或者忘了安装某个依赖。

在Symfony 2.4，而且仅在开发环境下，我们提供了比PHP自带的错误信息
牛逼得多的错误信息。比如说，当你使用Request类但是忘了use它的命名
空间的时候，你就会看到以下信息：

> Attempted to load class 'Request' from the global namespace in 
> foo.php line 12. Did you forget a use statement for this class?
> Perhaps you need to add 
> 'use Symfony\Component\HttpFoundation\Request' at the top of 
> this file?
> （foo.php第12行代码尝试从全域命名空间里加载'Request'。您是不是忘了
> 使用use语句呢亲？或许你应该在文件头部添加
> 'use Symfony\Component\HttpFoundation\Request'
> 哦亲）

想要知道更多相关错误信息，请查看PR 
[#8553](https://github.com/symfony/symfony/pull/8553)
