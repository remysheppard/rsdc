---
title: "Here's a CSS Snippet That I Can't Use"
description: But nonetheless I'm still very proud of it. Also it's technically SASS, I guess.
author: remy
date: 2021-12-31T17:03:19-05:00
images: 
- images/css-snippet.jpg
categories:
- Web Development
- CSS
tags:
- Code Snippet
- CSS Snippet
- Code Examples
- SASS
---

I wrote this little neat bit of CSS to handle adding the [Font Awesome "Arrow Up Right From Square" Icon](https://fontawesome.com/v6.0/icons/arrow-up-right-from-square?s=thin) to all outbound links.

```scss
a {
	color: lightred;
	text-decoration: none;

	&[href^="http"]:after {
		font: var(--fa-font-thin);
		font-size: $xsmall;
		vertical-align: middle;
		content: "\0020\f08e";
	}
}
```

It worked well enough. It grabs any link that has a `href` that starts with `http`. In itself, that's honestly kind of indiscriminate and perhaps a bit too general. I applied it to root level `a` tags in my stylesheet and it worked like a charm. The only problem was when internal links were specified absolutely instead of relatively.

Then it also added to my social links.

I could have increased the specificity of the tag, or perhaps narrowed the scope by writing it as something like:

```css
section.main-content a, aside.sidebar a {
	...
}
```

But that was a lot of work.

I was already using Hugo's [Markdown Render Hooks](https://gohugo.io/getting-started/configuration-markup#markdown-render-hooks) to modify hugo's default, outbound link behavior.

You see, I wanted outbound links to add `target="_blank"` automatically but I didn't want to create a shortcode or have to do anything other than use the started markdown link format.

I wanted the computer to do all the work. I just want to write.

So I popped open that file because I thought, *Well, while I'm in here doing the one thing I may as well do the other.*

So now I have a file `layouts -> _default -> _markup` called `render-link.html` that looks like this:

```go
<a 
	href="{{ .Destination | safeURL }}" 
	{{ with .Title }}title="{{ . }}" {{ end }}
	{{ if strings.HasPrefix .Destination "http" }}
		target="_blank" rel="noopener"
	{{ end }}
>
	{{ .Text | safeHTML }}
</a>
{{ if strings.HasPrefix .Destination "http" }}
	&nbsp;<i class="fa-thin fa-arrow-up-right-from-square fa-fw fa-xs"></i>
{{ end }}
```

So I'm intercepting Goldmark's rendering engine and replacing their link rendering with my own that checks if the link is outbound (via a `http` prefix, as all internal links are relativized). If it is an outbound link, I add `target="_blank"` to the internal link, and I add `&nbsp;<i class="fa-thin fa-arrow-up-right-from-square fa-fw fa-xs"></i>` outside of the link to render the little outbound indicator.

I'm not sure how other people handle this, but this is the easiest and most elegant solution I've found. 

Let me know.