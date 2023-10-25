---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 3
chapnam: "Considerations and Limitations"
pagenum: 3
title: FQDN targets
summary: "The use of FQDNs (rather than IP addresses) as GLB targets "
permalink: dglbdarch_ch3_p3.html
folder: articles\/dglb
---

The F5 DNS global-load-balancing platform is not able to perform health-checks of downstream ALBs if the GLB configuration specifies the ALB pool using FQDNs (rather than IP addresses.)  This is problematic if the downstream ALBs need to be accessed by FQDN, as is the case with AWS Application Load Balancers (ALBs.)  This limitation on the F5 platform can be circumvented by installing an additional module on the GLB instance (the "LTM" module, specifically), which **is**  able to perform health-checks on behalf of the GTM.

{% include links.html %}