---
title: 让Typecho文章内的超链接在新窗口打开
id: 10
date: 2023-10-17 08:43:37
auther: admin
excerpt: 支持两种形式的链接语法：行内式和参考式两种形式。而我们打开所生产的超链接，默认是在本窗口打开的，为了有更好的阅读体验，我们往往希望在新窗口。要想让的文章中链接加上“”，也有很多种方法，比如通过在网页搜索标签，为其添加新窗口属性。下面这种方式是直接修改程序源码，来实现：在搜索
permalink: /archives/10
categories:
 - note
tags: 
 - typecho
 - 超链接
 - markdown
---

Markdown支持两种形式的链接语法：行内式和参考式两种形式。
而我们打开所生产的超链接，默认是在本窗口打开的，为了有更好的阅读体验，我们往往希望在新窗口。
要想让Typecho的文章中链接加上“_blank”，也有很多种方法，比如通过jQuery在网页搜索<a>标签，为其添加新窗口属性。
下面这种方式是直接修改Typecho程序源码，来实现：
在\var\CommonMark\HtmlRenderer.php 搜索

    case CommonMark_Element_InlineElement::TYPE_LINK:
    $attrs['href'] = $this->escape($inline->getAttribute('destination'), true);
    if ($title = $inline->getAttribute('title')) {
        $attrs['title'] = $this->escape($title, true);
    }
    
    return $this->inTags('a', $attrs, $this->renderInlines($inline->getAttribute('label')));

在return前加上下面这段代码：

    $attrs['target'] = '_blank'; // 给链接增加_blank属性