---
title: 多语言模式
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: '2020-10-21T23:11:23+08:00'
lastmod: '2020-10-21T23:11:23+08:00'
draft: false
weight: 5
---

除了前文的[内容管理](../content-management/)以及[定制Eureka](../customization/)，Eureka也支持多语言模式。本文将带领你了解如何构建一个多语言网站。

<!--more-->

>	如果你的区域存在难以访问GitHub的问题，你可以将所有涉及到GitHub的网址替换为[Gitee镜像](https://gitee.com/wangchucheng/hugo-eureka/)。例如将`https://github.com/wangchucheng/hugo-eureka/`替换为`https://gitee.com/wangchucheng/hugo-eureka/`即可。

## 多语言配置

首先我们需要对配置文件进行一些修改以使用多语言功能。

将`config/_default/languages.yaml`中注释的内容取消注释。具体而言，对于默认语言的`contentDir`属性，取消其注释并将原来`content`文件夹中的所有内容移至`content/<language_code>/`文件夹中。

接下来将其他语言的配置取消注释，你可以在其中修改特定配置属性的值，就像示例中的`title`一样。

之后我们需要继续修改导航栏的相关内容。首先请在`config/_default/`文件夹中新建`menus.<language_code>.yaml`文件，并复制`menus.yaml`中的内容并进行相应设置。

最后，Eureka中有一些`i18n`字符串。Eureka目前官方支持的语言为：

-	中文
-	英文

由社区提供的语言支持：

-	法语
-	德语
-	意大利语
-	韩语
-	波兰语
-	俄语

如果你需要其他语言的翻译，你可以将[i18n](https://github.com/wangchucheng/hugo-eureka/tree/master/i18n)文件夹复制到项目根目录中，并根据其中的内容添加你语言的翻译，并以相应的语言代码命名。

我们同时欢迎用户为我们提供其他语言的翻译，你可以提交相应的[Pull Request](https://github.com/wangchucheng/hugo-eureka/pulls)给我们。

至此我们完成了多语言的配置。

## 多语言内容

在前一步，相信你已经将`content`文件夹中的内容移动至了`content/<language_code>/`文件夹中。多语言内容与[内容管理](../content-management)相似，但是新建内容的方式并不相同。接下来将介绍如何在多语言网站中新建内容。

单一语言时，我们新建文件只需要使用如下指令：

```shell
hugo new posts/<your_post.md>
```

而在多语言时则会生成在某一语言中，如果你想指定生成的语言位置，可以使用如下方式：

```shell
hugo new content/<language_code>/posts/<your_post.md>
```

需要注意的是，路径需从`content`开始。、

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>
