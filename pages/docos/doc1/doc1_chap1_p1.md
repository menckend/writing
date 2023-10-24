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

## test

## test

## test


## Try to detect presence of H2 sections programmatically 
...and disable TOC-toggle if they're not present.

{% assign tmparray = page.content | markdownify | split: '<H2>' |size %}
<p> Number of h2 headers in page: {{tmparray}} </p>

{% include links.html %}
