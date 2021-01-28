---
title: Customize Eureka
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

In [Content Management](../content-management), you have already learned about all kinds of content of Eureka. Next, we will introduce Eureka's customization options. Customize Eureka will lead you to understand how Eureka is configured and its options.

<!--more-->

## Navigation Bar

You can define the content of the web page navigation bar simply and quickly. In `config/_default/menus.toml`, there are multiple `main` modules, just modify them according to the content in the sample file. For example, adding the archive page in the navigation bar only needs to add the following content:

```yaml
main:
  - name: Archive
    url: /archive/
    weight: 40
```

It should be noted that the order of the navigation bar is in ascending order of the size of `weight`.

## Math

Eureka supports the use of KaTeX to render LaTeX mathematical formulas. If you need to configure KaTeX, you only need to configure the `[math]` in `config/_default/params.toml`.

**math.handler(string)**

The optional value is katex, leave it blank to disable this feature.

**math.katex(object)**

KaTeX related configuration. For specific optional values, please refer to: [Options · KaTeX](https://katex.org/docs/options.html). Since Eureka uses KaTeX's auto-render extension, the `displayMode` property in the link will be ignored.

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

You can set the value of the `math` attribute in the Front Matter of the file in any level, which will affect this page or all pages under this section. The priority is Page > Section > Site. For example, if I set `math = fasle` in Front Matter of `nested-doc` and set `math = true` in Front Matter of `nested-content-1.md`, it will make `nested-content-1.md` render math formulas. Formulas in other files under the `nested-doc` folder will not be rendered.

## Comment

Currently Eureka supports two types of comment systems, Disqus and Commento. To activate the comment system, just modify the content related to `[comment]` in `config/_default/params.toml`. Take Disqus as an example, if you need to activate Disqus, you only need to modify the content as follows:

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

## Basic Config File

Some basic configurations are defined in `config/_default/config.toml` to help you set up some basic functions of the website. This chapter will not cover the content already contained in the previous article.

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

**repoURL(string)**

Project repository URL.

**repoEditURL(string)**

Edit the URL of the current page content, if the project repository is on Github, it can be empty.

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