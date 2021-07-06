---
title: 更新Eureka
description: ''
summary: ''
toc: true
authors: []
tags: []
categories: []
series: []
date: '2020-10-21T23:58:12+08:00'
lastmod: '2020-10-21T23:58:12+08:00'
draft: false
weight: 6
aliases:
  - update-eureka
---

本文将介绍通过不同方式更新Eureka的方法。

<!--more-->

>	如果你的区域存在难以访问GitHub的问题，你可以将所有涉及到GitHub的网址替换为[Gitee镜像](https://gitee.com/wangchucheng/hugo-eureka/)。例如将`https://github.com/wangchucheng/hugo-eureka/`替换为`https://gitee.com/wangchucheng/hugo-eureka/`即可。

目前我们可以通过`Git Submodules`和`Hugo Modules`两种方式安装Eureka。接下来你将了解到如何更新Eureka。需要注意的是，你只能通过与安装相同的方式进行更新。

## 使用Git Submodules更新

> 如果当前环境下拥有或愿意安装[Go 1.12](https://golang.org/dl/)及以上版本，可以[迁移至Hugo Modules](#由git-submodules迁移至hugo-modules)。

使用Git Submodules更新只需在项目根目录下执行：

```shell
cd themes/eureka
git checkout <eureka_version>
git pull
```

Eureka的历史版本你可以在[Releases](https://github.com/wangchucheng/hugo-eureka/releases)中进行查看。

## 使用Hugo Modules更新

使用Hugo Modules安装Eureka时需要[Go 1.12](https://golang.org/dl/)及以上版本，推荐所有满足依赖要求的用户使用此方式进行安装。

使用Hugo Modules更新到Eureka最新版本只需在项目根目录下执行：

```shell
hugo mod get -u
```

如果你想指定特定版本，你只需执行：

```shell
hugo mod get github.com/wangchucheng/hugo-eureka@<eureka_version>
```

Eureka的历史版本你可以在[Releases](https://github.com/wangchucheng/hugo-eureka/releases)中进行查看。

## 由Git Submodules迁移至Hugo Modules

由于Hugo Modules在管理上比Git Submodules更为方便快捷且Hugo Modules为Hugo推荐的添加主题的方式。推荐所有在当前环境下拥有或愿意安装[Go 1.12](https://golang.org/dl/)及以上版本的用户迁移至Hugo Modules。

### 安装Go

如需使用Hugo Modules的绝大部分功能，你需要拥有Go 1.12及以上版本。可以在[Go官网](https://golang.org/dl/)进行安装。

### 删除Git Submodules

删除Git Submodules你只需：

```shell
git submodule deinit -f -- themes/eureka
rm -rf .git/modules/themes/eureka
git rm -f themes/eureka
```

### 初始化Hugo Modules

初始化Hugo Modules需要拥有Go 1.12及以上版本。如你还未安装Go，可参考[安装Go](#安装go)。

使用以下命令可初始化Hugo Modules：

```shell
hugo mod init <module_name>
```

最后将`config/_default/config.yaml`中的`theme: eureka`注释并将`theme: github.com/wangchucheng/hugo-eureka`取消注释。

这时你已经完成了由Git Submodules到Hugo Modules的迁移。

---

<div class="flex flex-col items-center">
	<span class="mb-4">喜欢Eureka就请点个<a href="https://github.com/wangchucheng/hugo-eureka">Star</a>吧！</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>