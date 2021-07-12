---
layout: default
title: 1 Introduction
parent: Overview
nav_order: 2
description: "Introduction"
comments: true
group: thesis
folders:
  thesis: regulatory-mechanism-and-interactions-of-micrornas
  prediction: mirna-target-prediction
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
figs:
  fig1_1: [pubmed-query-mirna-papers.webp, 546]
scholar:
  bibliography: thesis_1
---

{% capture path_thesis %}{{ site.baseurl }}/{{ page.folders.thesis }}{% endcapture %}
{% capture path_prediction %}{{ site.baseurl }}/{{ page.folders.prediction }}{% endcapture %}
{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture fig1_1 %}{{ fig_dir }}/{{ page.figs.fig1_1[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# 1 Introduction
{: .no_toc }

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## 1.1 Challenges {#S:1.1}

In the 1980s, most non-protein-coding regions in the genome were thought
to be 'junk' DNA with no functional purpose {% cite Orgel1980 -f {{ bib }} %}. Nonetheless,
during the last two decades, new classes of non-coding RNAs (ncRNAs)
that have gene regulatory roles have been discovered within these 'junk'
regions {% cite Wright2011 -f {{ bib }} %}. MicroRNAs (miRNAs) are one such new class of
ncRNAs that have many important regulatory roles on a genome-wide scale
{% cite Bartel2004 -f {{ bib }} %}. Because of their importance, research on miRNAs has
gained popularity in recent years (Fig. [1.1](#F:1.1)).
Although many research efforts have revealed basic miRNA characteristic
and regulation {% cite Bartel2004 Bartel2009 -f {{ bib }} %}, there are still many
challenges to identify the comprehensive characteristics and precise
regulatory mechanism of miRNAs. This thesis covers three such challenges
related to miRNA studies.

### &nbsp; {#F:1.1}
{: .no_toc }
![Figure 1.1]({{ fig1_1 }}){:width="{{ page.figs.fig1_1[1] }}"}

#### **Figure 1.1**. PubMed query.
{: .no_toc .text-caption }
Two figures show the trend of miRNA related papers
as **(A)** the number of papers, and **(B)** the ratio to all papers in
PubMed.
{: .fs-2 }

---

The first challenge is to identify accurate miRNA targets in animals. It
is important to understand miRNA contributions to the genome-wide gene
regulation, but there are several known obstacles related to
indentifying miRNA targeRts in animals. Firstly, miRNAs are quite
abundant {% cite Bartel2004 -f {{ bib }} %}, and one miRNA can potentially regulate many
protein-coding genes {% cite Friedman2009 -f {{ bib }} %}. In some cases, miRNAs bind their
target mRNAs by base-pairing with only six nucleotides {% cite Friedman2009 -f {{ bib }} %},
which results in thousands of potential candidate genes influenced by
one miRNA at a genome-wide level. Secondly, since miRNAs are expressed
in a cell- or tissue-specific manner {% cite Wang2009b -f {{ bib }} %}, one true positive
miRNA target can be a false positive in a different cell or tissue type.
Thirdly, the precise mechanism of miRNA binding process on its target
mRNA is unknown {% cite Bartel2009 -f {{ bib }} %}. Therefore, combinations of miRNA features
are usually used to predict miRNA targets, but the combined effects of
these features on miRNA targeting are unclear.

The second challenge is to interpret miRNA high-throughput data
appropriately with high accuracy. Microarray, next generation
sequencing, and quantitative proteomics are three major high-throughput
technologies widely used for miRNA studies. Nonetheless, analyses of the
data from these high-throughput technologies often give different
interpretations regarding miRNA characteristics and regulation
{% cite Baek2008 Selbach2008 Wen2011 -f {{ bib }} %}. A major obstacle is that there are
many factors involved in these analyses, but the main factors that cause
these differences are unknown.

The third challenge is to indentify potential miRNA interactions with
other ncRNAs. Although most miRNAs regulate genes at the
post-transcriptional level, some miRNAs can also regulate transcription
itself {% cite Place2008 Kim2008 Younger2011 -f {{ bib }} %}. This transcriptional
regulation seems to involve ncRNAs overlapping or interacting with the
target gene promoters
{% cite Han2007 Morris2011 Morris2008 Schwartz2008 Yue2010 -f {{ bib }} %}. Many
aspects of this miRNA regulation at the transcription level are poorly
understood. Moreover, few experimental data are available for this miRNA
regulation at the transcription level.

## 1.2 Goals {#S:1.2}

The main goal of this thesis is to reveal the characteristics and
regulations of miRNAs by analyzing several different types of
high-throughput data through bioinformatics approaches. To achieve this
goal, I defined three sub-goals to solve the three challenges of miRNA
studies described in the previous section.

The first sub-goal is to develop a miRNA target prediction algorithm
with high accuracy. Most existing prediction algorithms focus on
identifying individual target sites without considering multiple target
sites. They do not include multiple target sites that possibly
contribute to miRNA regulation. Moreover, most algorithms use strict
filtering, such as filtering with evolutional conservation. Filtering
can reduce false positive miRNA targets, but it potentially removes many
true positive targets at the same time. Therefore, the aim of this
sub-goal is to develop a model that can predict unbiased miRNA targets
by considering multiple targets without filtering.

The second sub-goal is to analyze several different types of miRNA
high-throughput technologies. The aim of this sub-goal is to reveal the
characteristics of each technology and identify strong factors that
cause inconsistent results between different types of experiments by
statistical approaches.

The third sub-goal is to infer potential miRNA regulations outside of
3' untranslated regions (UTRs) in general and interactions
between miRNAs and ncRNAs in complex loci in particular. A complex locus
is a region of DNA that contains multiple genes that have interactions
between them or share common regulatory mechanisms {% cite Engstrom2006 -f {{ bib }} %}. Our
hypothesis is that some miRNAs interact with ncRNA:mRNA pairs in complex
loci. The aim of this sub-goal is to investigate this hypothesis of
miRNA involvement in complex loci together with miRNA regulations
outside of 3' UTRs by computationally analyzing the data from
high-throughput experiments.

In this thesis, these sub-goals are referred to in italic to clarify the
relationship between parts of the text and their corresponding sub-goals
if necessary.

-   First sub-goal: *[miRNA target prediction]({{ path_prediction }}/)*

-   Second sub-goal: *[miRNA high-throughput experiments]({{ path_experiment }}/)*

-   Third sub-goal: *[miRNA and other ncRNAs]({{ path_ncrna }}/)*

## 1.3 Thesis structure {#S:1.3}

This thesis consists of eight chapters followed by five papers.

[Chapter Two: Papers and their corresponding sub-goals.]({{ path_thesis }}/2-papers-and-their-corresponding-sub-goals/)
This chapter summarizes the five papers included in this thesis. It also relates them
to each sub-goal.

[Chapter Three: MicroRNAs and other non-coding RNAs.]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/)
This chapter introduces the history, characteristics, and biological functions of
miRNAs as well as some additional information about other ncRNAs.

[Chapter Four: High-throughput biological experiments.]({{ path_thesis }}/4-high-throughput-biological-experiments/)
This chapter focuses on three high-throughput technologies used in our research:
microarray, next generation sequencing, and quantitative proteomics.

[Chapter Five: Statistical tests and methods.]({{ path_thesis }}/5-statistical-tests-and-methods/)
This chapter starts with explaining basic statistical tests followed by applied statistical
approaches used throughout in our research, such as non-parametric
tests, resampling, and multiple comparison tests.

[Chapter Six: Machine learning theory and Support vector machine.]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/)
Support vector machine (SVM) is the main method used in the first
sub-goal: *miRNA target prediction*. This chapter explains the
theoretical background of SVM, data preparation and evaluation methods
for SVM, as well as some other machine learning methods for comparison.

[Chapter Seven: Computational implementation.]({{ path_thesis }}/7-computational-implementation/)
Any state-of-the-art model or algorithm is ineffective without appropriate computational
implementation. This chapter focuses on the computation implementations
used in our research.

[Chapter Eight: Future perspective.]({{ path_thesis }}/8-future-perspectives/)
This chapter describes potential improvements of each sub-goal as future perspectives.

## References {#S:1.4}
{% bibliography --cited_in_order -f {{ bib }} %}
