---
layout: default
title: 8 Future perspectives
parent: Overview
nav_order: 9
description: "Future perspectives"
comments: true
folders:
  prediction: mirna-target-prediction
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
---

{% capture path_prediction %}{{ site.baseurl }}/{{ page.folders.prediction }}{% endcapture %}
{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

# 8 Future perspectives
{: .no_toc }

This chapter gives potential improvements in context of the three
sub-goals of our research. Many further perspectives are covered in the
papers, therefore, this section covers only additional perspectives that
are not discussed in the papers.

Firstly, for *[miRNA target prediction]({{ path_prediction }}/)*, it is important to improve the
computational speed of our two-step SVM model at the classification
phase. A current computational limitation of our model at classification
is mainly caused due to its usage of non-linear kernel at the second or
global level. Therefore, optimizing the second level classifier with a
linear kernel is a simple solution to improve the computational speed at
the classification phase. Moreover, training a SVM model with AGO
pull-down data is simple, but it can be a very effective approach.
However, existing AGO pull-down experiments provide no information
regarding difference of miRNA binding sites between controls and
transfected samples, therefore some scores, such as log-ratio values in
microarray, need to be calculated for SVM training.

Secondly, the results from our study in *[miRNA high-throughput experiments]({{ path_experiment }}/)*
can potentially improve other studies in both *[miRNA target prediction]({{ path_prediction }}/)*
and *[miRNA and other ncRNAs]({{ path_ncrna }}/)* because they mainly rely on the
data from microarray, proteomics, and next generation sequencing for
their model building and statistical analysis. Further interesting work
can be an expansion of the analysis with different types of data, such
as expression profiles of NCI-60 microarray data sets or time points
data.

Thirdly, understanding of ncRNAs characteristics and their interactions
with miRNAs becomes more important because ncRNA:ncRNA interactions are
likely involved in many gene regulations. In addition to cis-NATs and
CARs, it is interesting to expand the same approach to other types of
ncRNAs, such as long ncRNAs.

In conclusion, using data from next generation sequencing as well as
considering the results from *[miRNA high-throughput experiments]({{ path_experiment }}/)* is most
likely to enhance other studies in both *[miRNA target prediction]({{ path_prediction }}/)* and
*[miRNA and other ncRNAs]({{ path_ncrna }}/)*.
