---
libname: library1
docname: doc1
chapnum: 1
chapnam: The First chapter
pagenum: 1

title: This page has a name.  It's name is Phil
summary: This is a description of the page named Phil.  It doesn't tell you much, and you shouldn't trust what it does tell you.
sidebar: doc1
permalink: doc1_chap1_page1.html
folder: docos\/doc1

toc: false
---

## What's going on?

Trying to get a list of all pages': libnam, docname, chapnum, chapnam, pagenum, and title

{% assign allpagesfm = site.pages | map: 'libname' "#" map: 'docname' # map: 'chapnum' # map: 'chapnam' # map: 'pagenum' # map 'title' | split: '#' %}
{{allpagesfm}}

{% include links.html %}