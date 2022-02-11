---
title: Multilingual Mode
description: ""
summary: ""
toc: true
authors: []
tags: []
categories: []
series: []
date: "2020-10-21T23:11:23+08:00"
lastmod: "2020-10-21T23:11:23+08:00"
draft: false
weight: 5
---

In addition to [Content Management](content-management) and [Customize Eureka](customization) described above, Eureka also supports Multilingual Mode. Multilingual Mode will lead you to understand how to build a multilingual site.

<!--more-->

## Multilingual Config

First we need to make some modifications to the configuration file to use the multilingual mode.

Uncomment the commented content in `config/_default/languages.yaml`. Specifically, for the `contentDir` property of the default language, uncomment it and move all the contents in the original `content` folder to the `content/<language_code>/` folder.

Next, uncomment the configuration of other languages, where you can modify the value of a specific configuration property, just like the `title` in the example.

After that, we need to continue to modify the relevant content of the navigation bar. First, please create a new `menus.<language_code>.yaml` file in the `config/_default/` folder, and copy the content in `menus.yaml` and make corresponding settings.

Finally, there are some `i18n` strings in Eureka. The languages currently officially supported by Eureka are:

- Simplified Chinese
- English

Languages provided by the community:

- Traditional Chinese
- Arabic
- French
- German
- Italian
- Japanese
- Korean
- Polish
- Portuguese
- Russian
- Spanish

If you need translations in other languages, you can copy the [i18n](https://github.com/wangchucheng/hugo-eureka/tree/master/i18n) folder to the project In the root directory, add your language translation based on the content in it, and name it with the corresponding language code.

We also welcome users to provide us with translations in other languages. You can submit the corresponding [Pull Request](https://github.com/wangchucheng/hugo-eureka/pulls) to us.

So far we have completed the multilingual mode configuration.

## Multilingual Content

In the previous step, I believe you have moved the contents of the `content` folder to the `content/<language_code>/` folder. Multilingual content is similar to [Content Management](../content-management), but the way to create new content is different. Next, I will introduce how to create new content in a multilingual website.

In a single language, we only need to use the following commands to create a new file:

```shell
hugo new posts/<your_post.md>
```

In the case of multiple languages, it will be generated in a certain language. If you want to specify the generated language location, you can use the following method:

```shell
hugo new content/<language_code>/posts/<your_post.md>
```

It should be noted that the path must start with `content`.

---

<div class="flex flex-col items-center">
	<span class="mb-4">Please <a href="https://github.com/wangchucheng/hugo-eureka">Star</a> Eureka if you like it!</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>
