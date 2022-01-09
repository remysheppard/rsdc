---
title: "Content Atomization"
date: 2022-01-08T09:00:00-05:00
description: A quick tidbit about keeping your content as atomized as possible, and why it's better to lego-brick it together.
author: remy
images:
  - feature.jpg
categories:
  - Web Dev
tags:
  - Hugo
  - Content Strategy
  - Organization
  - Web Development
---
I recently started the project of rebuilding [my cat's blog](https://www.gabbythetabby.com) on Hugo. Which has been a fun and interesting challenge. I've started looking at how people interact with content on mobile devices and as a result I'm desiging an app-tray menu for the mobile end. 

Part of the problem I had, though, was moving from WordPress to hugo. When you export from WordPress you get a gigantic XML file. XML files were a really cool way to organize and transmit data, like, a long time ago. 

In fact, I remember about 10 years ago building a backend application for a local business with the `Authorize.Net` API, and it was XML. There weren't many online payment processors at the time, and JSON hadn't caught on yet, so I was building these big PHP scripts that would send and receive XML data. 

### *It was a bear.*

I bring it up only because using XML as a way to transport data for the web really feels outdated. There are a lot of other methods out there that allow you to have structure to your information in an easier to read and process format - Like JSON or YAML. 

And before you say anything: Yes I know RSS is a thing and XML is still very much in use for a lot of things - and I'm fine with XML - but it can be a bit bulky and cumbersome in some cases.

This gets us back to WordPress. When I exported my cat's website I was left with a *gigantic* XML file that serialized into XML tags every category, post, page, author, comment, image - every everything - into one, gigantic file.

And now I have to work to break that file down into component pieces so I can use it.

Compare that to my other project, [Lutheran Answers](https://www.lutherananswers.com), where I moved from a pre-made documentation theme to a custom template. It may not seem like it, but I had quite a bit of content to move over.

In addition to the *answers* section, I had podcasts, a blog post, and like 50% of the entire Book of Concord. 

{{< read-also "hugo-share-buttons" >}}

All of the content for that website, instead of being in a gigantic file, was inside of very individualized folders. Each file had it's own folder with it's own assets. Like folders were grouped under folder, which were grouped again, and again, up to the main /content folder.

When I moved to the new site and the new repo, the only thing I really had to do was copy the `content` folder. If I wanted to move things around, or put certain things together, it was easy. All of my data was very atomized and easily accessible.

I furthered this idea by breaking out authorship information into YAML data files.

Instead of hard coding my author information - which would suck to change later if I had a guest author - I went ahead and set it up so that my author information was compartmentalized in its own file that is called in on each individual page. 

This way I can specify which author file to pull from and extend it later with more authors if needed. And I can do that now without having to recode the entire site.

My overall point here is this: You will never regret separating out your content and data as much as possible. 

A complex machine is simply a complex arrangement of very simple pieces. It is easier to put together a bunch of smaller pieces, than to try and break up a larger thing.