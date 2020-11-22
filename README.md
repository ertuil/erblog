# Erblog

> ⚠️⚠️⚠️ **Note:** Mathjax is not included directly due to the performance considerations now! 
>
> Use `math: true` in Front Matter to enable Mathjax in each single page.
>
> Or set `Params.math: true` to enable it globally.

A personal blog theme powered by [Hugo](https://gohugo.io).
Erblog is written by Ertuil with [layui.js](https://www.layui.com), [font-awssome](https://fontawesome.com), github markdown css and [undraw](https://undraw.co).

![images/screenshot.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/screenshot.png)

> Erblog is also a responsive theme which means it is customed for your mobile platforms. 

<img src="https://raw.githubusercontent.com/ertuil/erblog/master/images/mobile.png" width="400px" alt="images/mobile.png"/>


> Now it is possible to change the color of your themes. Use `Params.badge` and `Params.quote` to select one of your favourite color.


| Some Pictures | |
| ---- | ----------- |
| ![images/color1.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/color1.png) | ![images/color2.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/color2.png) |
| ![images/color3.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/color3.png) | ![images/list.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/list.png) | 
| ![images/single.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/single.png) | ![images/zone.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/zone.png) |

## 1. Installation

You can install the theme by git clone.

```
$ git submodule add https://github.com/ertuil/erblog themes/erblog
$ git submodule init
$ git submodule update
```

Now you can get updates to Erblog in the future by updating the submodule:

```
$ git submodule update --remote themes/erblog
```

> [@progressify](https://github.com/progressify) contributed a new style for scrollbar. You can check out the branch called [https://github.com/ertuil/erblog/tree/styled-scrollbar](https://github.com/ertuil/erblog/tree/styled-scrollbar) to use. Here is an example:
> [https://progressify.dev](https://progressify.dev)
> Thanks to his contribution.

## 2. Configuration

There are some basic configuration options you may want to use:

| Name | Description | Default |
| ---- | ---- | ---- |
| title | Name of your website | None |
| googleAnalytics | Google Analytics ID| None |
| Params.portrait | Path to your portrait | erblog/static/self/img/avatar.jpg |
| Params.author | Your Name | Authors |
| Params.description | Description of your Blog | Intro |
| Params.bio | A Biography for your Blog | None |
| Params.logo | Your Blog's Logo | None |
| Params.favicon | The favicon file | /favicon.ico |
| Params.math | import mathjax globally | false |
| Params.index_posts_num | The number of posts displayed in Index | 5 | 
| Params.google_search | Enable Google Intra-Site Search Engine | false | 
| Params.badge | The color for badge ('red', 'cyan', 'orange', 'green', 'blue', 'black' and 'gray' are available) | 'red' |
| Params.quote | The color for quota ('red', 'cyan', 'orange', 'green', 'blue', 'black' and 'gray' are available) | 'green' |
| Params.notice | Contents of notification | none |
| Params.notice_color | The color for notification background ('red', 'cyan', 'orange', 'green', 'blue', 'black' and 'gray' are available) | 'red' |

Add your own custom menus in the `config.toml` like this:

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

A Menu in the footer is also available:

```
[[menu.footer]]
    identifier = "home"
    name = "home"
    url = "/"
    weight = 1

[[menu.footer]]
    identifier = "about"
    name = "About"
    url = "/about/"
    weight = 2
```

Now you can add your contacts like this:

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

For more details, see the example site.

## 3. Content Management

### 3.1 Posts

There are three basic sections, 'post', 'zone' and 'gallery'. You may create a new post using the following command:

```
hugo new post/post_name.md
```

### 3.2 Zone

A section like facebook

![images/zone.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/zone.png)

```
hugo new zone/example.md
```

### 3.3 Gallery

Gallery is a simple collection for your photos.

![images/gallery.png](https://raw.githubusercontent.com/ertuil/erblog/master/images/gallery.png)

```
hugo new gallery/gallery_name.md
```

You can upload your files to the `/static` directory and write the contents in `gallery_name.md`:

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

### 3.4 Add a Zone and Gallery to the Menu

Add the following content to your `config.toml` file:

```toml
[[menu.main]]
    url = "/zone/"
    name = "Zone"
    weight = 1

[[menu.main]]
    url = "/gallery/"
    name = "Gallery"
    weight = 2
```

## 4. User-Defined HTML Hooks

There are two hooks available for you to insert your HTML code.

1. `layouts/partials/self-define.html` renders content **above the footer for every page**.
2. `layouts/partials/self-define-single.html` renders content **above the footer for every blog post**. This hook is useful to define your *comment modules*, such as gittalk, and Disqus.

### 4.1 Using Hooks to Add Discus Comments

Add Discus comments to the bottom of each post by inserting the following in the `layouts/partials/self-define-single.html` hook.

```
{{ template "_internal/disqus.html" . }}
```

For this to work you will also need to define the `disqusShortName` in your `config.toml`:

``` toml
disqusShortName = "your-disqus-shortname"
```
