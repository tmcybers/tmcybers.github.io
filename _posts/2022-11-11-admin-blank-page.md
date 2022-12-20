---
title: Admin [Blank Page Jekyll] [Solution]
layout: post
post-image: /assets/images/bannergit.png
description: Solution to the error of the jekyyl /admin blank page, and here is my solution.
tags:
  - Jekyll
  - Admin
  - Linux
---

## After some days of large Research I have found a solution of the ---blank page--- of the localhost:4000/admin of jekylls themes.


``` bash

 U must remove the version of your jekyll-admin from Gem.file in your path admin.

and leave only jekyll-admin , simply , no version needed like "0.9.0" this will make /admin crashing with all gems and ruby versions

```

Take a `look` at `my gemfile` you should have equal to this.

![admin](/assets/images/imagesposts/admin.png)


var s = "JavaScript syntax highlighting";
alert(cheers);

{% include share-buttons.html %}