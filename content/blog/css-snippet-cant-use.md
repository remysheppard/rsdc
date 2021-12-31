---
title: "Here's a CSS Snippet That I Can't Use"
description: But nonetheless I'm still very proud of it. Also it's technically SASS, I guess.
author: remy
date: 2021-12-31T17:03:19-05:00
feature: images/css-snippet.jpg
categories:
- Web Development
- CSS
tags:
- Code Snippet
- CSS Snippet
- Code Examples
- SASS
---

```
a {
	color: $r-500;
	text-decoration: none;

	&[href^="http"]:after {
		font: var(--fa-font-thin);
		font-size: $xsmall;
		vertical-align: middle;
		content: "\0020\f08e";
	}

}
```