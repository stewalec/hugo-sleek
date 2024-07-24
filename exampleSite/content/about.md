---
title: About Hugo Sleek
author: Alec Stewart
---

Hugo Sleek is a bare-bones, minimal Hugo theme based off **[XMin](https://github.com/yihui/hugo-xmin)** by [Yihui Xie](https://yihui.org).

It is a simple theme that supports a navigation menu, a home page, other single pages, lists of pages, blog articles, tags, and RSS. That is all. Nothing fancy. CSS has been kept to a minimum and JavaScript has not been included at all. However, JavaScript can easily be introduced through the use of the <a href="https://codeberg.org/stewalec/hugo-sleek/src/branch/master/layouts/partials">`{head,foot}-custom.html`</a> partials. This theme does not contain any images, and is a plain-text theme.

## `hugo.yaml` (the config file)

For the example site, I defined permalinks for two sections, `articles` and `notes`, so that the links to pages under these directories will contain the date info, e.g. This is optional, and it is up to your personal taste of URLs.

```
permalinks:
  notes: "/notes/:year/:month/:day/:slug/"
  articles: "/articles/:year/:month/:day/:slug/"
```

You can define the menus through `menu.main` and `menu.footer`:

```
menu:
  main:
    - name: Home
      url: ""
      weight: 1
    - name: About
      url: "about/"
      weight: 2
    - name: articles
      url: "articles/"
      weight: 3
    - name: Notes
      url: "notes/"
      weight: 4
    - name: Tags
      url: "tags/"
      weight: 5
  footer:
    - name: RSS
      url: "rss"
```

Alternatively, you can add `menu: main` to the YAML metadata of any of your pages, so that these pages will appear in the menu.

The page footer can include an assortment of navigation links. An optional content license can also be included with the text treated as Markdown.

```
params:
  contentLicense: "[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)"
```

## Custom layouts

There are two layout files under `layouts/partials/` that you may want to override: `head_custom.html` and `foot_custom.html`. This is how you inject arbitrary HTML code to the head and foot areas. For example, in the **[XMin](https://github.com/yihui/hugo-xmin)** theme, that site has a file `layouts/partials/foot_custom.html` to support LaTeX math via KaTeX and center images automatically:

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/katex/dist/katex.min.css">
<script src="//cdn.jsdelivr.net/combine/npm/katex/dist/katex.min.js,npm/katex/dist/contrib/auto-render.min.js,npm/@xiee/utils/js/render-katex.js" defer></script>

<script src="//cdn.jsdelivr.net/npm/@xiee/utils/js/center-img.min.js" defer></script>
```

You can enable highlight.js for syntax highlighting by yourself through `head_custom.html` and `foot_custom.html` if you want.

If you do not like the default fonts (e.g., `Palatino`), you may provide your own `static/css/fonts.css` under the root directory of your website to override the `fonts.css` in the theme.

## Other features

Yihui Xie has prepared several examples via pull requests at https://github.com/yihui/hugo-xmin/pulls, so that you can see the implementations of these features when you check out the diffs in the pull requests. For example, you can:

- [Enable Google Analytics](https://github.com/yihui/hugo-xmin/pull/3)

- [Enable Disqus comments](https://github.com/yihui/hugo-xmin/pull/4)

- [Enable highlight.js for syntax highlighting of code blocks](https://github.com/yihui/hugo-xmin/pull/5)

- [Display categories and tags on a page](https://github.com/yihui/hugo-xmin/pull/2)

- [Add a table of contents](https://github.com/yihui/hugo-xmin/pull/7)

- [Add a link in the footer of each page to "Edit this page" on Github](https://github.com/yihui/hugo-xmin/pull/6)

## Final Remarks

I hope you enjoy this adapted theme. The source code is [on Codeberg](https://codeberg.org/stewalec/hugo-sleek). Happy hacking!
