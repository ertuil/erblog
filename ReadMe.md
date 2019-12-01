# Erblog

A personal blog theme powered by [Hugo](https://gohugo.io).
Erblog is written by Ertuil with [layui.js](https://www.layui.com), [font-awssome](https://fontawesome.com) and [undraw](https://undraw.co).

## Installation

You can install the theme by git clone.

```
$ git submodule add https://github.com/ertuil/erblog themes/erblog
$ git submodule init
$ git submodule update
```

Now you can get updates to Erblog in the future by updating the submodule:

```
$ git submodule update --remote themes/minimal
```

## Configuration

There are some basic configuration options you may want to use:

| Name | Description | Default |
| ---- | ---- | ---- |
| title | Name of your website | None |
| googleAnalytics | Google Analytics ID| None |
| Params.portrait | The protrait file | erblog/static/self/img/avater.jpg |
| Params.author | Your Name | None |
| Params.description | A simple description | None |
| Params.bio | Your biological description | None |
| Params.favicon | The favicon file | "/favicon.ico" |

Alse you can add your own custom menus in `config.toml` like this:

```
[[menu.main]]
    url = "/home/"
    name = "Files"
    weight = 6

[[menu.main]]
    url = "/dl/"
    name = "Download"
    weight = 7
```

None you add add your contacts like this:

```
# Social icons to be shown on the right-hand side of the navigation bar
# The "name" field should match the name of the icon to be used
# The list of available icons can be found at http://fontawesome.io/icons/

[[menu.icon]]
    url = "mailto:me@xxx.com"
    name = "envelope-o"
    weight = 1

[[menu.icon]]
    url = "https://github.com/username/"
    name = "github"
    weight = 1

[[menu.icon]]
    url = "https://twitter.com/username"
    name = "twitter"
    weight = 1

[[menu.icon]]
    url = "https://www.instagram.com/username/"
    name = "instagram"
    weight = 1
```

## Content Management

There are two basic sections, 'post' and 'gallery'. You may create a new post using the following command:

```
hugo new post/post_name.md
```

Gallery is a simple collection for your photos.

```
hugo new gallery/gallery_name.md
```

You can upload your files to `/static` directory and write these contents in `gallery_name.md`:

```
---
title: "A gallery"
date: 2019-12-01T13:21:53+08:00
draft: false
---

![0](/avater.jpg)
![1](/people/1.png)
![2](/people/2.png)
![3](/people/3.png)
```