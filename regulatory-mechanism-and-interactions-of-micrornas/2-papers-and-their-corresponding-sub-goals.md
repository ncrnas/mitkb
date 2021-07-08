---
layout: default
title: 2 Papers and sub-goals
parent: Overview
nav_order: 3
description: "Papers and their corresponding sub-goals"
folders:
  prediction: mirna-target-prediction
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
pages:
  review: micrornas-targeting-and-target-prediction
  two_step_svm: two-step-svm-model
  confounding: confounding-factors-in-mirna-experiments
---

{% capture path_prediction %}{{ site.baseurl }}/{{ page.folders.prediction }}{% endcapture %}
{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

# 2 Papers and their corresponding sub-goals
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

This thesis includes five papers, and each paper has a corresponding
sub-goal (Table [2.1](#T:2.1)). This chapter gives a brief description of
paper in context of each sub-goal.

<br />
### **Table 2.1**. Papers and corresponding sub-goals of our research. {#T:2.1}
{: .no_toc .text-caption }

| **Sub-goal**                                                 | **Paper No.**                                                   | **Title**      |
|--------------------------------------------------------------|-----------------------------------------------------------------|------------------------|
| [miRNA target prediction]({{ path_prediction }}/)            | [Paper 1]({{ path_prediction }}/{{ page.pages.review }}/)       | MicroRNAs - targeting and target prediction |
|                                                              | [Paper 2]({{ path_prediction }}/{{ page.pages.two_step_svm }}/) | A two step site and mRNA-level model for predicting microRNA targets |
|                                                              | Paper 5                                                         | Inferring causative variants in microRNA target sites |
| [miRNA high-throughput experiments]({{ path_experiment }}/) | [Paper 3]({{ path_experiment }}/{{ page.pages.confounding }})   | Target gene expression levels and competition between transfected and endogenous microRNAs are strong factors in high-throughput experiments |
| [miRNA and other ncRNAs]({{ path_ncrna }}/)                 | Paper 4                                                         |MicroRNAs affect gene expression by targeting cis-transcribed non-coding RNAs |

---

## 2.1 Three papers for the first sub-goal: *miRNA target prediction* {#S:2.1}

**[Paper 1]({{ path_prediction }}/{{ page.pages.review }}/): MicroRNAs - targeting and target prediction**.
This review paper outlines the features associated with animal miRNA targeting. It
summarizes the characteristics of the features in six different
categories: miRNA:mRNA paring, Site location, Conservation, Site
accessibility, Multiple sites, and Expression profiles. It also contains
a list of 30 different miRNA target prediction tools with information of
feature coverage in context of the six categories.

**[Paper 2]({{ path_prediction }}/{{ page.pages.two_step_svm }}/): A two step site and mRNA-level model for predicting microRNA targets**. This paper presents a miRNA target prediction model that
recognizes both the individual characteristics of functional binding
sites and the global characteristics of miRNA-targeted mRNAs. Our novel
two-step SVM model trains site level features at the first step, and,
subsequently, it trains mRNA level features at the second step.
Benchmark experiments showed that our two-step SVM model had a higher
overall performance than other established miRNA target prediction
tools.

**Paper 5: Inferring causative variants in microRNA target sites**. This
paper shows an example that miRNA predictions from our two-step SVM
model performs better than the other prediction algorithms when the
predictions are used by other tools. Laurent F. Thomas was the main
contributor to this study, and he developed a tool that can help
identifying Single-nucleotide polymorphisms (SNPs) associated with
diseases by focusing on SNPs affecting miRNA regulation. The tool uses
miRNA target predictions to check the influence of SNPs that affect
miRNA targeting. It can use any miRNA prediction tools that generate
scores of miRNA target predictions. The paper showed that the tool had
the best performance when our two-step SVM model was used.

## 2.2 One paper for the second sub-goal: *miRNA high-throughput experiments* {#S:2.2}

**[Paper 3]({{ path_experiment }}/{{ page.pages.confounding }}/): Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments**.
This paper shows characteristics
of different miRNA high-throughput experiments. Analysis on these
high-throughput experiment data sometimes show inconsistent miRNA
regulation factors, for example, one experiment shows 3' UTR
length is one of the most important factors, whereas other experiment
shows it is least important. We investigated several factors that might
affect this inconsistence, and we revealed that competition between
endogenous miRNAs and the ectopically expressed miRNAs significantly
contributed to the differences among different miRNA high-throughput
experiments. We also found that this competition effect affected other
factors, such as mRNA expression level and 3' UTR length, in
terms of miRNA targeting.

## 2.3 One paper for the third sub-goal: *miRNA and other ncRNAs* {#S:2.3}

**Paper 4: MicroRNAs affect gene expression by targeting cis-transcribed non-coding RNAs**.
This paper shows potential miRNA regulation on two
types of complex loci: cis-natural antisense transcripts (cis-NATs) and
chromatin associated RNAs (CARs). We used several different types of
data from high-throughput miRNA experiments to infer potential miRNA
regulation on such loci. Our statistical analyses revealed that complex
loci containing non-coding cis-NATs or CARs appeared to be under strong
regulation, although this type of miRNA targeting is less prevalent than
miRNA targeting of 3' UTRs.
