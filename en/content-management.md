+++
title = "Content Management"
description = ""
summary = ""
toc = true
authors = []
tags = []
categories = []
series = []
date =  2020-10-20T10:30:48+08:00
lastmod = 2020-11-22T11:54:28+08:00
draft = false

weight = 3
+++

In [Getting Started](../getting-started), I believe you have successfully run the Hugo website using Eureka theme. Next we will add some content. This article will lead you to understand the structure of the website content and editing skills.

<!--more-->

## Directory Structure

For single-language projects, you can manage the content in the `content` folder under the project root directory. For multilingual projects, the content is in a language-specific directory, such as `content/en/`.

The content of the content root directory is generally classified according to website modules and their structure. For example, we generally store blog posts in `content/posts/`. The main types currently provided by Eureka are:

- Post page
- Document page
- Author page

### New Post Page

The post content is Eureka's default structure, so there is no need to specify its type when creating a new post page.

```shell
hugo new posts/<your_post.md>
```

The above command can create a new Markdown file containing the default Front Matter in the `content/posts/` folder.

### New Document Page

When creating a new document page, you need to specify its type as `docs`.

```shell
hugo new -k docs docs/<your_doc>/<your_page.md>
```

The above command can create a new Markdown file containing the default document content in the `content/docs/<your_doc>/` folder.

If you have not created the content of the document type before, you need to generate the document list first:

```shell
hugo new -k docs docs
```

### Multi-version document

