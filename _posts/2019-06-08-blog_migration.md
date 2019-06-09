---
layout: post
title: Blog migration, from Wordpress to github-pages (Jekyll)
categories: System
tags:
- Jekyll
- blogging
- workflow
---

### My motive

The *Wordpress CMS* had served me well over the time. I had used it for a decade or so.

I never had any trouble with it, but it was becoming harder and harder to maintain:

- a dynamic website requires good administration, especially for updates and security;
- it is quite demanding in resources (PHP, MySQL), so hosting is pricy;
- adding contents is cumbersome, as it must be done online, within a browser and in a HTML editor.

These items caused much friction with my busy schedule and my workflow, vastely based around `git` and `markdown`.


### Advantages of a static website

First, there is an obvious advantage regarding hosting. Rendering static webpages is light and fast, so there are many cheap or even free hosting solutions.

Like many other people, I chose *Github Pages*, which is based on the Jekyll engine. Basically, you just create a `git` repo, fill it with `html` or `markdown`, and Github takes care of the rest to render the website after you push some changes.

It's transparent to the user and very well [documented](https://pages.github.com/), which is far from enough for my needs.

The other advantage is that the security issue is solved: it's much easier to secure a static website, moreover, in my case, it's now delegated to *Github*.

Finally, it is perfectly aligned with my workflow. I can now just fire up *Visual Studio Code* (my current favorite editor), write some article in `markdown` anytime and just push it online with `git`.
It is much more flexible and time saving, so I hope it will help me to publish from time to time.


### The migration: what did not work

By intuition, I thought that converting from the source, *Wordpress*, would give the best results.

I found that there is an extension just for that, namely [Simply Static](https://www.simplystatic.co/). There are a bunch of options to fix links and then generate a `zip` archive with the static contents.

On the paper, it looks nice, but for some reason, it did not work well with my blog: I ended with many broken links, missing resources, so it was not worth it.

I also considered just linking to the archive of my blog on [archive.org](https://archive.org/). After all, if it's already there, why bothering hosting old contents?
Unfortunately, it has a few caveats: some pages are missing and the performances are terribly bad, so much that it was a "no go".

Interestingly, there is a service [Wayback Machine Downloader](https://www.waybackmachinedownloader.com) which, for a small fee, offers to take care of the download. I tried the demo, but again experienced some breakage, so I was not convinced. 


### What worked: downloading with `httrack`.

A good old tool for scraping websites is `httrack`.

Below is the command I used to scrap the blog:

```sh
➜ httrack "https://phocean.net/" "+*.phocean.net/*"
```

I obtained a local archive, wich mostly worked when opened in a browser. However, many absolute links remained, which caused trouble with some CSS, `jquery` or images.

But nothing insurmountable: 15 minutes later, after `sed`, regex and eventually `find`, I got a perfect archive. For free.

### Conclusion

That's it, nothing special but I wanted to share this experience. I now hope to blog slightly more often. If you have some commets, you can find me on [twitter](https://twitter.com/_phocean) or [mastodon](https://mastodon.xyz/@phocean).