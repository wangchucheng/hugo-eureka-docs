---
title: 内容管理
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: '2020-10-20T10:30:48+08:00'
lastmod: 2020-11-22T03:54:28.000Z
draft: false
weight: 3
---

在[主页配置](../homepage-configuration)中，你已经成功地构建了网站主页。接下来我们将添加一些内容。本文将带领你了解网站内容结构及编辑技巧。

<!--more-->

## 目录结构

对于单一语言的项目，你可以在项目根目录下的`content`文件夹中管理内容。对于多语言项目，内容则处在特定语言的目录下，例如`content/zh/`。

内容根目录的内容一般根据网站模块及其结构进行分类，例如我们一般将博客文章储存于`content/posts/`中。Eureka目前的提供的主要类型为：

- 文章页
- 文档页
- 作者页

### 新建文章页

文章内容为Eureka默认的文章结构，因此新建文章页时不需指定其类型。

```shell
hugo new posts/<your_post.md>
```

以上命令可以在`content/posts/`文件夹中新建一个包含默认Front Matter的Markdown文件。

### 新建文档页

新建文档页时需指定其类型为`docs`。

```shell
hugo new -k docs docs/<your_doc>/<your_page.md>
```

以上命令可以在`content/docs/<your_doc>/`文件夹中新建一个包含默认文档内容的Markdown文件。

如果你此前没有创建过文档类型的内容，你需要先生成文档列表：

```shell
hugo new -k docs docs
```

### 多版本文档

