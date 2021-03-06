---
layout: default
title: "Process model basics"
permalink: /docs/process-intro/
toc: true
sidebar:
  nav: "docs"
---

[//]: # (Please put comments like this one into the text to communicate with other OBI-ers)

Generally a **[`process`](http://purl.obolibrary.org/obo/BFO_0000015)** can have other processes as parts, and can have instances with start and end times associated with them.  A **[`planned process`](http://purl.obolibrary.org/obo/OBI_0000011)** is carried out by agent(s) who are guided by some kind of **[`plan specification`](http://purl.obolibrary.org/obo/IAO_0000104){:target="_blank"}**, an ICE which has **[`objective`](http://purl.obolibrary.org/obo/IAO_0000005)** and **[`action`](http://purl.obolibrary.org/obo/IAO_0000007)** components. A **[`study design`](http://purl.obolibrary.org/obo/OBI_0500000)** and its **[`protocol`](http://purl.obolibrary.org/obo/OBI_0000272)** part(s) are subclasses of `plan specification`. This is documented in the [`Core Classes`](/docs/core-classes/) page.

<img align="right" src="/assets/images/docs/data_assay.png">

A **process / datum model diagram** shows how material entities or data items can be an input or output of some process. This diagram often includes parts of entity property diagrams in order to reference components as inputs or in aboutness clauses.

The **[`assay`](http://purl.obolibrary.org/obo/OBI_0000070)** process diagram to right details axioms that enable types of assay to inherit requirements: [paraphrasing] that an assay input is a material entity playing an evaluant role, and that an assay outputs one or more data items.

<br clear="right">

The next example shows a **[`mass measurement assay`](http://purl.obolibrary.org/obo/OBI_0000445)** which takes in some material and outputs a **[`mass measurement datum`](http://purl.obolibrary.org/obo/IAO_0000414)**.  The output datum is stated to be a measure of (only) mass quality. The **[`is quality measurement of`](http://purl.obolibrary.org/obo/IAO_0000221)** object property is actually a sub-property of `is about` which is used when the target of aboutness is a quality.

<img src="/assets/images/docs/data_john_mass_process.png">

The Abox shows John as an input (standing on a scale, say), and documents that a `mass measurement datum` has been taken by the `mass measurement assay`. A process modeller can work at this more abstract level, avoiding references to specific protocols or instruments involving, say, units of measure. Alternately, by merging process modelling with specific value specifications (described below), we can describe particular equipment used in an experimental protocol or execution - say a brand and model of weight scale that is only capable of measuring in grams. (That level of detail promotes an ontology-driven plug-and-play future of equipment selection and protocol design.)

## Processes with inputs playing roles

**Mark's doctor/patient interaction event example here....**

Processes can have other participants besides inputs and outputs, such as operators and material consumables.




## Process parts

Here is a representation of a patient's HPV status, adapted from ["Ontology-Enhanced Representations of Non-image Data in The Cancer Imaging Archive"](http://ceur-ws.org/Vol-2285/ICBO_2018_paper_37.pdf). It illustrates that one may want to record the input to a subprocess and the output of a more abstract process, in this case involving an assay as part of a diagnostic process.

<img src="/assets/images/docs/data_patient_hpv_status.png">


## Material processing

<img align="right" src="/assets/images/docs/data_processed_material.png">

Processes don't necessarily generate information products.  The OBI [`material processing`](http://purl.obolibrary.org/obo/OBI_0000094){:target="_blank"} class covers many kinds of process such as sample preparation, manufacturing, and staining. [`Processed specimen`](http://purl.obolibrary.org/obo/OBI_0000953){:target="_blank"} is likely needed as part of experimental protocol modeling involving biosamples. It remains a material entity, rather than a `data item` that assays output.
