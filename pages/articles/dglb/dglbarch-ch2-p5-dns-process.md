---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 2
chapnam: "The Reference Architecture"
pagenum: 5
title: Resolution Process
summary: "Detailed explanation of DNS zones and records as well as the recursive resolution process used in this architecture."
permalink: dglbdarch_ch2_p5.html
folder: articles\/dglb
---

The process of DNS resolution from client-device, to recursive-resolver, to authoritative nameserver, back to recursive-resolver, to glb, back to recursive resolver, and back to client-device is depicted in the following flowcharts:
{% capture details %}
![image](./dglb-resolution-flowchart.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide flowchart{% endcapture %}{% include details.html %}

{% capture details %}
![image](./dglb-resolution-flowchart4.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide sub-flowcharts (steps 4 and 6){% endcapture %}{% include details.html %}



{% include links.html %}