---
libname: Articles
docname: Global Load Balancing Reference Architecture
chapnum: 3
chapnam: "Limitations/Constraints"
pagenum: 1
title: limitation 1
summary: "some limitations"
permalink: dglbdarch_ch3_p1.html
folder: articles\/dglb
---

## Limitations

### Coarseness of Load-balancing Granularity and Impact on Session Persistence

Because DNS-based GLBs are only in path for DNS, they are only able to act on data in the DNS queries it receives when categorizing the client-side of connections that it is load-balancing.  The source-IP address of the DNS queries that it receives for the FQDN's of GLB'ed services is the primary mechanism for that type of categorization.  In this architecture, the IP addresses of the recursive resolvers (not the clients) are exposed to the GLBs.  The upshot of this is that with session persistence enabled, the GLBs are required to make the **same**  load-balancing decision for each recursive resolver that it receives DNS queries from. This is not a problem in the short term, with relatively low requirements for multi-active site-level load-balancing, but that use-case is expected to increase in the near future.

### Presentation of Downstream ALBs as IP addresses or FQDNs

The F5 DNS global-load-balancing platform is not able to perform health-checks of downstream ALBs if the GLB configuration specifies the ALB pool using FQDNs (rather than IP addresses.)  This is problematic if the downstream ALBs need to be accessed by FQDN, as is the case with AWS Application Load Balancers (ALBs.)  This limitation on the F5 platform can be circumvented by installing an additional module on the GLB instance (the "LTM" module, specifically), which **is**  able to perform health-checks on behalf of the GTM.

### 1:1 Relationship between FQDNs and load-balanced services

ALBs may have a 1:many FQDN:load-balanced-service relationship, whereas GLBs have a 1:1 FQDN:load-balanced-service relationship.  Application load-balancers (ALBs) typically present to the consumer with one ore more IP address, which *may* be abstracted as an FQDN.  A single client-facing FQDN can be sufficient for an ALB to act as a load-balancer for *multiple* different applications.  Because it is inline for the actual *application* data plane, the ALB *can* perform application-layer inspection to classify requests for different URIs to different back-end resource pool.  It can likewise instantiate TCP listeners on multiple ports using the same IP address, and map each TCP port to a different backend resource pool.   In this scenario, an ALB with a single FQDN and single virtual-IP address can independently distribute traffic for **multiple** backend load-balanced services.   While a single FQDN can suffice for ALBs to independently manage load-balancing for multiple services, the same is not true of GLBs.  This is true is all cases, but is especially significant for Kubernetes workload.

{% include links.html %}