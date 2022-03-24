---
title: Customize Eureka
description: ""
summary: ""
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

In [Content Management](../content-management), you have already learned about all kinds of content of Eureka. Next, we will introduce Eureka's customization options. Customize Eureka will lead you to understand how Eureka is configured and its options.

<!--more-->

## Style

You can customize the colors and fonts of Eureka by setting the `style` param in `config/_default/params.yaml`. Set this param to `default` or leave it blank to use the default style.

If you want to customize the style, you can create a config file with the style name you want in `data/styles/`. Then you can set the `style` param to your style name. You can refer to the [default style](https://github.com/wangchucheng/hugo-eureka/blob/master/data/styles/default.yaml) to see available params of a style.

## Navigation Bar

You can define the content of the web page navigation bar simply and quickly. In `config/_default/menus.yaml`, there are multiple `main` modules, just modify them according to the content in the sample file. For example, adding the archive page in the navigation bar only needs to add the following content:

```yaml
main:
  - name: Archive
    url: /archive/
    weight: 40
```

It should be noted that the order of the navigation bar is in ascending order of the size of `weight`.

## Highlight

Eureka uses highlight.js to render code highlighting. If you need to configure highlight.js, you only need to configure the `highlight` in `config/_default/params.yaml`.

**highlight.handler(string)**

The optional value is highlightjs.

**highlight.highlightjs.languages(list)**

Highlight.js will include some common languages by default, and other languages can be configured through this property. See [Available Languages](https://github.com/highlightjs/cdn-release/tree/master/build/languages).

**highlight.highlightjs.style(string)**

Eureka uses the solarized-light style of highlight.js by default, and the style used can be configured through this property. See [Available Styles](https://github.com/highlightjs/cdn-release/tree/master/build/styles).

## Math

Eureka supports the use of KaTeX to render LaTeX mathematical formulas. If you need to configure KaTeX, you only need to configure the `math` in `config/_default/params.yaml`.

**math.handler(string)**

The optional value is `katex`, leave it blank to disable this feature.

**math.katex(object)**

KaTeX related configuration. For specific optional values, please refer to: [Options · KaTeX](https://katex.org/docs/options.html). Since Eureka uses KaTeX's auto-render extension, the `displayMode` property in the link will be ignored.

Because Hugo's config params are case-insensitive, you need to add `-` or `_` before the uppercase letters. For example, `throwOnError` should be written as `throw-On-Error` or other acceptable formats.

Eureka also supports independent configuration of whether to render math formula for each page or section. For example, you have a project with the following file structure:

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

You can set the value of the `enableMath` attribute in the Front Matter of the file in any level, which will affect this page or all pages under this section. The priority is Page > Section > Site. For example, if I set `enableMath: fasle` in Front Matter of `nested-doc` and set `enableMath: true` in Front Matter of `nested-content-1.md`, it will make `nested-content-1.md` render math formulas. Formulas in other files under the `nested-doc` folder will not be rendered.

## Comment

Eureka supports using Disqus, Utterances and Commento as comment system。If you need to configure comment, you just need to configure the `comment` in `config/_default/params.yaml`

Eureka also supports independent configuration of whether to enable comment for each page or section. For example, you have a project with the following file structure:

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

You can set the value of the `enableComment` attribute in the Front Matter of the file in any level, which will affect this page or all pages under this section. The priority is Page > Section > Site. For example, if I set `enableComment: fasle` in Front Matter of `nested-doc` and set `enableComment: true` in Front Matter of `nested-content-1.md`, it will make `nested-content-1.md` enable comment. Comment in other files under the `nested-doc` folder will not be enabled.

**comment.handler(string)**

The optional value is `disqus`, `utterances`, `valine` and `commento`, leave it blank to disable this feature.

**comment.disqus.shortname(string)**

The shortname of Disqus.

**comment.utterances(object)**

Utterances related configuration. For specific optional values, please refer to: [utterances](https://utteranc.es/). If you want the color scheme of utterances to follow eureka's, you can set `theme` to `eureka` in config params.

**comment.valine(object)**

Valine related configuration. For specific optional values, please refer to: [Config Reference | Valine](https://valine.js.org/en/configuration.html).

Because Hugo's config params are case-insensitive, you need to add `-` or `_` before the uppercase letters. For example, `appId` should be written as `app-Id` or other acceptable formats.

**comment.commento.url**

If self-hosting, please enter the url (e.g. https://commento.example.com) here. Otherwise leave empty.

## Diagram

Eureka supports the use of Mermaid to render diagrams. If you need to configure Mermaid, you only need to configure the `diagram` in `config/_default/params.yaml`.

**diagram.handler(string)**

The optional value is `mermaid`, leave it blank to disable this feature.

**diagram.mermaid(object)**

Mermaid related configuration. For specific optional values, please refer to: [Configuration handling in Mermaid API](https://mermaid-js.github.io/mermaid/#/Setup).

Because Hugo's config params are case-insensitive, you need to add `-` or `_` before the uppercase letters. For example, `diagramPadding` should be written as `diagram-Padding` or other acceptable formats.

## Basic Config File

Some basic configurations are defined in `config/_default/config.yaml` to help you set up some basic functions of the website. This chapter will not cover the content already contained in the previous article.

**baseURL(string)**

The root domain name of the site.

**title(string)**

Site title.

**theme(string)**

The theme used on the site.

**paginate(int)**

The number of content per page.

**copyright(string)**

The site copyright statement will appear at the bottom of the page.

**enableGitInfo(bool)**

Whether to use git information. The default is `false`.

**enableEmoji(bool)**

Whether to use emoji, the default is `false`.

**summaryLength(int)**

Summary length, the default is 70.

**defaultContentLanguage(string)**

The language code of the default language.

**hasCJKLanguage(bool)**

Whether to include Chinese, Japanese, and Korean content, the default is `false`.

**defaultContentLanguageInSubdir(bool)**

Whether the default language is under the sub-link when multilingual, for example, when the default language is `en`, `/` will be redirected to `/en/`.

**googleAnalytics(string)**

Google Analytics code. Starting from `0.2.1`, Google Analytics is only generated in the production environment. If you want to preview in the development environment, you need to set the Hugo environment variable to `production`.

**markup.tableOfContents(object)**

Table of contents rendering method.

**markup.tableOfContents.startLevel(int)**

Start title level of the table of contents.

**markup.tableOfContents.endLevel(int)**

End title level of the table of contents.

**markup.tableOfContents.ordered(bool)**

Whether to generate an ordered list.

**taxonomies(object)**

All taxonomies in the website.

**build(object)**

Build settings.

**build.useResourceCacheWhen(string)**

Use cache files for rendering. If there are no special circumstances, please keep `always`.

In addition, Hugo also has some predefined basic configurations. For details, please refer to [Configure Hugo](https://gohugo.io/getting-started/configuration/).

## Params Config File

In addition to the basic configuration, you can also set some params provided by Eureka. This chapter will not cover the content already contained in the previous article.

**mainSections(list)**

The types in the list will be displayed on the homepage.

**description(string)**

The description of the site.

**repoEditURL(string)**

The content editing URL can be defined in `params.yaml` or Front Matters. The value is the edit url of the repository corresponding to the current directory.

For example, define `repoEditURL: https://github.com/<username>/<repo>/blob/<branch>` in `params.yaml` to display the corresponding link at the bottom of each article.

If you only want to display the content in `content/docs`, you can define `repoEditURL: https://github.com/<username>/<repo>/blob/ <branch>/content/docs` in the Front Matters of `_index.md` of the folder`. Other levels are handled in the same way.

**titleSeparator(string/list)**

Set the separator of the page title. The default value is `|`.

If you only need a single-level separator, enter it as a string. For example, enter `titleSeparator: '-'` and the title of the page will be similar to `Eureka - Tech Mansion`.

If multiple levels of separators are required, enter them as a list. For example, enter `titleSeparator: ['|', '-']` and it will be displayed as `Homepage Configuration - Eureka | Tech Mansion` in titles which requires multiple levels. Others will display as `Eureka | Tech Mansion`.

**dateFormat(string)**

The format of the date displayed on the website. The config should meet the [corresponding format](https://gohugo.io/functions/format/#gos-layout-string) of Golang.

**colorScheme(string)**

The default color scheme of the website. Optional values are `auto`, `light` and `dark`. Leave blank as `auto`.

**siteType(string)**

Site type.

**icon(string)**

Site icon, please refer to [Image Loading](../content-management/#image-loading).

**publisherName(string)**

Publisher name.

**publisherLogo(string)**

Publisher icon, when empty is the site icon.

---

<div class="flex flex-col items-center">
	<span class="mb-4">Please <a href="https://github.com/wangchucheng/hugo-eureka">Star</a> Eureka if you like it!</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>