Eureka supports multiple versions of documents. You only need to copy all the contents of the historical version to the subfolder named version number. The version number should follow [Semantic Version](https://semver.org/), and whether the version number contains `v` at the beginning can be recognized normally.

Take the following directory structure as an example:

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

If you want to create a document of version `1.0.0`, you just need to move all the content to a folder named `1.0.0`.

### New Author Page

When creating a new author page, you need to specify its type as `authors`.

```shell
hugo new -k authors authors/<your_author>
```

The above command can create a new folder containing default author content in the `content/authors/` folder.

## File Structure

Hugo's content file is mainly composed of two parts, the Front Matter at the front of the file and the body part after it. Front Matter can use toml, yaml or json format. The body part follows Markdown syntax.

```toml
+++
title = "Hello World"
description = ""
toc = true
authors = []
tags = []
categories = []
series = []
...
+++
```

The above is a basic Front Matter style. You can set various attributes through it.

If you need to understand Hugo's predefined Front Matter or more about Front Matter, you can refer to Hugo's [Related Documents](https://gohugo.io/content-management/front-matter/).

## Front Matter

### Post Page Front Matters

The post page has the following commonly used Front Matters:

- **title(string)**: Post title.
- **description(string)**: Post description.
- **toc(bool)**: Whether to activate the directory, the default is `false`.
- **authors(array)**: The author of the post, whose name should match the content in `content/authors/`.
- **tags(array)**: Post tags.
- **categories(array)**: Post categories.
- **series(array)**: Post series.
- **date(string)**: The time that the post was published, the format should meet the [RFC 3339](https://tools.ietf.org/html/rfc3339) date format.
- **lastmod(string)**: The last modification time of the post, the format should meet the [RFC 3339](https://tools.ietf.org/html/rfc3339) date format.
- **featuredVideo(string)**: Featured video. Please refer to [Video Loading](#video-loading). When `featuredVideo` and `featuredImage` exist at the same time, only `featuredVideo` will be displayed.
- **featuredImage(string)**: Featured image. Please refer to [Image Loading](#image-loading) for related operations.
- **draft(bool)**: Whether it is a draft, the default is `true`.

If you need to understand Hugo's predefined Front Matter, you can refer to Hugo's [Related Documents](https://gohugo.io/content-management/front-matter/).

### Document Page Front Matters

The documentation page has the following commonly used Front Matters:

- **title(string)**: The title of this page of the document.
- **description(string)**: Description of this page of the document.
- **toc(bool)**: Whether to activate the directory, the default is `false`.
- **authors(array)**: The name of the author of this page of the document should match the content in `content/authors/`.
- **date(string)**: The publication time of this page of the document, and the format should meet the [RFC 3339](https://tools.ietf.org/html/rfc3339) date format.
- **lastmod(string)**: The last modification time of this page of the document, and the format should meet the [RFC 3339](https://tools.ietf.org/html/rfc3339) date format.
- **featuredImage(string)**: Featured pictures on this page of the document. For related operations, please refer to [Image Loading](#image-loading).
- **draft(bool)**: Whether it is a draft, the default is `true`.

If you need to understand Hugo's predefined Front Matter, you can refer to Hugo's [Related Documents](https://gohugo.io/content-management/front-matter/).

### Author Page Front Matters

The author page has the following commonly used Front Matters:

- **title(string)**: Author name.
- **role(string)**: Author role.
- **bio(string)**: The author's briefly introduction.
- **avatar(string)**: The author's avatar. For related operations, please refer to [Image Loading](#image-loading).
- **organization(object)**: Author's current organization.
  - **name(string)**: Organization name.
  - **url(stirng)**: Organization URL.
- **social(array)**: Social media information.
  - **icon(string)**: Social media name. Available icons can be checked on [Font Awesome](https://fontawesome.com/). After querying, you can get results similar to `<i class="fab fa-github"></i>`. The value of icon is github.
  - **iconPack(string)**: Social media package name. The value of iconPack is the fab in the previous item.
  - **url(string)**: Social media links.

If you need to understand Hugo's predefined Front Matter, you can refer to Hugo's [Related Documents](https://gohugo.io/content-management/front-matter/).

## Math

Eureka supports the use of KaTeX to render mathematical formulas. You can find a way to configure KaTeX in [Customize Eureka](../customization/#math).

You can use `$...$` or `\(...\)` to enter inline equations, and `&&...&&` or `\[...\]` to enter displayed equations.

When typing in a document, some Markdown syntax will conflict with LaTeX (such as `_` and `\`), which may cause the TeX code to be processed by the Markdown renderer and display incorrect results. Eureka provides two solutions.

The first solution is that you can use `\\` instead of `\` and `\\_` instead of `_` to solve this problem, but this means that you need to modify your LaTeX formulas, which makes migration difficult.

The second method is to use html tags to wrap the formula block, this method can only be used for displayed equations. You can wrap the line formula in `<div>`:

```html
<div>
your_displayed_equation
</div>
```
It should be noted that when using this method, the `unsafe` attribute of `[markup.goldmark.renderer]` in the `config.toml` configuration file should be set to `true`.

## Video Loading

There are some places in Eureka that need to load videos, such as featured video. Eureka provides a variety of video loading methods, all of which need to be implemented by specifying the path in Front Matter. The video link supports local videos and external videos.

For locally stored videos, you can store the video in the `static` folder under the project root directory and fill in the relative path in the configuration file. For example, to store `example.mp4` in `assets/videos/example.mp4`, you only need to set the corresponding attribute in Front Matter (for example, featuredVideo) to:

```toml
featuredVideo = "videos/example.mp4"
```

For sharing videos on video sites, you only need to set the value of the Front Matter corresponding property (such as featuredVideo) to the video player url. It should be noted that the video player URL is not the URL of the video website, but the value of the `src` attribute in its embed code (usually an iframe).

```toml
featuredVideo = "https://example.com"
```

## Image Loading

There are many places where pictures need to be loaded in Eureka, such as homepage pictures or author avatars. Eureka provides a very rich image loading method:

### Image Loading in Config Files

We need to add pictures in some places in the configuration file, such as homepage pictures. The image link in the configuration file supports local links and external links.

For locally stored pictures, you can choose to store the pictures in the `assets` or `static` folder under the project root directory, and fill in the relative path in the configuration file. For example, to store `example.jpg` in `assets/images/example.jpg`, you only need to set the configuration file as:

```toml
imgLeft = "images/example.jpg"
```

It should be noted that the `icon` attribute can only be stored in the `assets` folder.

For external images, you only need to set the value of the corresponding attribute of the configuration file to the image url.

```toml
imgLeft = "https://example.com"
```

### Add Images in Front Matter

Sometimes we need to add pictures to the Front Matter of the content, such as the author's avatar. In addition to the two methods mentioned in [Image Loading In Configuration](#image-loading-in-config-files), you can also name the picture with a specific file name and store it in the same folder as the content.

The following is how the current attributes are named:

- **featuredImage**: featured.jpg
- **avatar**: avatar.jpg

---

<div class="flex flex-col items-center">
	<span class="mb-4">Please <a href="https://github.com/wangchucheng/hugo-eureka">Star</a> Eureka if you like it!</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>