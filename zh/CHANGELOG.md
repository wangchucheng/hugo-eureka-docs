---
title: 更新日志
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: 2020-12-23T15:55:21.000Z
lastmod: 2020-12-23T15:55:21.000Z
draft: false
weight: 7
---

## 0.8.2 (2021-07-09)


### Bug Fixes

* inconsistent utterances color scheme ([9ffd36e](https://github.com/wangchucheng/hugo-eureka/commit/9ffd36e6e03aeafec3a3c0778da0b7bb5b030b73)), closes [#122](https://github.com/wangchucheng/hugo-eureka/issues/122)


## 0.8.1 (2021-07-06)


### Bug Fixes

* cannot switch color scheme without utterances ([ccd5695](https://github.com/wangchucheng/hugo-eureka/commit/ccd5695125f1516db25424dc723eaa9fc6b3e87a))
* incorrect escape character display in summary ([378aad4](https://github.com/wangchucheng/hugo-eureka/commit/378aad4d6f541e6a0b2f9f79cd54315b310f3f72)), closes [#123](https://github.com/wangchucheng/hugo-eureka/issues/123)


### Features

* add Korean i18n support ([#103](https://github.com/wangchucheng/hugo-eureka/issues/103)) ([11ee4a8](https://github.com/wangchucheng/hugo-eureka/commit/11ee4a8b146722582f2dd8600812463f76dd0a21))


## 0.8.0 (2021-04-21)


### Features

* add German i18n support ([#90](https://github.com/wangchucheng/hugo-eureka/issues/90)) ([8d0808e](https://github.com/wangchucheng/hugo-eureka/commit/8d0808eb8d3cc0464794de9f88d0b2e8995f4efa))
* add polish i18n support ([#95](https://github.com/wangchucheng/hugo-eureka/issues/95)) ([177e4b1](https://github.com/wangchucheng/hugo-eureka/commit/177e4b19c294652a163cf93d35fdc5ae91acf3e3))
* add russian i18n support ([#87](https://github.com/wangchucheng/hugo-eureka/issues/87)) ([b5396e8](https://github.com/wangchucheng/hugo-eureka/commit/b5396e81a11d983b519c2bc1042c120582743244))
* add utterances support ([d07e103](https://github.com/wangchucheng/hugo-eureka/commit/d07e1032454d90d3282e6d5caa5899a244e59ec6))
* recursive enableComment param ([ebf560f](https://github.com/wangchucheng/hugo-eureka/commit/ebf560f9f484c5027a5fc9f418510d363a6bed3e))
* recursive repoEditURL ([285eb0f](https://github.com/wangchucheng/hugo-eureka/commit/285eb0f5e27f97b8eeddff251204bbdeed17564d))
* support Valine ([#79](https://github.com/wangchucheng/hugo-eureka/issues/79)) ([1762613](https://github.com/wangchucheng/hugo-eureka/commit/1762613dfb06a9f2fb0958b4550234ea7193b772))


## 0.7.0 (2021-04-03)


### Bug Fixes

* make KaTeX options case sensitive ([4b0bb03](https://github.com/wangchucheng/hugo-eureka/commit/4b0bb031102826fccf891a648f44713636f33dd0))


### Features

* add mermaid support ([296ed03](https://github.com/wangchucheng/hugo-eureka/commit/296ed03bc593a54af0eec50c7d4e4b63b7d0ac69)), closes [#26](https://github.com/wangchucheng/hugo-eureka/issues/26)


## 0.6.0 (2021-03-12)


### Bug Fixes

* fix render error when scale is null ([9fcd389](https://github.com/wangchucheng/hugo-eureka/commit/9fcd3891b1c27a73e29490cc050c85452178b837))
* KaTeX formula overflow ([c6c7aa2](https://github.com/wangchucheng/hugo-eureka/commit/c6c7aa2688a00918ec70f7387273e85761a08e90)), closes [#62](https://github.com/wangchucheng/hugo-eureka/issues/62)
* markdown render error for experiences writeup ([#44](https://github.com/wangchucheng/hugo-eureka/issues/44)) ([4934fb9](https://github.com/wangchucheng/hugo-eureka/commit/4934fb902d29de68daa6c3e4d6f607a23ebf5445))
* unable to change highlightjs style ([#66](https://github.com/wangchucheng/hugo-eureka/issues/66)) ([4f4c844](https://github.com/wangchucheng/hugo-eureka/commit/4f4c8443a391b4933a019a0940c8f8b86d93101e))


### Features

* add custom highlightjs languages ([01a9ea3](https://github.com/wangchucheng/hugo-eureka/commit/01a9ea34ab121f7210a306a4bbc125c5e84e73aa))
* add experiences widget ([#37](https://github.com/wangchucheng/hugo-eureka/issues/37)) ([26dde52](https://github.com/wangchucheng/hugo-eureka/commit/26dde5274fb57dad6445bc2eeb4937865512070a)), closes [#35](https://github.com/wangchucheng/hugo-eureka/issues/35)
* add markdownify to about front matter ([#33](https://github.com/wangchucheng/hugo-eureka/issues/33)) ([13d24ae](https://github.com/wangchucheng/hugo-eureka/commit/13d24aee7a87924442254f0efc7011630054ba14))


## 0.5.0 (2021-01-21)


### Bug Fixes

* readMore link ([4b342eb](https://github.com/wangchucheng/hugo-eureka/commit/4b342ebeba8aeccc95cde1845bab3019871e16eb)), closes [#28](https://github.com/wangchucheng/hugo-eureka/issues/28)
* schema context url ([8252316](https://github.com/wangchucheng/hugo-eureka/commit/825231682ad8640986f214a05535f0d56a6b1616))


## 0.4.0 (2020-12-27)


### Bug Fixes

* postcss version problem ([6a39f3a](https://github.com/wangchucheng/hugo-eureka/commit/6a39f3acf6f9d98ee0ba73b20be711838b85d68e))


### Features

* widget system for configuring homepage ([c33985a](https://github.com/wangchucheng/hugo-eureka/commit/c33985a935b5bf5706bed27bc112f700df2f2903)), closes [#11](https://github.com/wangchucheng/hugo-eureka/issues/11)


### BREAKING CHANGES

* Param 'hero' in params.toml is deprecated.
* Param 'icon_pack' in %q is deprecated. Use 'iconPack'.
* 'doc_list' in doc layout is deprecated. Use 'doc-list'.


## 0.3.1 (2020-12-17)


### Bug Fixes

* 404 top margin ([5c8e0b6](https://github.com/wangchucheng/hugo-eureka/commit/5c8e0b6c72d45d4f76979d4b9de14f8fa58e3b7a))
* empty featured placeholder ([8f5a4d0](https://github.com/wangchucheng/hugo-eureka/commit/8f5a4d0c1aed9935e18fb0c5861cb3500d48d6a7))



## 0.3.0 (2020-12-15)


### Bug Fixes

* jumping scrollbar ([6638e3a](https://github.com/wangchucheng/hugo-eureka/commit/6638e3a102cb8e678dfed77c926f2498cc05d583)), closes [#14](https://github.com/wangchucheng/hugo-eureka/issues/14)


### Features

* customize title separator ([69af104](https://github.com/wangchucheng/hugo-eureka/commit/69af104e562b4a2d86aff01cb9187f64a475f948))
* featured video ([f1e1ec9](https://github.com/wangchucheng/hugo-eureka/commit/f1e1ec9f79295532a85b59c075e2ebac55951bd7)), closes [#15](https://github.com/wangchucheng/hugo-eureka/issues/15)



## 0.2.1 (2020-11-27)


### Bug Fixes

* external images in config params ([e943060](https://github.com/wangchucheng/hugo-eureka/commit/e943060162dc4a3e91be78a060b0af185476ad7d))
* images cannot be named freely ([d998e9f](https://github.com/wangchucheng/hugo-eureka/commit/d998e9fa89455ac70270cb81ae7d6dded8e4e7db)), closes [#13](https://github.com/wangchucheng/hugo-eureka/issues/13)



## 0.2.0 (2020-11-21)


### Bug Fixes

* fix open graph image ([070255a](https://github.com/wangchucheng/hugo-eureka/commit/070255abb183f176b8380847692984ec14f13ef0))
* title link error on themes.gohugo.io ([18467c0](https://github.com/wangchucheng/hugo-eureka/commit/18467c04ead1ac90b894b02e49af15e5be15af68))
* toc auto scroll ([96741f4](https://github.com/wangchucheng/hugo-eureka/commit/96741f4b4da8079b96e9c7d342b0b03235f4654b))


### Features

* customize default color scheme ([1fc544b](https://github.com/wangchucheng/hugo-eureka/commit/1fc544b7cd8c578f4fc9daf810e42761b7a1e8c5))
* KaTeX support ([b346260](https://github.com/wangchucheng/hugo-eureka/commit/b346260f352021a98e9596b2e2c404c25c5887bd)), closes [#9](https://github.com/wangchucheng/hugo-eureka/issues/9)



## 0.1.3 (2020-11-07)



## 0.1.2 (2020-10-31)


### Bug Fixes

* use .url in post author ([351905a](https://github.com/wangchucheng/hugo-eureka/commit/351905a42dd6bb1bb81bb5ba00d4ad6be1c50db4))


### Features

* add docs version management ([bc71391](https://github.com/wangchucheng/hugo-eureka/commit/bc71391e3a875dc7277795b0622f4979afa5ba41))
* customize date format ([302dff7](https://github.com/wangchucheng/hugo-eureka/commit/302dff7ff41563b572aae21a0abd6ccb0e96a42f))



## 0.1.1 (2020-10-24)


### Bug Fixes

* inaccurate description meta in docs type ([d62797b](https://github.com/wangchucheng/hugo-eureka/commit/d62797b070b36182bbf83a88f8ac4229cd4880d9))


### Code Refactoring

* deprecate .link in author's social param ([b3a547b](https://github.com/wangchucheng/hugo-eureka/commit/b3a547bae35955aa64b2a21f803e40695cb4fa13))


### BREAKING CHANGES

* deprecate .link in author's social param. Use .url instead.

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>