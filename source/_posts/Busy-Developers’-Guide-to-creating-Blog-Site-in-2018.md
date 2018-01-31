---
title: Busy Developers’ Guide to creating Blog Site in 2018
date: 2018-01-31 01:03:21
tags: ["blog","deployment"]
---

[Hexo](https://hexo.io/) is a fast, simple & powerful blog framework

[Github Pages](https://pages.github.com/) offer free websites for you and your projects. Hosted directly from your GitHub repository.

This blog post attempts to provide simple guide to get started with [Hexo](https://hexo.io/) and [Github Pages](https://pages.github.com/)

## Install Hexo

```
npm install -g hexo-cli
```

![npm makes it possible and really easy to get hexo](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/hexo-install.gif)

## Create a project for your Github Pages

```
hexo init <username>.github.io
```

![initialize your blog site with hexo init](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/hexo-init.gif)

and cd to the new directory

```
cd <username>.github.io
```

## Initialize git repo

```
git init . && git add . && git commit -am 'first commit'
```

![initialize git repository](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/git-init.gif)

and create a new branch for your repo

```
git checkout -b develop
```

![create a separate branch for your site code](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/git-branch.gif)

<details>
 <summary>Pro Tip: Github Pages use <b>master branch</b> from your repo</summary>

* your blogsite exists on `https://<username>.github.io`
* git repository for your site exists on https://github.com/&lt;username&gt;/&lt;username&gt;.github.io.git

* github will autiomatically pull all static files **from master branch** from your repo and deploy it to your site
  </details>

## Configure your site

You can edit `_config.yml` file at root of repo to configure Hexo. Here is a summary of bare mimimum options you should configure:

```
title: <username>
description: yet another blog site
author: <username>
url: https://<username>.github.io
```

## Preview your site

```
hexo server
```

![hexo-server let's you preview your site](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/hexo-server.gif)

And navigate to http://localhost:4000

![default hexo site](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/hexo-default-site.png)

## Setup deployment to Github Pages

```
npm install hexo-deployer-git --save
```

![hexo-deployer-git makes it trivial to deploy your site](/Busy-Developers’-Guide-to-creating-Blog-Site-in-2018/hexo-deployer-git.gif)

and add necessary config to `_config.yml`

```
deploy:
  type: git
  repo: https://github.com/<username>/<username>.github.io.git
  branch: master
```

## Deploy your site

```
hexo clean
hexo deploy
```

Hurray, your site should now be available on https://&lt;username&gt;.github.io
