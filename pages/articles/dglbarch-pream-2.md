---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 1
chapnam: "Preamble"
pagenum: 2
title: "What *is* GLB?"
summary: "The quickest of overviews as to just what DNS-based global-load-balancing actually *is*."
permalink: dglbdarch_ch1_p1.html
folder: articles\/dglb
toc: false
---

Global load balancing ("GLB") is a service that directs inbound connections intended to terminate on a nominal application/service to actual instances of that application/service (typically at geographically dispersed locations.) GLB is distinguished from application-load-balancing ("ALB") in that its intended use-case is the distributing traffic across multiple physical locations/sites, rather than just across application-instances within a single location.

*DNS-based* global load-balancing (dGLB) uses the DNS "layer" of a networked application stack to perform that steering function.

There *are* other "flavors" of GLB to be had, but they are outside the scope of *this* document.


{% include links.html %}