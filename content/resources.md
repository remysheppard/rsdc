---
title: Resources
layout: resources
type: about
description: The tools and processes I use to keep this ship afloat.
author: remy
date: 2021-12-31T17:03:19-05:00
images: 
  - images/resources-header.jpg
---

On this page you're going to find the tools and technology I use to keep this website running.

### Static Site Generator
##### [Hugo](https://www.gohugo.io)

I don't know if you know this: But this website is just plain HTML. I create a series of templates and content files that reference each other as GoLang objects (essentially) and then a piece of software called *Hugo* runs and in 0.748s (most recent build time) compiles everything together and spits out a plain HTML website.

You can learn more about the JAMstack [here](https://www.jamstack.org).

### "Hosting"
#### [GitHub](https://www.github.com)

Traditional hosting is kind of dead anymore, I think? I mean, I'm sure people out there are still using HostGator, or whatever, but with the advent of cloud architecture and serverless structures, technologies like Docker, etc. I don't know, man, I just don't see people paying for traditional hosting.

This website is technically a *Git repo* (which you can view [here](https://github.com/bootyocean18/rsdc), if you want). So in that sense, it is "hosted" on GitHub. But the magic happens when the website is compiled and deployed.

### CI/CD
#### [Netlify](https://www.netlify.com)

For the real back-end Heavy Lifting™ I use Netlify. Netlify handles building and deploying my website for me. Basically, if you're new to this: I push an update to a content file (say, the stuff on this page). That update gets logged in my Git Repo. 

Netlify notices that my Git repo has updated and pulls those files. It then runs Hugo in a dockerized container and builds the HTML output.

Then Netlify hosts those html files on their global, super fast CDN, and links my domain there. That way, when you visit my website, you hit the nearest CDN node and get served up the most recent HTML build of my website.

Nifty.

### Analytics
##### [Fathom](https://usefathom.com/ref/JHDRUD)

For Analytics I use Fathom, because they don't actually track you. They just let me know if folks are actually getting here. Good stuff.

Unlike Google Analytics, I actually *pay* for Fathom, which means that **you** aren't the product, *Fathom is*. Fathom is completely compliant with all privacy legislation globally because none of your data is ever actually stored anywhere.

Fathom doesn't track you across the web, and I have no idea how many other websites that you visit in a day use Fathom. None of your information is ever stored anywhere so it can never be sold to anyone, or made available to any party - including myself, Fathom, or anyone else.

If you would like to use Fathom on your own website, consider using [my affiliate link](https://usefathom.com/ref/JHDRUD). You get $10 off your first month, and I get 10% of your purchase price (100% of Fathom affiliate proceeds goes to support my cats).