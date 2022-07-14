---
title: Related Posts in Hugo
description: In this post I will show you how a built a shortcode that does related posts for Hugo, which is nifty.
author: remy
date: 2022-02-12T13:26:14.589Z
tags:
  - Hugo
  - HTML
  - Netlify
  - CI/CD
categories:
  - Hugo
  - Web Development
---

One of the cooler things WordPress lets you do - probably because of fancy computer words like "relational database" - is let you insert "Related Content" right in the middle of your current post.

Internet marketers frequently will link to, "something else you might like" right in the middle of the thing you're reading. I've even seen news services doing it!

Anyway, Hugo can't just do that. So I built a short code that sort of can, as long as you know where you want to go.

```html
{{ with .Get 0 }}
{{ $link :=  printf "/blog/%s/index.md" . }}
  <aside class="read-also">
    <i class="fa-light fa-lightbulb-on fa-fw fa-xl"></i>
    <strong style="padding-left:1rem">You Might also Like:</strong>
    &nbsp;
    {{ with $.Site.GetPage $link }}
      <a href="{{ .RelPermalink }}">
        {{ .Title }}
      </a>
    {{ end }}
  </aside>
{{ end }}
```