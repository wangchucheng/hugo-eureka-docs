---
title: 主页配置
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: '2020-12-27T17:50:15+08:00'
lastmod: '2020-12-27T17:50:15+08:00'
draft: false
weight: 2
---

在[入门](../getting-started/)中，相信你已经成功运行了使用Eureka主题的Hugo网站。在本文中你将了解到如何自由配置网站主页。

<!--more-->

## 简介

Eureka提供了一个功能强大且配置灵活的小组件系统来构建主页。Eureka提供的小组件系统可以在不编写代码的情况下自由组合并自定义组件样式。

Eureka目前提供的小组件有：

-	**pages**：以列表或卡片等多种形式显示文章的组件。
-	**about**：显示网站作者信息的组件。
-	**vintage**：经典的Eureka主页组件。
-	**blank**：可彻底自定义的组件。
-	**experiences**: 显示包含职位、工作单位、时间地点及简介等信息的职业经历。

主页内容由`content/homepage`文件夹中的文件定义，每一个小组件对应一个文件。

## 新建小组件

你可以使用以下命令在`homepage`文件夹中生成一个`pages`类型的小组件：

```
hugo new -k widgets/pages content/zh/homepage/<your-name.md>
```

需要注意的是，`blank`类型为用户提供了可以自由编写html代码并嵌入Eureka的功能，所以其文件类型为html。在生成`blank`类型的文件时应指定其类型为`.html`而非`.md`。

```
hugo new -k widgets/blank content/zh/homepage/<your-name.html>
```

## 配置小组件

生成小组件后你可以通过Front Matter中的属性对小组件进行配置，小组件的共用属性都包含在`[widget]`内。

**handler(string)**

小组件类型。

**width(string)**

小组件宽度，可选值为sm，md，lg和xl。默认为md。

**sidebar.position(string)**

侧边栏位置，可选值为left和right。留空为不显示。

**sidebar.scale(string)**

侧边栏宽度，可选值为sm，md，lg和xl。默认为md。

**background.color(string)**
	
背景颜色，可选值为primary，secondary，tertiary和任意css中有效的颜色值。默认为primary。背景图片优先级高于背景颜色。

**background.image(string)**

背景图片，可填入本地链接或外链。更多见[加载图片](../content-management#加载图片)。

**background.size(string)**

背景图片尺寸，可选值为auto，cover和contain。默认为auto。

**background.position(string)**

背景图片位置，可选值为center，top，right，bottom和left。

**background.attachment(string)**

背景图片固定方式，可选值为fixed，local和scroll。

### 配置Pages小组件

pages小组件有部分特有属性，也可以快速地进行配置。

**section(string)**

需要显示的章节，例如`posts`等。

**count(int)**

显示的文章数，默认为5。

**style(string)**

显示样式，可选值为card，plain和masonry。

### 配置About小组件

about小组件的属性名与作者页参数一致，可参考[作者页参数](../content-management#作者页参数)。

### 配置Vintage小组件

vintage小组件默认为两张图片和一句标语构成。你可以简单地自定义图片内容及标语内容。

**slogan(string)**

vintage小组件标语。

**imgLeft(string)**

vintage小组件左侧图片，设置方式可参考[加载图片](../content-management/#加载图片)。

**imgRight(string)**

vintage小组件右侧图片，设置方式可参考[加载图片](../content-management/#加载图片)。

### 配置Experiences小组件

Experiences小组件由多个包含职位、工作单位、时间地点及简介等信息的职业经历卡片组成。

可能的使用方式可以包括职业经历、教育经历、奖项、项目等。

所有Experiences小组件的信息包含在Front Matter中。更多的职业经历可以通过在Front Matter列表中添加新的对象进行添加。

示例结构如下所示：

```
experiences:
	- title:
		organization:
			name:
			url:
		dates:
		location:
		writeup:

	- title:
		...  (同上)
```

**experiences.title(string)**
可选。该字符串会显示在卡片最上方，可使用Markdown语法。

**experiences.organization.name(string)**
可选。该字符串会显示在工作地点旁吗，可使用Markdown语法。

**experiences.organization.url(string)**
可选。该值可作为工作单位的链接地址。

**experiences.dates(string)**
可选。工作时间，可使用Markdown语法。

**experiences.location(string)**
可选。工作地点，可使用Markdown语法。

**experiences.writeup(string)**
可选。该值为经历简述，可使用Markdown语法。

如果需要在Front Matter中使用多行字符串，可参考如下示例：

```
    writeup: >
      Donec scelerisque egestas augue at tempor. Fusce faucibus magna in.

      - Suspendisse lacinia mauris a laoreet vehicula.

      - Aenean tincidunt enim vitae ante blandit tempor.

      - Nam tincidunt diam quis lorem rutrum ullamcorper.
```

## 小组件排序

网站主页由小组件构成，你也可以快速设置其显示顺序。

每个小组件的Front Matter中都有`weight`属性值，你只需设置该值即可确定小组件顺序。

主页显示顺序为`weight`值按升序排列。

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>