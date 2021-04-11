---
title: Homepage Configuration
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

In [Getting Started](../getting-started), I believe you have successfully run the Hugo website using Eureka theme. In this article you will learn how to configure the website homepage.

<!--more-->

## Introduction

Eureka provides a powerful and flexible widget system to build a homepage. The widget system can freely combine and customize components without writing code.

Eureka currently provides these widgets:

-	**pages**：Display pages in multiple forms such as list or card.
-	**about**：A widget that displays information about the website author.
-	**vintage**：The classic Eureka homepage component.
-	**blank**：Completely customizable widget.
-	**experiences**: Displays cards containing information such as position/title, organization, some dates, location, title, and a writeup.

The content of the homepage is defined by the files in the `content/homepage` folder, and each widget corresponds to a file.

If you never configured homepage before, you can use this command to new `homepage` folder:

```
hugo new -k homepage homepage
```

If your website has multiple languages, you can use this command to new:

```
hugo new -k homepage content/en/homepage
```

>	So far, if you use Hugo Modules to install Eureka, this command cannot create the folder correctly. You need to manually copy the [homepage](https://github.com/wangchucheng/hugo-eureka/tree/master/archetypes/homepage) folder to your `content` folder.

## New Widget

You can use the following command to generate a widget of type `pages` in the `homepage` folder:

```
hugo new -k widgets/pages homepage/<your-name.md>
```

If your website has multiple languages, you can use this command to new:

```
hugo new -k widgets/pages content/en/homepage/<your-name.md>
```

It should be noted that the `blank` type provides users with the ability to freely write html code and embed in Eureka, so the file type is html. When generating a file of type `blank`, specify its type as `.html` instead of `.md`.

```
hugo new -k widgets/blank homepage/<your-name.html>
```

If your website has multiple languages, you can use this command to new:

```
hugo new -k widgets/blank content/en/homepage/<your-name.html>
```

## Widget Configuration

After the widget is generated, you can configure the widget through the attributes in Front Matter. The common parameters of the widget are included in `[widget]`.

**handler(string)**

Widget type.

**width(string)**

The width of the widget. The optional values are sm, md, lg and xl. The default is md.

**sidebar.position(string)**

The position of the sidebar. The optional values are left and right. Leave blank to not display.

**sidebar.scale(string)**

The width of the sidebar. The optional values are sm, md, lg and xl. The default is md.

**background.color(string)**
	
Background color, optional values are primary, secondary, tertiary and any valid color value in css. The default is primary. The background image has priority over the background color.

**background.image(string)**

Background image, you can fill in local link or external link. For more information, see [Image Loading](../content-management#image-loading).

**background.size(string)**

The size of the background image, the optional values are auto, cover and contain. The default is auto.

**background.position(string)**

The position of the background image. The optional values are center, top, right, bottom and left.

**background.attachment(string)**

Background image attachment. The optional values are fixed, local and scroll.

### Pages Widget Configuration

The pages widget has some unique attributes and can also be configured quickly.

**section(string)**

The section to be displayed, such as `posts`, etc.

**count(int)**

The count of posts displayed, the default is 5.

**style(string)**

Display style, optional values are card, plain and masonry.

### About Widget Configuration

The Front Matters of the about widget is consistent with the author page parameters, please refer to [Author Page Front Matters](../content-management#author-page-front-matters).

### Vintage Widget Configuration

The vintage widget is composed of two images and a slogan by default. You can easily customize the images and the slogan.

**slogan(string)**

Vintage widget slogan.

**imgLeft(string)**

The image on the left side of the vintage widget. For the setting method, please refer to [Image Loading](../content-management/#image-loading).

**imgRight(string)**

The picture on the right side of the vintage widget. For the setting method, please refer to [Image Loading](../content-management/#image-loading).

### Experiences Widget Configuration

The experiences widget is composed of multiple cards where each card displays a title, an organization (with a hyperlinked url), some dates, a location, and a writeup. There can be as many cards as desired in the experiences widget with each card containing their relevant information.

Example usages for the experiences widget include documenting employment history, education history, awards, projects, etc.

All the relevant parameters are contained in experiences section of the front matter. Additional cards can be added by adding a dash with the relevant parameters (title, organization, dates, location, writeup).

Example below of the structure of the configuration.

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
		...  (repeat as necessary to add new cards below)
```

**experiences.title(string)**
Optional. This string is at the top of the card in bold and in larger font size relative to the rest of the card..
Markdown formatting is enabled.

**experiences.organization.name(string)**
Optional. This string is shown beside the country string below the title in normal sized font.
Markdown formatting is enabled.

**experiences.organization.url(string)**
Optional. This url string in this parameter is used as the destination when the organization string is clicked.

**experiences.dates(string)**
Optional. This string is shown below the title in normal sized font.
Markdown formatting is enabled.

**experiences.location(string)**
Optional. This string is shown beside the organization name string below the title in normal sized font.
Markdown formatting is enabled.

**experiences.writeup(string)**
Optional. This string is what is shown at the bottom of the card below all other parameters. Markdown formatting is enabled. 

To allow line breaks and bullet points, a blank line is required between each seperate line. Example below.

```
    writeup: >
      Donec scelerisque egestas augue at tempor. Fusce faucibus magna in.

      - Suspendisse lacinia mauris a laoreet vehicula.

      - Aenean tincidunt enim vitae ante blandit tempor.

      - Nam tincidunt diam quis lorem rutrum ullamcorper.
```

## Sorting Widgets

The homepage of the website is composed of widgets, and you can quickly set the display order.

Each widget’s Front Matter has a `weight` parameter value, you only need to set this value to determine the order of the widgets.

The display order of the homepage is the `weight` value in ascending order.

---

<div class="flex flex-col items-center">
	<span class="mb-4">Please <a href="https://github.com/wangchucheng/hugo-eureka">Star</a> Eureka if you like it!</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>