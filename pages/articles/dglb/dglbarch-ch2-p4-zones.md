---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 2
chapnam: "Technical Architecture"
pagenum: 4
title: DNS Zone/Record Details
summary: "Detailed explanation of DNS zones and records as well as the recursive resolution process used in this architecture."
permalink: dglbdarch_ch2_p4.html
folder: articles\/dglb
---

## Diagram Key

{% capture details %}
![image](./dglb-zones-key.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide key{% endcapture %}{% include details.html %}

## Enterprise Nameserver DNS Zones

The structure of the DNS zones maintained by the DNS authoritative nameservers is illustrated in the following figure.
{% capture details %}
![image](./dglb-zones-1.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide diagram{% endcapture %}{% include details.html %}

## Global DNS Nameserver DNS Zones

The structure of the DNS zones maintained by the global load-balancers is illusrated in the following diagram.
{% capture details %}
![image](./dglb-zones-2.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide diagram{% endcapture %}{% include details.html %}

{% include links.html %}