---
title: Getting Started
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: '2020-10-19T22:50:23+08:00'
lastmod: '2020-10-19T22:50:23+08:00'
draft: false
weight: 1
---

In Getting Started you will learn how to quickly build a Hugo site with Eureka.

<!--more-->

## Prerequisites

To use Eureka normally, you need to install the following:

- [Git](https://git-scm.com/)
- [Hugo v0.74.0+](https://gohugo.io/getting-started/installing/)
- [Go 1.12+](https://golang.org/dl/) (When installing with Hugo Modules)

## Quick Installation

Eureka can be quickly installed by using the Github Template [Hugo Eureka Starters](https://github.com/wangchucheng/hugo-eureka-starters).

When using this method, please click the `Use this template` button on the page and set your repository information.

If you want to install with Hugo Modules, just click the `Create repository from template` button after entering the information.

If you want to install with Git Submodules, please check the `Include all branches` option after entering the information, and then click the `Create repository from template` button. After the repository is created, set the default branch to the `git-submodules` branch.

## Manual Installation

Eureka can be quickly integrated into the Hugo project. Currently, Eureka can be installed in two ways: [Git Submodules](#install-with-git-submodules) and [Hugo Modules](#install-with-hugo-modules).

### Install with Git Submodules

> If you have or are willing to install [Go 1.12](https://golang.org/dl/) or above in the current environment, you can use the more convenient and quick [Hugo Modules](#install-with-hugo-modules) installation.

When installing with Git Submodules, you only need to execute under the project location:

```shell
git submodule add https://github.com/wangchucheng/hugo-eureka.git themes/eureka
```

The default content at this time is the main branch. We recommend to use versions in [Releases](https://github.com/wangchucheng/hugo-eureka/releases), as the main branch may contain unstable features or even errors. To checkout versions, you only need to:

```shell
cd themes/eureka
git checkout <eureka_version>
```

Next, copy the `config` folder in [exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite) to the project root directory, and check the contents of the `config` folder and configure it. After configuration, delete the original `config.toml` file.

If you create a new Hugo project, the `content` folder is blank in default. You can copy the `content` folder in [exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite) to the project root directory to preview.

After completing the above steps, use the following command to preview the project in the browser:

```shell
hugo server
```

Drafts will not be deployed by Hugo, so you need to set the `draft` property of the content header to `false` or use `hugo server -D` to preview the site.

If you are not familiar with the basic usage of Hugo or want to know more about Hugo, you can refer to [Hugo Basic Usage](https://gohugo.io/getting-started/usage/).

### Install with Hugo Modules

When using Hugo Modules to install Eureka, you need [Go 1.12](https://golang.org/dl/) and above. It is recommended that all users who meet the dependency requirements use this method to install.

First, initialize a new Hugo Module in the project root directory:

```shell
hugo mod init <module_name>
```

Next, copy the `config` folder in [exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite) to the project root directory, and check the contents of the `config` folder and configure it.

Finally, comment `theme: eureka` in `config/_default/config.yaml` and uncomment `theme: github.com/wangchucheng/hugo-eureka`. After configuration, delete the original `config.toml` file.

If you create a new Hugo project, the `content` folder is blank in default. You can copy the `content` folder in [exampleSite](https://github.com/wangchucheng/hugo-eureka/tree/master/exampleSite) to the project root directory to preview.

After completing the above steps, use the following command to preview the project in the browser:

```shell
hugo server
```

Drafts will not be deployed by Hugo, so you need to set the `draft` property of the content header to `false` or use `hugo server -D` to preview the website.

If you are not familiar with the basic usage of Hugo or want to know more about Hugo, you can refer to [Hugo Basic Usage](https://gohugo.io/getting-started/usage/).

## Add Content

After installing Eureka, you can start adding content to the website. You can manually create files and add information in the `content` folder. At the same time, you can also use `hugo new` to complete the above content for you.

Add a default type of content to the project:

```shell
hugo new posts/hello-world.md
```

This will help you generate a file with the following content in the `content/post` folder.

```yaml
---
title: Hello World
description:
toc: true
authors: []
tags: []
categories: []
series: []
date: '2020-10-20T10:30:48+08:00'
lastmod: '2020-10-20T10:30:48+08:00'
featuredImage: ''
draft: false
---
```

You can modify the value or start writing your body content after the `+++` at the end of the file.

Eureka also provides you with other types of templates, you can specify the type with `-k KIND`:

```shell
hugo new -k authors authors/new-author
```

This will generate author-type content in the `content/authors` folder.

For all content types provided by Eureka, please refer to [archetypes](https://github.com/wangchucheng/hugo-eureka/tree/master/archetypes).

## Change Configuration

Since Eureka is committed to providing a highly customizable and feature-rich theme, we replaced the automatically generated `config.toml` file with the `config` folder to provide a clearer structure. You can modify any content in the configuration file:

```yaml
title: My Own Title
```

For the relevant configuration of the homepage, please refer to [Homepage Configuration](../homepage-configuration)。

## Generate Site

To generate a site, you need to:

```shell
hugo
```

Similar to `hugo server`, `hugo` will not generate draft content. The generated web page is located in the `public` folder. You can deploy it on static web deployment platforms such as Github Pages or Netlify.

---

<div class="flex flex-col items-center">
	<span class="mb-4">Please <a href="https://github.com/wangchucheng/hugo-eureka">Star</a> Eureka if you like it!</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>