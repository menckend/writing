---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 3
chapnam: "Considerations and Limitations"
pagenum: 5
title: Use Cases
summary: "dGLB isn't particularly good at the actual balancing part of its just, but there are still plenty of good uses for it."
permalink: dglbdarch_ch3_p5.html
folder: articles\/dglb
---

Because dGLB provides a relatively coarse-grained mechanism for traffic distribution, it is of relatively low utility for balancing (the irony isn't lost on anyone) workload distribution across targets. Use cases are instead best differentiated by the resiliency models they enable.

### Active/Standby

In the active/standby use-case, the FQDN for a globally-load-balanced service will have exactly two targets. One of the targets (steady-state) is tasked for use during steady-state operating mode, and the other target (recovery) is tasked for use *only* if the steady-state instance fails. The dGLBs are configured with policy to ensure that they reply to DNS queries use the "steady-state" target's data as long as the steady-state target is passing healtchecks with the dGLB, and to respond using the "recovery" instance's data only when it passes healthchecks AND the "steady-state" instance fails healthchecks. This use-case is generally a good match for disaster-recovery scenarios.

### All Active

In the active/active use-case, the FQDN for a globally-load-balanced service will have two or more targets. The dGLB will be configured to alternate using the data of *each* target that is passing healtchekcs when responding to queries for the FQDNs of load-balanced services. The manner of alternation may vary greatly depending on the functionality of the specific dGLB platform and the nuances of the deployed workload.

{% include links.html %}