Eureka支持多版本文档。你只需将历史版本全部内容复制到名称为版本号的子文件夹下即可。版本号需遵循[语义化版本](https://semver.org/)，版本号最前是否包含`v`均可以被正常识别。

以如下目录结构为例：

```text
content
├── docs
│      ├── doc-1
│      │      ├── content1.md
│      │      ├── content2.md
│      │      ├── 1.0.0
│      │      │      ├── content1.md
│      │      │      ├── content2.md
│      │      │      └── _index.md
│      │      └── _index.md
│      └── ...   
└── ...
```

如果你想创建`1.0.0`版本的文档，你只需将所有内容移至以`1.0.0`命名的文件夹中即可。

### 新建作者页

新建作者页时需指定其类型为`authors`。

```shell
hugo new -k authors authors/<your_author>
```

以上命令可以在`content/authors/`文件夹中新建一个包含默认作者内容的文件夹。

## 文件结构

Hugo的内容文件主要由两部分组成，文件最前部的Front Matter及之后的正文部分。Front Matter可以使用toml，yaml或json形式。正文部分则遵循Markdown语法。

```yaml
---
title: Hello World
description:
toc: true
authors: []
tags: []
categories: []
series: []
...
---
```

以上为一个基本的Front Matter的样式。你可以通过其设置各类属性。

如果你需要了解Hugo预定义的Front Matter或更多关于Front Matter的内容，可以参考Hugo的[相关文档](https://gohugo.io/content-management/front-matter/)。

## Front Matter

### 文章页参数

文章页有以下常用Front Matter参数：

- **title(string)**：文章标题。
- **description(string)**：文章描述。
- **toc(bool)**：是否激活目录，默认为`false`。
- **authors(array)**：文章作者，名称应于与`content/authors/`内的内容相符。
- **tags(array)**：文章标签。
- **categories(array)**：文章分类。
- **series(array)**：文章系列。
- **date(string)**：文章发表时间，格式应满足[RFC 3339](https://tools.ietf.org/html/rfc3339)日期格式。
- **lastmod(string)**：文章最后修改时间，格式应满足[RFC 3339](https://tools.ietf.org/html/rfc3339)日期格式。
- **featuredVideo(string)**：文章精选视频，相关操作可参考[加载视频](#加载视频)，`featuredVideo`与`featuredImage`同时存在时，只会显示`featuredVideo`。
- **featuredImage(string)**：文章精选图片，相关操作可参考[加载图片](#加载图片)。
- **draft(bool)**：是否为草稿，默认为`true`。

如果你需要了解Hugo预定义的Front Matter，可以参考Hugo的[相关文档](https://gohugo.io/content-management/front-matter/)。

### 文档页参数

文档页有以下常用Front Matter参数：

- **title(string)**：文档该页标题。
- **description(string)**：文档该页描述。
- **toc(bool)**：是否激活目录，默认为`false`。
- **authors(array)**：文档该页作者，名称应于与`content/authors/`内的内容相符。
- **date(string)**：文档该页发表时间，格式应满足[RFC 3339](https://tools.ietf.org/html/rfc3339)日期格式。
- **lastmod(string)**：文档该页最后修改时间，格式应满足[RFC 3339](https://tools.ietf.org/html/rfc3339)日期格式。
- **featuredImage(string)**：文档该页精选图片，相关操作可参考[加载图片](#加载图片)。
- **draft(bool)**：是否为草稿，默认为`true`。

如果你需要了解Hugo预定义的Front Matter，可以参考Hugo的[相关文档](https://gohugo.io/content-management/front-matter/)。

### 作者页参数

作者页有以下常用Front Matter参数：

- **title(string)**：作者姓名。
- **role(string)**：作者角色。
- **bio(string)**：作者简要介绍。
- **avatar(string)**：作者头像，相关操作可参考[加载图片](#加载图片)。
- **organization(object)**：作者当前机构。
  - **name(string)**：机构姓名。
  - **url(stirng)**：机构网址。
- **social(array)**：社交媒体信息。
  - **icon(string)**：社交媒体名称。可用的图标可以在[Font Awesome](https://fontawesome.com/)上进行查询。查询后你可以获得类似`<i class="fab fa-github"></i>`的结果。icon的值即为github。
  - **iconPack(string)**：社交媒体包名。iconPack的值为上一项中的fab。
  - **url(string)**：社交媒体链接。

如果你需要了解Hugo预定义的Front Matter，可以参考Hugo的[相关文档](https://gohugo.io/content-management/front-matter/)。

## 数学公式

Eureka支持使用KaTeX渲染数学公式。你可以在[定制Eureka](../customization/#数学公式)中找到配置KaTeX的方式。

你可以使用`$...$`或`\(...\)`输入行内公式，使用`&&...&&`或`\[...\]`输入行间公式。

在文档中输入时，由于部分Markdown语法会与LaTeX冲突（例如`_`与`\`），可能会导致TeX代码被Markdown渲染器处理，而显示错误的结果。Eureka提供了两种解决方案。

第一种方案是你可以使用`\\`代替`\`以及`\\_`代替`_`解决此问题，但这意味着你需要修改你的LaTeX公式，导致了迁移的困难。

第二种方式则是使用html标签包裹公式块，此种方法只能针对行间公式。可将行间公式包裹在`<div>`内：

```html
<div>
your_displayed_equation
</div>
```

需要注意的是，在使用这种方法时，在`config.yaml`配置文件中的`markup.goldmark.renderer`的`unsafe`属性应设为`true`。

## 加载视频

Eureka中有一些需要加载视频的地方，例如精选视频。Eureka提供了多种视频加载方式，这些方式都需要通过在Front Matter中指定路径来实现。视频链接支持本地视频以及外链。

对于本地存储的视频，你可以将视频存储于项目根目录下的`static`文件夹，并在配置文件中填写其相对路径。例如将`example.mp4`存储于`assets/videos/example.mp4`，你只需将Front Matter中对应属性（例如featuredVideo）设置为：

```yaml
featuredVideo: videos/example.mp4
```

对于视频网站的分享视频，你只需将Front Matter对应属性（例如featuredVideo）的值设置为视频播放器url即可。需要注意的是，视频播放器url并非视频网站的网址，而是其嵌入代码（一般为iframe）中`src`属性的值。

```yaml
featuredVideo: https://example.com
```

## 加载图片

Eureka中有许多需要加载图片的地方，例如主页图片或作者头像等。Eureka提供了非常丰富的图像加载方式：

### 在配置文件中添加图片

我们需要在配置文件中的一些地方添加图片，例如主页图片。配置文件中的图片链接支持本地链接以及外链。

对于本地存储的图片，你可以选择将图片存储于项目根目录下的`assets`或`static`文件夹，并在配置文件中填写其相对路径。例如将`example.jpg`存储于`assets/images/example.jpg`，你只需将配置文件设置为：

```yaml
imgLeft: images/example.jpg
```

需要注意的是，`icon`属性只能存储于`assets`文件夹中。

对于外链图片，你只需将配置文件对应属性的值设置为图片url即可。

```yaml
imgLeft: https://example.com
```

### 在Front Matter中添加图片

有时我们需要在内容的Front Matter中添加图片，例如作者头像。除了[在配置文件中添加图片](#在配置文件中添加图片)提到的两种方式外，你还可以将图片以特定文件名命名并存储于内容的同一文件夹下。

以下为当前属性的命名方式：

- **featuredImage**：featured.jpg
- **avatar**：avatar.jpg

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>