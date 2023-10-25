---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 2
chapnam: "Technical Architecture"
pagenum: 1
title: Overview
summary: "High-level functional/conceptual description"
permalink: dglbdarch_ch2_p1.html
folder: articles\/dglb
---

## Functional Description

In this architecture, a DNS-based global-load-balancing (dGLB) service provides a mechanism for distributing incoming connections across a given application/service to two or more different locations where clusters of the application/service are being front-ended by application load balancers (ALBs.)  The GLB devices implement several core functions:

* Responding to DNS queries for the FQDNs of globally load-balanced services
* Performing health-checks of the downstream load-balancing targets for each GLB-hosted FQDN
* Executing a configured policy to determine **which**  downstream load-balancing target's information to include in DNS responses for the load-balanced FQDNs

By executing these functions, the GLB devices are able to distribute "connections" to a given FQDN across backend targets.  dGLB is ***only*** in-path for the DNS phase of client-to-server connectivity, which makes for extremely low capacity requirements on the GLB devices, but significantly limits to granularity and accuracy with which load-balancing can be implemented.

## Conceptual Architecture Diagram

The structure of the DNS zones maintained by the DNS authoritative nameservers is illustrated in the following figure.
{% capture details %}
![image](./dglb-conceptual-key.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide key{% endcapture %}{% include details.html %}
{% capture details %}
![image](./dglb-conceptual-1.drawio.svg)
{% endcapture %}
{% capture summary %}Show/hide diagram{% endcapture %}{% include details.html %}

{% include links.html %}