---
layout: post
title: Symfony 2.4的新特性：控制台的改进
meta_keywords: symfony, symfony 2.4, 控制台
meta_description: 
category: news
active_nav: news
---

[原文链接](http://symfony.com/blog/new-in-symfony-2-4-console-improvements)

为庆祝新版本的到来，让我们先看看对[在控制台里显示日至](http://symfony.com/blog/new-in-symfony-2-4-show-logs-in-console)功能做了什么新改进。

更好看的常见错误信息
--------------------

当创建新的Command对象时，如果你想重写构造函数，你_必须_记得调用`parent::__construct()`。
要是你不小心忘记了，你会得到一个特别奇怪的错误信息。不过因为这都属于常见错误，2.4版本会非常友好的提醒你注意调用父类的构造函数。

紧凑风格的TableHelper布局方式
-----------------------------

Symfony 2.3的TableHelper提供了不错的将数据显示在表格里的方式。
它提供了两套风格：默认`LAYOUT_DEFAULT`和无边`LAYOUT_BORDERLESS`。
2.4里添加了第三种：紧凑`LAYOUT_COMPACT`

当显示很多数据的时候，或者你不想要边框的时候就可以使用它。

```shell
# The new compact layout

ISBN          Title                    Author
99921-58-10-7 Divine Comedy            Dante Alighieri
9971-5-0210-0 A Tale of Two Cities     Charles Dickens
960-425-059-0 The Lord of the Rings    J. R. R. Tolkien
80-902734-1-6 And Then There Were None Agatha Christie

# The default layout

+---------------+--------------------------+------------------+
| ISBN          | Title                    | Author           |
+---------------+--------------------------+------------------+
| 99921-58-10-7 | Divine Comedy            | Dante Alighieri  |
| 9971-5-0210-0 | A Tale of Two Cities     | Charles Dickens  |
| 960-425-059-0 | The Lord of the Rings    | J. R. R. Tolkien |
| 80-902734-1-6 | And Then There Were None | Agatha Christie  |
+---------------+--------------------------+------------------+

# The borderless layout

=============== ========================== ==================
 ISBN            Title                      Author
=============== ========================== ==================
99921-58-10-7   Divine Comedy              Dante Alighieri
9971-5-0210-0   A Tale of Two Cities       Charles Dickens
960-425-059-0   The Lord of the Rings      J. R. R. Tolkien
80-902734-1-6   And Then There Were None   Agatha Christie
=============== ========================== ==================
```

更加语义化的任务运行详情显示等级接口
------------------------------------

从2.3版本开始，查看任务运行详情选项已经从布尔值变成了从0~3的等级，不过检查等级的过程，很繁琐……

```php
if (self::VERBOSITY_VERBOSE <= $this->verbosity) {
    // ...
}
```

不过在2.4中，我们加了一些快捷方法：

```php
if ($output->isVerbose()) {
    // ...
}

if ($output->isQuiet()) {
    // ...
}

if ($output->isVeryVerbose()) {
    // ...
}

if ($output->isDebug()) {
    // ...
}
```

设置终端显示尺寸
----------------

默认情况Console组建是自适应控制台窗口大小的。不过可能有时也需要指定显示的尺寸大小

在2.4版本很容易做到：

```php
// first argument is the width
// second argument is the height
$app->setTerminalDimensions(80, 50);
````

内置通过服务容器定义命令的功能
------------------------------

在2.4中你可以通过服务容器管理你的命令，比如你现在可以给某个命令注入需要的依赖。
要将某个服务定义为命令，只用简单的给它打上`console.command`的tag就行。

新的注册服务的方式也兼容以前的方式（可被自动识别出来），你可以两种混合使用。
