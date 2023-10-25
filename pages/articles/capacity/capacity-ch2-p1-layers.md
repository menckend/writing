---
libname: Articles
docname: -DRAFT- Abstracting Capacity
chapnum: 2
chapnam: "Foundations"
pagenum: 1
title: Multi-layered Architecture Model
summary: "IT systems are inherently layered; we need a consistent way to talk about how that layering works if we're going to look at how that layering is related to capacity."
permalink: capacity_ch2_p1.html
folder: articles\/capacity
---

## Let's Talk Layers

The idea of a layered-model is foundational in information technology, but is worth elaborating on briefly with regards to IT systems architecture. 

### Conventional Description

I haven't been able to locate any single authoritative reference for what a "layered architecture" is, but there are a few themese that seem to be pretty ubiquitous:

#### Properties of Layers

* Layers are groupings of elements with similar functionality. 
    * Typically depicted as horizontal bands in graphical representations.)
* Layers are arranged hierarchically
* Information moves between adjacent layers only

#### Benefits of Layered architectures

* Well-implemented layered architectures allow for modular refit of system elements.
    * An MS SQLServer instance acting as an element in a "database layer" could be be replaced with a PostGRESQL, for instance
* Provide an abstracted, functional-level view of overall system architecure

### How I'll approach layered architectures throughout this document

I will use the following conventions with regards to conceptual layers of IT systems architecture throughout this document:

* Layers are designated with both an index number and a name
* Layers are hierarchical
* For any two "adjacent" layers in an architecture stack, the *lower* of the two layers is considered to be (the "hosting" layer), which *hosts* the upper of the two layers (the "<em>workload</em>" layer).
    * Conversely, the workload layer is hosted on the hosting layer.
* The hosting layer exposes (provides) "functions" and "capacity" to the workload layer through its "interfaces"
    * A "function" is something that the hosting layer can do.
    * "Capacity" is how *much* of a function the hosting layer can do.
    * An "interface" is an implementation of a well-defined mechanism through which the workload layer can expose/deliver functions and capacity
* The workload layer consumes (receives) functions and capacity from the workload layer via its own interfaces, which implement the same well-defined mechanism as the inerfaces of the hosting layer

## Examples of Layered Architecture Models

Here are a couple of extremely uniquitous layered-models that crop up in IT systems architecture:

### OSI Networking Model

OK, maybe a bit too on the nose, given my background, but it's certainly ubiquitous! In this model, there are seven layers, starting with Layer One (Physical) and rising all the way to Layer 7 (Application). Here, we'll take a quick look at Layers 3 (network) and (4) connection and see how they match up with the framework I discussed above. In that model:

* Layer 3 (network; typically implemented as IP) is the hosting layer for layer 4 (connection; typically implemented as TCP.)
    * L3/IP provides data transport services to the transport layer (TCP) using a well-defined interface called a "socket"


<br>
<br>
{% include links.html %}