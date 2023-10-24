---
libname: library1
docname: doc1
chapnum: 1
chapnam: "Dumb Chapter 1"
pagenum: 1
title: "l1d1ch1p1"
summary: "l1d1ch1 summary "
permalink: doc1_chap1_p1.html
folder: docos\/doc1
---

## What's going on?

Testing a way to get at different permutations of "libname", "docname", "chapnum", "chapnam", "pagenum", etc... for populating topnav and sidebars.

## Results

Seemed to work.  Onto something else.


## Try to detect presence of H2 sections programmatically 
...and disable TOC-toggle if they're not present.

{% assign tmparray = page.content | split: '##' | size %}
<p> Number of level-2 headers in page: {{tmparray}} </p>
<!--<p>Loop through page.content </p>
{% for chunk in page.content %}
<p>Array index = {{forloop.index0}}<p>
<p>{{chunk}}</p>
<p>{{page.content[forloopindex0]}}</p>
{% endfor %}
<p>_________________</p>
-->

{% include links.html %}
