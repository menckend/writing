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

<p>Loop through an array that page.content was mapped to.</p>
<p>
{% assign bigvar == emptyArray %}
{% assign bigvar == page.content %}
{% for chunk in bigvar %}
{{chunk}}
{% endfor %}
</p>


{% include links.html %}
