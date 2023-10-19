---
libname: library1
docname: doc1
chapnum: 1
chapnam: "The First chapter"
pagenum: 1

title: "This page has a name.  It's name is Phil"
summary: "This is a description of the page named Phil.  It doesn't tell you much, and you shouldn't trust what it does tell you."
sidebar: doc1
permalink: doc1_chap1_page1.html
folder: docos\/doc1

toc: false
---

## What's going on?
Trying to get a list of all pages': libnam, docname, chapnum, chapnam, pagenum, and title

{% assign pagelist = site.pages %}
{% assign pageliblist = site.pages | map: libname %}
{% assign pagedoclist = site.pages | map: docname %}

{{pageliblist}}
{{pagedoclist}}

{% include links.html %}