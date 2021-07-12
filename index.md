---
layout: default
title: Home
nav_order: 1
description: "mitkb: A knowledge base of miRNA targeting"
permalink: /
comments: true
folders:
  basicinfo: basic-information
  thesis: regulatory-mechanism-and-interactions-of-micrornas
  prediction: mirna-target-prediction
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
---
{% capture path_basicinfo %}{{ site.baseurl }}/{{ page.folders.basicinfo }}{% endcapture %}
{% capture path_thesis %}{{ site.baseurl }}/{{ page.folders.thesis }}{% endcapture %}
{% capture path_prediction %}{{ site.baseurl }}/{{ page.folders.prediction }}{% endcapture %}
{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

# mitkb: A knowledge base of miRNA targeting

## About the site

The main goal of **mitkb** is to provide a comprehensive konwlege base of microRNA (miRNA) targeting.

## Contents
The site aims to provide information regarding miRNA and miRNA targeting in the following 5 sections.

1. Overview

2. miRNA target prediction

3. miRNA high-throughput experiments

4. miRNAs and other non-coding RNAs

5. Support articles

### 1. Overview
The first section ([Overview]({{ path_thesis }})) is based on a doctoral thesis - Computational analysis of regulatory mechanism and interactions of microRNAs - successfully defended at Norwegian University of Science and Technology (NTNU), Trondheim, Norway in 2011.

The thesis covers bioinformatics approaches of various miRNA analyses, including the overview of non-coding RNAs, a short summary of high-throughput experiments, and theoretical background of statistical analysis and support vector machine.

<div class="code-example">
Saito, T. (2011). Computational analysis of regulatory mechanism and interactions of microRNAs (Doctoral dissertation). Norwegian University of Science and Technology, Trondheim, Norway.
<a href="https://doi.org/10.5281/zenodo.4902327">https://doi.org/10.5281/zenodo.4902327</a>
</div>
{: .bg-grey-lt-000 .p-3 }

### 2. microRNA target prediction
The second section ([Target prediction]({{ path_prediction }})) provides information about miRNA targeting and target prediction tools. It contains online version of a review article and a research article.

The review article starts with an introduction of miRNA targeting followed by computational methods of target prediction. The article also provides a list of target prediction tools that were available as of the publication time.

<div class="code-example">
Saito, T and Sætrom, P. (2010). MicroRNAs–targeting and target prediction.
New biotechnology 27 (3), 243-249.
<a href="https://doi.org/10.1016/j.nbt.2010.02.016">https://doi.org/10.1016/j.nbt.2010.02.016</a>.
</div>
{: .bg-grey-lt-000 .p-3 }

The research paper describes a microRNA target prediction model called Two-step SVM. Most target prediction methods have been developed to miRNA target sites, nonetheless there are many important features at the mRNA level, too. For instance, the miRNA regulation is known to be more effective when two target sites reside in an optimal distance than a single site. The aim of Two-step SVM is to integrate mRNA level features that most other models completely disregard.

<div class="code-example">
Saito, T and Sætrom, P. A two-step site and mRNA-level model for predicting microRNA targets.
<i>BMC Bioinformatics</i> <strong>11,</strong> 612 (2010).
<a href="https://doi.org/10.1186/1471-2105-11-612">https://doi.org/10.1186/1471-2105-11-612</a>.
</div>
{: .bg-grey-lt-000 .p-3 }

### 3. microRNA high-throughput experiments
The third section ([Biological experiments]({{ path_experiment }})) touches on technologies of microRNA high-throughput experiments and then move to descriptions of the challenges that would negatively affect interpretations of the experiment outcomes.

The main content of the section is based on a research article that summarises of confounding factors, which are such pit falls that are often associated with high-throughput experiments without noticing.

<div class="code-example">
Saito, T and Sætrom, P. Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments. <i>Silence</i> <strong>3,</strong> 3 (2012).
<a href="https://doi.org/10.1186/1758-907X-3-3">https://doi.org/10.1186/1758-907X-3-3</a>.
</div>
{: .bg-grey-lt-000 .p-3 }

### 4. microRNAs and other non-coding RNAs
The fourth section ([Other ncRNAs]({{ path_ncrna }})) provides interactions between miRNAs and other types of non-coding RNAs.

### 5. Support articles
The last section ([Support articles]({{ path_basicinfo }})) provides summaries of key topics, such as overview of miRNA and miRNA targeting.

- What is microRNA?
- What is microRNA target prediction?
- What is a confounding factor?

## License of this website

<div class="code-example">
This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>. <br /><br />
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>
</div>
{: .bg-grey-lt-000 .p-3 }
