---
title: 定制Eureka
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: 2020-10-20T15:14:21.000Z
lastmod: 2020-11-22T03:33:26.000Z
draft: false
weight: 4
aliases:
  - customize-eureka
---

在[内容管理](../content-management)中，你已经了解了Eureka的各类内容。接下来我们将介绍Eureka的定制化选项。本文将带领你了解Eureka的配置方式及其选项。

<!--more-->

## 导航栏

你可以简单快捷的定义网页导航栏的内容。在`config/_default/menus.yaml`中，有多个`main`模块，只需根据示例文件中的内容进行修改即可。例如在导航栏加入archive页只需加入以下内容即可：

```yaml
main:
  - name: Archive
    url: /archive/
    weight: 40
```

需要注意的是，导航栏的顺序按`weight`的大小升序排列。

## 代码高亮

Eureka使用highlight.js渲染代码高亮。如需配置highlight.js，只需对`config/_default/params.yaml`中的`highlight`进行相关配置即可。

**highlight.handler(string)**

可选值为highlightjs。

**highlight.highlightjs.languages(list)**

highlight.js默认会包含部分常见语言，通过该属性可配置默认语言外的其他语言。查看[可用的语言](https://github.com/highlightjs/cdn-release/tree/master/build/languages)。

**highlight.highlightjs.style(string)**

Eureka默认使用highlight.js的solarized-light样式，通过该属性可配置使用的样式。查看[可用的样式](https://github.com/highlightjs/cdn-release/tree/master/build/styles)。

## 数学公式

Eureka支持使用KaTeX渲染LaTeX数学公式。如需配置KaTeX，只需对`config/_default/params.yaml`中的`math`进行相关配置即可。

**math.handler(string)**

可选值为`katex`，留空则不启用该功能。

**math.katex(object)**

KaTeX相关配置。具体可选值可参考：[Options · KaTeX](https://katex.org/docs/options.html)。由于Eureka使用了KaTeX的自动渲染拓展，因此链接中的`displayMode`属性将会被忽略。

因为Hugo的配置文件为大小写不敏感的，因此你需要在大写字母前添加`-`或`_`。例如，`throwOnError`应写作`throw-On-Error`或其他有效形式。

Eureka也支持对每个界面是否启动数学公式渲染进行单独配置。例如你有以下文件结构的项目：

```
content/
├── posts
│   ├── post-1.md
│   ├── post-2.md
│   └── ...
│
└── docs
    ├── doc-1
    │   ├── content-1.md
    │   ├── content-2.md
    |   ├── nested-doc
    │   |   ├── nested-content-1.md
    │   |   ├── nested-content-2.md
    |   |   └── _index.md
    │   └── _index.md
    └── ...
```

你可以在任意一级文件的Front Matter内设置`math`属性的值，这会影响该页面或该章节下的所有页面。优先级为Page > Section > Site。例如我在`nested-doc`的Front Matter中设置`math = fasle`而在`nested-content-1.md`的Front Matter中设置`math = true`则会使`nested-content-1.md`渲染数学公式而`nested-doc`文件夹中的其他文件不进行渲染。

## 评论

目前Eureka支持Disqus和Commento两类评论系统。若需激活评论系统，只需修改`config/_default/params.yaml`中`comment`相关内容。以Disqus为例，如需激活Disqus，只需将内容按如下方式修改即可：

```yaml
comment:
  # Options: disqus and commento.
  platform: disqus
  disqus:
    shortname: <your_shortname>
  commento:
    # If self-hosting, please enter the url (e.g. https://commento.example.com) here. Otherwise leave empty.
    url: ''
```

## 图表

Eureka支持使用Mermaid渲染图表。如需配置Mermaid，只需对`config/_default/params.yaml`中的`diagram`进行相关配置即可。

**diagram.handler(string)**

可选值为`mermaid`，留空则不启用该功能。

**diagram.mermaid(object)**

Mermaid相关配置。具体可选值可参考：[Configuration handling in Mermaid API](https://mermaid-js.github.io/mermaid/#/Setup)。

因为Hugo的配置文件为大小写不敏感的，因此你需要在大写字母前添加`-`或`_`。例如，`diagramPadding`应写作`diagram-Padding`或其他有效形式。

## 基本配置文件

在`config/_default/config.yaml`中定义了部分基本配置，帮助你设置网站的一些基础功能。本章节将不涉及前文已包含的内容。

**baseURL(string)**

网站根域名。

**title(string)**

网站标题。

**theme(string)**

网站使用的主题。

**paginate(int)**

每页内容数量。

**copyright(string)**

网站版权声明，会出现在网页最下方。

**enableGitInfo(bool)**

是否使用git信息。默认为`false`。

**enableEmoji(bool)**

是否使用emoji，默认为`false`。

**summaryLength(int)**

概要长度，默认为70。

**defaultContentLanguage(string)**

默认语言的语言代码。

**hasCJKLanguage(bool)**

是否包含中文、日语、韩语内容，默认为`false`。

**defaultContentLanguageInSubdir(bool)**

多语言时默认语言是否处在子链接下，例如默认语言为`zh`时，`/`将会被重定向至`/zh/`。

**googleAnalytics(string)**

Google Analytics代码。从`0.2.1`开始，Google Analytics只在生产环境中生成。如果你想在开发环境中预览，你需要设置Hugo环境变量为`production`。

**markup.tableOfContents(object)**

内容目录渲染方式。

**markup.tableOfContents.startLevel(int)**

开始渲染目录的标题层级。

**markup.tableOfContents.endLevel(int)**

结束渲染目录的标题层级。

**markup.tableOfContents.ordered(bool)**

是否生成有序列表。

**taxonomies(object)**

网站中的所有Taxonomies。

**build(object)**

构建设置。

**build.useResourceCacheWhen(string)**

使用缓存文件进行渲染，如无特殊情况请保持`always`。

除此之外，Hugo还有一些预定义的基本配置，具体可参考[Configure Hugo](https://gohugo.io/getting-started/configuration/)。

## 参数配置文件

除了基本配置外，你还可以设置一些Eureka提供的属性。本章节将不涉及前文已包含的内容。

**mainSections(list)**

列表中的类型将会显示在首页上。

**description(string)**

网站的描述。

**repoEditURL(string)**

内容编辑网址，可在`params.yaml`或Front Matters中定义。值为当前目录对应的仓库编辑地址。

例如在`params.yaml`中定义`repoEditURL: https://github.com/<username>/<repo>/blob/<branch>`即可在每篇文章最下方显示对应链接。

如果只想显示`content/docs`中的内容则可在该文件夹的`_index.md`的Front Matters中定义`repoEditURL: https://github.com/<username>/<repo>/blob/<branch>/content/docs`。其他各层次同理。

**titleSeparator(string/list)**

设置网页标题的分隔符。默认值为`|`。

如只需单层次的分隔符则以字符串形式输入。例如输入`titleSeparator: '-'`则网页标题将类似于`Eureka - 技术公馆`。

如需多层次的分隔符则以列表形式输入，例如输入`titleSeparator: ['|', '-']`则在需要多层次的标题中将显示为`主页配置 - Eureka | 技术公馆`。其他位置将显示为`Eureka | 技术公馆`。

**dateFormat(string)**

网站中显示日期的格式，配置应满足Go语言的[相应格式](https://gohugo.io/functions/format/#gos-layout-string)。

**colorScheme(string)**

网站默认颜色模式。可选值为`auto`、`light`和`dark`。留空为`auto`。

**siteType(string)**

网站类型。

**icon(string)**

网站图标，设置方式可参考[加载图片](../content-management/#加载图片)。

**publisherName(string)**

发布者姓名。

**publisherLogo(string)**

发布者图标，为空则为网站图标。

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>