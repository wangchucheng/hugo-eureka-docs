---
title: Update Eureka
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

Update Eureka will introduce different ways to update Eureka.

<!--more-->

Currently we can install Eureka in two ways: `Git Submodule` and `Hugo Modules`. Next you will learn how to update Eureka. It should be noted that you can only update in the same way as the installation.

## Update with Git Submodule

> If you have or are willing to install [Go 1.12](https://golang.org/dl/) and above in the current environment, you can [migrate to Hugo Modules](#migrate-from-git-submodule-to-hugo-modules).

Use Git Submodule to update only in the project root directory:

```shell
cd themes/eureka
git checkout <eureka_version>
git pull
```

You can view the historical version of Eureka in [Releases](https://github.com/wangchucheng/hugo-eureka/releases).

## Update with Hugo Modules

When using Hugo Modules to install Eureka, you need [Go 1.12](https://golang.org/dl/) and above. It is recommended that all users who meet the dependency requirements use this method to install.

To use Hugo Modules to update to the latest version of Eureka, you only need to execute it in the project root directory:

```shell
hugo mod get -u
```

If you want to specify a specific version, you just need to execute:

```shell
hugo mod get github.com/wangchucheng/hugo-eureka@<eureka_version>
```

You can view the historical version of Eureka in [Releases](https://github.com/wangchucheng/hugo-eureka/releases).

## Migrate from Git Submodule to Hugo Modules

Because Hugo Modules is more convenient and faster to manage than Git Submodule, and Hugo Modules is Hugo's recommended way to add themes. It is recommended that all users who have or are willing to install [Go 1.12](https://golang.org/dl/) and above in the current environment migrate to Hugo Modules.

### Install Go

To use most of the functions of Hugo Modules, you need to have Go 1.12 and above. You can install it on [Go official website](https://golang.org/dl/).

### Delete Git Submodule

To delete Git Submodule you only need to:

```shell
git submodule deinit -f -- themes/eureka
rm -rf .git/modules/themes/eureka
git rm -f themes/eureka
```

### Initialize Hugo Modules

Initialization of Hugo Modules requires Go 1.12 and above. If you haven't installed Go, please refer to [Install Go](#install-go).

Use the following command to initialize Hugo Modules:

```shell
hugo mod init <module_name>
```

Finally, comment `theme: eureka` in `config/_default/config.yaml` and uncomment `theme: github.com/wangchucheng/hugo-eureka`.

At this point you have completed the migration from Git Submodule to Hugo Modules.

---

<div class="flex flex-col items-center">
	<span class="mb-4">Please <a href="https://github.com/wangchucheng/hugo-eureka">Star</a> Eureka if you like it!</span>
	<a class="github-button" href="https://github.com/wangchucheng/hugo-eureka" data-size="large" aria-label="Star wangchucheng/hugo-eureka on GitHub">Star</a>
</div>