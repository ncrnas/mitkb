---
layout: default
title: "Supplementary information"
parent: Target prediction
description: "Supplementary information: A two-step site and mRNA-level model for predicting microRNA targets"
nav_order: 3
group: two-step-svm
folders:
  prediction: mirna-target-prediction
pages:
  main: two-step-svm-model
tabs:
  tabS1: tableS1
  tabS2: tableS2
  tabS3: tableS3
  tabS4: tableS4
  tabS5: tableS5
  tabS6: tableS6
  tabS7: tableS7
  tabS7_attr: {skip_sp_head: true}
  tabS8: tableS8
  tabS9: tableS9
  tabS10: tableS10
  tabS11: tableS11
  tabS12: tableS12
  tabS13: tableS13
  tabS14: tableS14
  tabS15: tableS15
figs:
  figS1: [cross-validation-target-site-level.webp, 500]
  figS2: [target-count-divided-by-three-prime-utr-length.webp, 500]
  figS3: [svm-training-with-and-without-negative-data.webp, 800]
  figS4: [cross-validation-mrna-level.webp, 500]
  figS5: [roc-benchmark-mirna-target-prediction-linsley.webp, 800]
  figS6: [roc-benchmark-sirna-off-target-prediction-jackson.webp, 800]
  figS7: [roc-benchmark-mirna-target-prediction-lim.webp, 800]
  figS8: [roc-benchmark-sirna-off-target-prediction-birmingham.webp, 800]
  figS9: [roc-benchmark-mirna-target-prediction-grimson.webp, 800]
  figS10: [two-step-svm-discriminant-value-vs-mirna-target-type.webp, 500]
  figS11: [evaluate-mirna-site-accessibility-conservation.webp, 800]
  figS12: [two-step-support-vector-regression.webp, 800]
  figS13: [two-step-svm-gene-expression.webp, 800]
  figS14: [two-step-svm-training-with-proteomics.webp, 500]
  figS15: [roc-benchmark-mirna-target-prediction-selbach.webp, 800]
  figS16: [roc-benchmark-mirna-target-prediction-baek.webp, 800]
  figS17: [roc-benchmark-mirna-target-prediction-linsley-log-ratio-01.webp, 800]
  figS18: [roc-benchmark-mirna-target-prediction-linsley-log-ratio-03.webp, 800]
  figS19: [roc-benchmark-mirna-target-prediction-selbach-log-ratio-01.webp, 800]
  figS20: [roc-benchmark-mirna-target-prediction-selbach-log-ratio-03.webp, 800]
  figS21: [roc-benchmark-mirna-target-prediction-baek-log-ratio-01.webp, 800]
  figS22: [roc-benchmark-mirna-target-prediction-baek-log-ratio-03.webp, 800]
scholar:
  bibliography: two_step_svm_suppl
---

{% capture page_main %}{{ site.baseurl }}/{{ page.folders.prediction }}/{{ page.pages.main }}{% endcapture %}

{% assign tab_arr = site.data[page.group] %}
{% assign tabS1 = tab_arr[page.tabs.tabS1] %}
{% assign tabS2 = tab_arr[page.tabs.tabS2] %}
{% assign tabS3 = tab_arr[page.tabs.tabS3] %}
{% assign tabS4 = tab_arr[page.tabs.tabS4] %}
{% assign tabS5 = tab_arr[page.tabs.tabS5] %}
{% assign tabS6 = tab_arr[page.tabs.tabS6] %}
{% assign tabS7 = tab_arr[page.tabs.tabS7] %}
{% assign tabS8 = tab_arr[page.tabs.tabS8] %}
{% assign tabS9 = tab_arr[page.tabs.tabS9] %}
{% assign tabS10 = tab_arr[page.tabs.tabS10] %}
{% assign tabS11 = tab_arr[page.tabs.tabS11] %}
{% assign tabS12 = tab_arr[page.tabs.tabS12] %}
{% assign tabS13 = tab_arr[page.tabs.tabS13] %}
{% assign tabS14 = tab_arr[page.tabs.tabS14] %}
{% assign tabS15 = tab_arr[page.tabs.tabS15] %}
{% assign tabS16 = tab_arr[page.tabs.tabS16] %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture figS1 %}{{ fig_dir }}/{{ page.figs.figS1[0] }}{% endcapture %}
{% capture figS2 %}{{ fig_dir }}/{{ page.figs.figS2[0] }}{% endcapture %}
{% capture figS3 %}{{ fig_dir }}/{{ page.figs.figS3[0] }}{% endcapture %}
{% capture figS4 %}{{ fig_dir }}/{{ page.figs.figS4[0] }}{% endcapture %}
{% capture figS5 %}{{ fig_dir }}/{{ page.figs.figS5[0] }}{% endcapture %}
{% capture figS6 %}{{ fig_dir }}/{{ page.figs.figS6[0] }}{% endcapture %}
{% capture figS7 %}{{ fig_dir }}/{{ page.figs.figS7[0] }}{% endcapture %}
{% capture figS8 %}{{ fig_dir }}/{{ page.figs.figS8[0] }}{% endcapture %}
{% capture figS9 %}{{ fig_dir }}/{{ page.figs.figS9[0] }}{% endcapture %}
{% capture figS10 %}{{ fig_dir }}/{{ page.figs.figS10[0] }}{% endcapture %}
{% capture figS11 %}{{ fig_dir }}/{{ page.figs.figS11[0] }}{% endcapture %}
{% capture figS12 %}{{ fig_dir }}/{{ page.figs.figS12[0] }}{% endcapture %}
{% capture figS13 %}{{ fig_dir }}/{{ page.figs.figS13[0] }}{% endcapture %}
{% capture figS14 %}{{ fig_dir }}/{{ page.figs.figS14[0] }}{% endcapture %}
{% capture figS15 %}{{ fig_dir }}/{{ page.figs.figS15[0] }}{% endcapture %}
{% capture figS16 %}{{ fig_dir }}/{{ page.figs.figS16[0] }}{% endcapture %}
{% capture figS17 %}{{ fig_dir }}/{{ page.figs.figS17[0] }}{% endcapture %}
{% capture figS18 %}{{ fig_dir }}/{{ page.figs.figS18[0] }}{% endcapture %}
{% capture figS19 %}{{ fig_dir }}/{{ page.figs.figS19[0] }}{% endcapture %}
{% capture figS20 %}{{ fig_dir }}/{{ page.figs.figS20[0] }}{% endcapture %}
{% capture figS21 %}{{ fig_dir }}/{{ page.figs.figS21[0] }}{% endcapture %}
{% capture figS22 %}{{ fig_dir }}/{{ page.figs.figS22[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# ﻿Supplementary information: A two-step site and mRNA-level model for predicting microRNA targets
{: .no_toc .text-center }

Takay Saito and Pål Sætrom
{: .text-center }

<iframe src="https://widgets.figshare.com/articles/14923641/embed?show_title=0" width="100%" height="351" allowfullscreen frameborder="0"></iframe>

<div class="code-example">
<strong>Citation:</strong> <br />
Saito, T and Sætrom, P. A two-step site and mRNA-level model for predicting microRNA targets.
<i>BMC Bioinformatics</i> <strong>11,</strong> 612 (2010).
<a href="https://doi.org/10.1186/1471-2105-11-612">https://doi.org/10.1186/1471-2105-11-612</a>.
</div>
{: .bg-grey-lt-000 .p-3 }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Supplementary Methods {#S:1}
### Data partition into positive (down-regulated) and negative genes {#S:1-1}
Down-regulated (positive) genes of GEO datasets were defined as records with p-value < 0.001 and log intensity ratio < -0.3 to obtain strongly down-regulated genes. Down-regulated genes for the Birmingham dataset were obtained directly from the published data {% cite Birmingham2006 -f {{ bib }} %}.

Some microarray records contained different results for the same combination of miRNA/siRNA and mRNA; for example, there were five records of a miRNA on the same mRNA, and four of them were regarded as down-regulated but one of them were unaffected. In this case, all records that belonged to this combination were disregarded to enhance the quality.

Negative records of GEO datasets consisted of both unaffected and up-regulated genes. Unaffected genes were defined as records with p-value > 0.3 and log intensity ratio between -0.3 and 0.3, whereas up-regulated genes were defined as records with p-value < 0.001 and log intensity ratio > 0.3. Negative records for the Birmingham dataset were defined as all RefSeq transcripts except the positive records.

As a final filter, all miRNA:mRNA pairs that had either very high (>1.25) or very low (<-1.5) log intensity values in the control experiments were eliminated to reduce potential noise form extreme expression values.

All the positive records were used in the training dataset, whereas negative records were randomly selected to meet a total record number of 20000, unless otherwise specified. A maximum total record number of 20000 was used due to computational time and memory space constraints.

For the test data, positive records were selected as for the training data, whereas all the remaining records were used as negative records.

For the Linsley dataset {% cite Linsley2007 -f {{ bib }} %}, down-regulated genes were defined as records with p-value < 0.001 and log intensity ratio < -0.2.

For the Selbach and Baek datasets, down-regulated genes (positive) were defined as records with log ratio values < -0.2, whereas unaffected genes (negative) were defined as log ratio values > 0. The records that do not fit in these criteria were not used in this study.

### Data retrieval for benchmarks {#S:1-2}
Prediction data were downloaded from the Segal Lab site ([https://genie.weizmann.ac.il/pubs/mir07/](https://genie.weizmann.ac.il/pubs/mir07/)) for PITA All and PITA Top, the TargetScanHuman 5.1 site ([http://www.targetscan.org](http://www.targetscan.org)) for TargetScan and TargetScan with conserved genes, the MicroCosm Targets Version 5 site (http://www.ebi.ac.uk/enright-srv/microcosm) for miRanda, the miRDB site ([http://mirdb.org](http://mirdb.org)) for mirTarget2, and the PicTar WEB INTERFACE site ([https://pictar.mdc-berlin.de/](https://pictar.mdc-berlin.de/)) for PicTar. Several methods provide only target site level scores for download, and, in that case, summation methods showed in the web sites or in the original publications were applied to obtain scores for the mRNA level. For siRNA predictions, PITA and TargetScan executable programs were downloaded and used to calculate prediction scores.

### Performance evaluation on independent dataset {#S:1-3}
Six dataset – “ROC with All genes”, “ROC10*n”, “ROC with 7mer + Conservation”, and three method-specific datasets for TargetScan, miRanda, and PicTar – were created for evaluation. The “ROC with All genes” dataset was comprised of all the records from the microarray dataset.

“ROC10\*n” was based on the standard ROC50 {% cite Gribskov1996 -f {{ bib }} %} benchmark. The ROC50 benchmark score is the area under the ROC curve until 50 negatives are found. Consequently, the “ROC10\*n” benchmark datasets consisted of all the true positives found in the microarray experiments and the 10*n first negatives found by each method benchmarked.

The “ROC with 7mer + Conservation” dataset was comprised of genes with conserved 8mer or 7mer-m8 or 7mer-A1 sites. Sites were defined as conserved if the average phyloP 44 scores in the seed region were > 0.9.

The three method-specific datasets for TargetScan, miRanda, and PicTar were generated by only using the records from the microarray experiments that had corresponding predictions for each method.

## Supplementary Results {#S:2}
### Analysis of target site level training data: Selection of seed types influences the coverage of potential target sites {#S:2-1}
Current methods for miRNA target prediction base their analyses on identifying so-called seed sites in 3' UTR. The definition of seed types varies from one prediction algorithm to another {% cite Gaidatzis2007 Grimson2007 Hammell2008 -f {{ bib }} %}, however, and this heavily influences the coverage of potential target sites. Lower coverage means that predictions may lack many true positive sites, whereas higher coverage may result in poor accuracy because of too many false positive sites.

Based on four different microarray datasets - Birmingham {% cite Birmingham2006 -f {{ bib }} %}, Jackson {% cite Jackson2006 -f {{ bib }} %}, Lim {% cite Lim2005 -f {{ bib }} %}, and Grimson {% cite Grimson2007 -f {{ bib }} %}, we identified a set of 823 genes that were down-regulated in response to artificial miRNA or siRNA transfection, or up-regulated in response to miRNA inhibition (see [Supplementary Methods](#S:1-1)). This positive set of genes constituted 0.14% of the 571570 potential miRNA:gene interactions assayed in the microarray experiments. Searching for seed sites among the positive genes identified that 347 and 510 genes contained stringent and all types of seed sites. Thus, basing miRNA target predictions on stringent seeds or all seed types would cover 42% or 62% of the positive genes. The corresponding numbers for the negative set of 570747 genes were 128254 and 31277. Consequently, the predictive accuracy, as measured by the positive predictive value (PPV = True positive predictions / All positive predictions), was almost three times greater for stringent seeds (PPV = 1.1%) than for all seed types (PPV = 0.40%). Even so, this showed that predicting miRNA targets purely based on identifying stringent seed sites would give too many false positive predictions to be viable in practice.

Several approaches have shown that other target-related features besides the seed type and additional data such as miRNA and mRNA expression profiles can improve predictive accuracy {% cite Huang2007 Sales2010 -f {{ bib }} %}. We therefore chose to include all seed types to achieve high coverage in the training data and then improve the accuracy through two-step SVM training.

### Prediction of targets with optimal distance sites: Optimal distance is effectively incorporated in our SVM prediction {#S:2-2}
We were interested to see how well the features of optimal distances were incorporated into our algorithm. Our model uses two mRNA features that represent optimal distances: (i) the number of sites that have other neighboring sites within 13-46 nt and (ii) the number of sites that have other neighboring sites within 17-25 nt. Furthermore, one target site level feature, “distance to the next target” could be effective to recognize the targets with optimal distance. However, these features showed little contribution when the influence of both target site and mRNA level features was analyzed (Tables [S2](#T:S2) and [S4](#T:S4)). Therefore, we applied a different approach as to see the difference of prediction power between the target genes with optimal distance and other target genes.

First, we categorized all potential targets into four different target types, which were defined by the number of potential target sites, seed types, and existence of optimal distance sites within the gene’s 3’ UTR. “Single non-stringent” and “Single stringent” were targets that had only one “non-stringent” and “stringent” seed site, whereas “Multiple without optimal distance” and “Multiple with optimal distance” were targets that had multiple sites where none or at least one pair of sites were within . Then, we checked the mRNA level classifier’s distributions of discriminant values for these four target types. The resulting box plots (Fig. [S10](#F:S10)) show that for each target type, the mRNA-level SVM clearly separates between the positive (down-regulated) and negative (non-down-regulated) targets. Moreover, targets with multiple sites had higher discriminant values than targets with single stringent and single non-stringent sites, and the targets with optimally spaced sites had the highest discriminant values. Thus, site distance contributed positively to the SVM’s predictions.

### Site accessibility and sequence conservation: Explicit usage of site accessibility and sequence conservation do not improve SVM prediction {#S:2-3}
Although target site accessibility is important for both miRNA and siRNA targeting {% cite Kertesz2007 Long2007 -f {{ bib }} %}, it is unclear how useful computational predictions of target site accessibility are for genome-wide miRNA target analyses {% cite Baek2008 Hammell2008 -f {{ bib }} %}. Similarly, even though many target prediction tools rely on conserved sequences, as these indicate conserved function and targeting, sequences with little or no evidence of conservation can still be functional target sites {% cite Sethupathy2006 -f {{ bib }} %}. Moreover, calculating target site accessibility and conservation features demand much higher computational power and resources than calculating the other features. Therefore, we constructed classifiers without using the site accessibility and sequence conservation features to evaluate their importance in our SVM model.

To evaluate the classifier without of site accessibility and sequence conservation features, we compared the ROC scores of three mRNA level classifiers that used the same mRNA level features, but three different target site classifiers; that is, classifiers (i) without site accessibility and conservational information, (ii) with site accessibility, and (iii) with conservational information. The classifiers were then tested on the independent dataset.

All the results from the 10-fold cross-validation and independent tests showed very little difference among the three classifiers (Fig. [S11](#F:S11)). Although theoretically sound, the computationally intensive accessibility predictions could therefore, in practice, be eliminated from the SVM classifier. In addition, although many miRNA target sites appear to be well conserved, the small influence of the conservation-related features on SVM performance indicate that many non-conserved miRNA targets exist. This is consistent with the results of the benchmarks of the 8 existing miRNA target prediction methods. Consequently, the proportion of non-conserved miRNA target sites in the set of all potential target sites seems too large to be ignored. Therefore, we opted to train our SVM classifiers without using site accessibility and sequence conservation.

### Classification vs. Regression: Support vector classification (SVC) performs better than support vector regression (SVR) {#S:2-4}
The microarray data used in our experiments measured actual changes in gene expression in response to miRNA or siRNA over-expression. Consequently, even though we treated miRNA target prediction as a classification problem, target prediction could also be solved as a regression problem. To test whether treating target prediction as a regression problem would further improve our predictions, we used the PyML library to train SVR models to fit the log ratio values from the Jackson, Lim, and Grimson microarray experiments. We did not use the Birmingham dataset because pre-processed log ratio values were not available. The SVR models used the same two step approach and the same features as our previous SVC models. The same optimization approach as we used for the SVC models showed that a linear kernel with default parameters gave the best predictions at both the target site and mRNA level. This model selection often resulted in over-fitting or no convergence, however, hence requiring more analysis time than SVC to find an optimal kernel. Moreover, the SVR target site and mRNA level models showed lower prediction performance at the 10-fold cross-validation and independent data set than the SVC models did (Fig. [S12](#F:S12)). Thus, when the input is based on features derived from the target sequence, classification models are as good or better at predicting miRNA or siRNA target gene expression fold changes as are regression models.

### Dataset selection: Different parameters for constructing training or test data do not affect SVM prediction performance {#S:2-5}
It is important to verify that our SVM approach is still effective when we select different positive (down-regulated) and negative (non-down-regulated) datasets for both training and test because it proves that our SVM approach is not optimized only for a certain parameter criteria of data selection. We generated seven different datasets; one for training and six for independent test sets to further investigate SVM prediction power with different data selection parameters.

Two major steps applied to create datasets in our study were; (i) all microarray datasets were separated into three groups; down-regulated, unaffected and up-regulated, depending of the log ratio values, and (ii) positive data were selected from down-regulated genes, whereas negative records were from both unaffected and up-regulated genes. However, some miRNAs are known to potentially up-regulate genes. The mechanism of this up-regulation is unknown, and the features of up-regulated target sites/genes are possibly quite different from those of miRNAs involved in down-regulation. To check the influence of involving these up-regulated genes in our SVM training sets, we constructed a dataset without up-regulated genes, and trained and tested it on the independent datasets. The 10-fold cross-validation ROC plots for both target site and mRNA level classifiers trained without up-regulated genes (Fig. [S13](#F:S13) A, C) were almost identical to those trained with up-regulated genes (Fig. [S13](#F:S13) E, G). The prediction power was also retained when the classifiers were tested on the Linsley dataset (Fig. [S13](#F:S13) B, D) and compared with those trained with up-regulated genes (Fig. [S13](#F:S13) F, H).

Moreover, we generated six independent subsets for one transcriptomics (Linsley) and two proteomics (Selbach and Baek) experiments. Two different positive record datasets defined by log-ratio values <-0.1 and <-0.3 were created for each experiment, resulting in six independent datasets altogether. We performed benchmarks on these datasets and compared with the dataset defined by the log-ratio values <-0.2, which had been used as the default value for all the other benchmarks. The number of positive records detected by all of the eight algorithms in the benchmarks was higher in the log ratio <-0.1 sets; Linsley (Table [S10](#T:S10)), Selback (Table [S12](#T:S12)), and Baek (Table [S14](#T:S14)), and lower in the log ratio <-0.3 sets; Linsley (Table [S11](#T:S11)), Selback (Table [S13](#T:S13)), and Baek (Table [S15](#T:S15)), as expected. The ROC scores from the benchmarks show that SVM outperforms other algorithms in most cases regardless of different parameter criteria of data selection. We also analyzed the ROC curves of the benchmarks to check the trends among the log ratio <-0.2 sets; Linsley (Fig. [5]({{ page_main }}#F:5), [S5](#F:S5)), Selback (Fig. [6]({{ page_main }}#F:6), [S15](#F:S15)) and Baek (Fig.[6]({{ page_main }}#F:6), [S16](#F:S16)), the log ratio <-0.1 sets; Linsley (Fig. [S17](#F:S17)), Selback (Fig. [S19](#F:S19)) and Baek (Fig. [S21](#F:S21)), and the log ratio <-0.3 sets; Linsley (Fig. [S18](#F:S18)), Selback (Fig. [S20](#F:S20)) and Baek (Fig. [S22](#F:S22)). All ROC curves showed very similar trends among different positive record sets. More importantly, our SVM approach retained its prediction power even when it was tested on the log ratio <-0.3 and <-0.1 sets.

These results indicate that our SVM prediction power is not affected when trained with or without up-regulated genes, or tested on strongly down-regulated pairs (log ratio <-0.3) as well as moderately down-regulated pairs (log ratio <-0.1).

## Supplementary Tables {#S:3}
### **Table S1**. Target site level features. {#T:S1}
{: .text-caption }

{% include tbl_simple.html data=tabS1 %}

<sup><strong>a</strong></sup>Vector size used in SVM training. <sup><strong>b</strong></sup>Site accessibility features. ○: Yes, blank: No. <sup><strong>c</strong></sup>Sequence conservation features. ○: Yes, Blank: No. <sup><strong>d</strong></sup>Features included in the final version of our classifier. ○: included features, blank: features excluded during optimization steps.
{: .fs-2 }

---

### **Table S2**. Analysis of target site level feature influence. {#T:S2}
{: .text-caption }

{% include tbl_simple.html data=tabS2 %}

<sup><strong>a</strong></sup>ROC diff shows the difference of ROC scores between the classifier trained with all the features (0.7050) and classifiers trained with one feature removed.
{: .fs-2 }

---

### **Table S3**. mRNA level features. {#T:S3}
{: .text-caption }

{% include tbl_simple.html data=tabS3 %}

<sup><strong>a</strong></sup>Vector size used in SVM training. <sup><strong>b</strong></sup>Features included in the final version of our classifier. ○: included features, blank: features excluded during optimization steps.
{: .fs-2 }

---

### **Table S4**. Analysis of mRNA level feature influence. {#T:S4}
{: .text-caption }

{% include tbl_simple.html data=tabS4 %}

<sup><strong>a</strong></sup>ROC diff shows the difference of ROC scores between the classifier trained with all the features (0.7997) and classifiers trained with one feature removed.
{: .fs-2 }

---

### **Table S5**. Benchmarks on the Linsley dataset. {#T:S5}
{: .text-caption }

{% include tbl_simple.html data=tabS5 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S6**. mRNA/siRNA sequences from five microarray experiments. {#T:S6}
{: .text-caption }

{% include tbl_simple.html data=tabS6 %}

Jackson (GSE5814), Lim (GSE2075), Grimson (GSE8501), and Birmingham (E-MEXP-668) were used for training, and Linsley (GSE6838) was used for the independent test. Two datasets, Selbach and Baek, from mass spectrometry experiments were used as both training datasets (for the proteomics-based classifiers) and independent test sets (for the mRNA-based classifiers).
{: .fs-2 }

<sup><strong>a</strong></sup>MAPK14-193 has three different sample groups; (i) GSM133702 and GSM134468, (ii) GSM134488, and (iii) GSM134491. We assigned three different unique IDs to these groups, therefore they were treated as different sequences internally in our model.
{: .fs-2 }

---

### **Table S7**. Parameters used for the Needle software. {#T:S7}
{: .text-caption }

{% include tbl_simple.html data=tabS7 attr=page.tabs.tabS7_attr %}

The scoring matrix was generated based on the matrix used in the miRanda algorithm {% cite Enright2003 -f {{ bib }} %}.
{: .fs-2 }

---

### **Table S8**. Benchmarks on the Selbach dataset. {#T:S8}
{: .text-caption }

{% include tbl_simple.html data=tabS8 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S9**. Benchmarks on the Baek dataset. {#T:S9}
{: .text-caption }

{% include tbl_simple.html data=tabS9 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S10**. Benchmarks on the Linsley dataset – Positive records defined by log ratio -0.1. {#T:S10}
{: .text-caption }

{% include tbl_simple.html data=tabS10 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S11**. Benchmarks on the Linsley dataset – Positive records defined by log ratio -0.3. {#T:S11}
{: .text-caption }

{% include tbl_simple.html data=tabS11 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S12**. Benchmarks on the Selbach dataset – Positive records defined by log ratio -0.1. {#T:S12}
{: .text-caption }

{% include tbl_simple.html data=tabS12 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S13**. Benchmarks on the Selbach dataset – Positive records defined by log ratio -0.3. {#T:S13}
{: .text-caption }

{% include tbl_simple.html data=tabS13 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S14**. Benchmarks on the Baek dataset – Positive records defined by log ratio -0.1. {#T:S14}
{: .text-caption }

{% include tbl_simple.html data=tabS14 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

### **Table S15**. Benchmarks on the Baek dataset – Positive records defined by log ratio -0.3. {#T:S15}
{: .text-caption }

{% include tbl_simple.html data=tabS15 %}

<sup><strong>a</strong></sup>Positive and Negative show the total number of positive (down-regulated) and negative (unaffected) genes present within the six benchmarks (Method “All”) and among the predictions of each method on the six benchmarks. <sup><strong>b</strong></sup>ROC is the method’s ROC score on the specific benchmark.
{: .fs-2 }

---

## Supplementary Figures {#S:4}

### &nbsp; {#F:S1}
{: .no_toc }
![Figure S1]({{ figS1 }}){:width="{{ page.figs.figS1[1] }}"}

#### **Figure S1**. 10-fold cross-validation of target site level classifiers trained on three microarray datasets.
{: .text-caption }
The ROC graphs show the classification performance of four classifiers trained with three microarray datasets at the target site level. The curve is the average ROC curve of the ten individual cross-validation test results; error bars show standard errors. Dotted lines illustrate random prediction. Avg. AUC is the average of the area under the curve (AUC; ROC score) of the ten individual cross-validation test results. \
**(A)** Trained with the Birmingham, Lim and Grimson datasets. \
**(B)** Trained with the Jackson, Birmingham and Grimson datasets. \
**(C)** Trained with the Jackson, Lim and Grimson datasets. \
**(D)** Trained with the Jackson, Birmingham and Lim datasets.
{: .fs-2 }

---

### &nbsp; {#F:S2}
{: .no_toc }
![Figure S2]({{ figS2 }}){:width="{{ page.figs.figS2[1] }}"}

#### **Figure S2**. Density plot for the number of potential target sites divided by 3’UTR length.
{: .text-caption }
It shows the density distribution of the values calculated by the number of miRNA potential sites divided by the 3’ UTR length. The red line indicates the distribution of down-regulated genes whereas the blue line is for the non-affected genes. The difference between two density distributions is very significant (Kolmogorov-Smirnov test, p-value: 3.862e-11).
{: .fs-2 }

---

### &nbsp; {#F:S3}
{: .no_toc }
![Figure S3]({{ figS3 }}){:width="{{ page.figs.figS3[1] }}"}

#### **Figure S3**. Comparison between two SVM trainings with or without explicit addition of negative records.
{: .text-caption }
Two box plots show the number of potential target sites vs. discriminant values from mRNA level training. The left panel shows the distributions of discriminant values by the number of potential target sites for the classifier trained without any explicit additional of negative records. The right panel shows the classifier trained with data enriched with 1000 randomly selected non-target genes with more than 7 target sites. Records with the number of target sites >25 and/or negative discriminant values were disregarded. Whereas the left box plot shows that discriminant values for negative (non-downregulated) genes generally increase with increasing number of potential target sites, the right box plot indicates that the discriminant values for negative genes are relatively stable.
{: .fs-2 }

---

### &nbsp; {#F:S4}
{: .no_toc }
![Figure S4]({{ figS4 }}){:width="{{ page.figs.figS4[1] }}"}

#### **Figure S4**. 10-fold cross-validation of mRNA level classifiers trained on three microarray datasets.
{: .text-caption }
The ROC graphs show the classification performance of four classifiers trained with three different combinations of microarray datasets at the mRNA level. The curve is the average ROC curve of the ten individual cross-validation test results; error bars show standard errors. Dotted lines illustrate a random prediction. Avg. AUC is the average of the area under the curve (AUC; ROC score) of the ten individual cross-validation test results.  \
**(A)** Trained with the Birmingham, Lim and Grimson datasets.  \
**(B)** Trained with the Jackson, Birmingham and Grimson datasets.  \
**(C)** Trained with the Jackson, Lim and Grimson datasets.  \
**(D)** Trained with the Jackson, Birmingham and Lim datasets.
{: .fs-2 }

---

### &nbsp; {#F:S5}
{: .no_toc }
![Figure S5]({{ figS5 }}){:width="{{ page.figs.figS5[1] }}"}

#### **Figure S5**. Three method-specific benchmarks of 8 different algorithms on the Linsley dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms; SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2, and PicTar, on the Linsley dataset. Dotted lines illustrate random prediction. The values of the area under the ROC curve (AUC) are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with TargetScan dataset, **(B)** ROC with miRanda dataset, and **(C)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S6}
{: .no_toc }
![Figure S6]({{ figS6 }}){:width="{{ page.figs.figS6[1] }}"}

#### **Figure S6**. siRNA benchmarks on the Jackson dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performance of 3 different target prediction algorithms – SVM not trained on Jackson dataset (SVM), PITA, and TargetScan (TargetS) – on the Jackson dataset. The SVM classifier was trained with the Lim, Birmingham and Grimson datasets. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, and **(C)** ROC with 7mer + Conservation.
{: .fs-2 }

---

### &nbsp; {#F:S7}
{: .no_toc }
![Figure S7]({{ figS7 }}){:width="{{ page.figs.figS7[1] }}"}

#### **Figure S7**. miRNA benchmarks on the Lim dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM not trained on Lim dataset (SVM), PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Lim dataset. The SVM classifier was trained with the Jackon, Birmingham and Grimson datasets. Dotted lines illustrate random prediction. The values of the area under the ROC curve (AUC) are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with TargetScan dataset, **(B)** ROC with miRanda dataset, **(C)** ROC with PicTar dataset, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S8}
{: .no_toc }
![Figure S8]({{ figS8 }}){:width="{{ page.figs.figS8[1] }}"}

#### **Figure S8**. siRNA benchmarks on the Birmingham dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 3 different target prediction algorithms – SVM not trained on Birmingham dataset (SVM), PITA, and TargetScan (TargetS) – on the Birmingham dataset. The SVM classifier was trained with the Jackson, Lim and  Grimon datasets. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, and **(C)** ROC with 7mer + Conservation.
{: .fs-2 }

---

### &nbsp; {#F:S9}
{: .no_toc }
![Figure S9]({{ figS9 }}){:width="{{ page.figs.figS9[1] }}"}

#### **Figure S9**. miRNA benchmarks on the Grimson dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM not trained on Grimson dataset (SVM), PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Grimson dataset. The SVM classifier was trained with the Jackon, Lim, and Birmingham datasets. Dotted lines illustrate random prediction. The values of the area under the ROC curve (AUC) are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with TargetScan dataset, **(B)** ROC with miRanda dataset, **(C)** ROC with PicTar dataset, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S10}
{: .no_toc }
![Figure S10]({{ figS10 }}){:width="{{ page.figs.figS10[1] }}"}

#### **Figure S10**. Targets with optimal distance sites show higher average discriminant value than other three target types.
{: .text-caption }
The boxplot shows the comparison of mRNA level discriminant values among four different target types. The result shows our SVM approach gives scores as the preference: “multiple with optimal distance” > “multiple without optimal distance” > “single stringent” > “single non-stringent”.
{: .fs-2 }

---

### &nbsp; {#F:S11}
{: .no_toc }
![Figure S11]({{ figS11 }}){:width="{{ page.figs.figS11[1] }}"}

#### **Figure S11**. Adding site accessibility and sequence conservation features did not affect target prediction accuracy.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the classification performance of three mRNA level classifiers. These classifiers had the same mRNA level features, but their discriminant values were generated by three different target site classifiers: (i) neither site accessibility nor sequence conservation used, (ii) with site accessibility and, (iii) with conservational information. Panels A-C show the three classifiers’ 10-fold cross-validation performance. The curve is the average ROC curve of the ten individual cross-validation test results; error bars show standard errors; Avg. AUC is the average of the area under the curve (AUC; ROC score) of the ten individual cross-validation test results. Panels D-F show the three classifiers’ performance on the independent (Linsley) dataset; ROC graphs were plotted by only considering the genes with prediction scores in the Linsley dataset. Dotted lines illustrate random prediction.  \
**(A)** 10-fold cross-validation of the classifier with neither site accessibility nor sequence conservation used  \
**(B)** 10-fold cross-validation of the classifier with site accessibility  \
**(C)** 10-fold cross-validation of the classifier with sequence conservation  \
**(D)** Classifier with neither site accessibility nor conservational information tested on the independent dataset  \
**(E)** Classifier with site accessibility tested on the independent dataset  \
**(F)**  Classifier with sequence conservation tested on the independent dataset
{: .fs-2 }

---

### &nbsp; {#F:S12}
{: .no_toc }
![Figure S12]({{ figS12 }}){:width="{{ page.figs.figS12[1] }}"}

#### **Figure S12**. SVC performs better than SVR at both target site and mRNA levels.
{: .text-caption }
The ROC graphs show the prediction performance of SVM regression (SVR) and SVM classification (SVC). Panels **A**, **C**, **E**, and **G** show the models’ 10-fold cross-validation performance. The curve is the average ROC curve of the ten individual cross-validation test results; error bars show standard errors; Avg. AUC is the average of the area under the curve (AUC; ROC score) of the ten individual cross-validation test results. Panels **B**, **D**, **F**, and **H** show the models’ performance on the independent (Linsley) dataset; ROC graphs were plotted by only considering the genes with SVC and SVR prediction scores in the Linsley dataset. Dotted lines illustrate random prediction. SVR and SVC show very similar performance, but SVC shows slightly better performance than SVR at both target site and mRNA levels.  \
**(A)** 10-fold cross-validation of SVR target site level  \
**(B)** Target site level SVR classifier tested on the independent dataset  \
**(C)** 10-fold cross-validation of SVR mRNA level  \
**(D)** mRNA level SVR classifier tested on the independent dataset  \
**(E)** 10-fold cross-validation of SVC target site level  \
**(F)** Target site level SVC classifier tested on the independent dataset  \
**(G)** 10-fold cross-validation of SVC mRNA level  \
**(H)** mRNA level SVC classifier tested on the independent dataset
{: .fs-2 }

---

### &nbsp; {#F:S13}
{: .no_toc }
![Figure S13]({{ figS13 }}){:width="{{ page.figs.figS13[1] }}"}

#### **Figure S13**. SVM performance is similar between the training set with up-regulated genes and the one without up-regulated genes.
{: .text-caption }
The ROC graphs show the prediction performance of two SVM classifiers trained either with or without up-regulated genes. Panels **A**, **C**, **E**, and **G** show the models’ 10-fold cross-validation performance. The curve is the average ROC curve of the ten individual cross-validation test results; error bars show standard errors; Avg. AUC is the average of the area under the curve (AUC; ROC score) of the ten individual cross-validation test results. Panels **B**, **D**, **F**, and H show the models’ performance on the independent (Linsley) dataset; ROC graphs were plotted by only considering the genes with SVM prediction scores in the Linsley dataset. Dotted lines illustrate random prediction. Two classifiers show almost identical performances in terms of both ROC sores and ROC curves.  \
**(A)** 10-fold cross-validation of SVM without up-regulated genes at target site level  \
**(B)** Target site level SVM without up-regulated genes tested on the independent dataset  \
**(C)** 10-fold cross-validation of SVM without up-regulated genes at mRNA level  \
**(D)** mRNA level SVM without up-regulated genes tested on the independent dataset  \
**(E)** 10-fold cross-validation of SVM with up-regulated genes at target site level  \
**(F)** Target site level SVM with up-regulated genes tested on the independent dataset  \
**(G)** 10-fold cross-validation of SVM with up-regulated genes at mRNA level  \
**(H)** mRNA level SVM with up-regulated genes tested on the independent dataset
{: .fs-2 }

---

### &nbsp; {#F:S14}
{: .no_toc }
![Figure S14]({{ figS14 }}){:width="{{ page.figs.figS14[1] }}"}

#### **Figure S14**. Two-step SVM retains the performance when trained with proteomics data.
{: .text-caption }
**(A)** SVM classifier was trained by the Selbach and Baek datasets. The definitions of the error bars, AUC, true positive and false positive rates were the same as described in Figure [2]({{ page_main }}#F:2). **(B)** Both proteomics and transcriptomics classifiers were tested on the Linsley dataset.  Proteomics data contains the Selbach and Baek datasets, whereas Transcriptomics contains the Jackson, Lim, Birmingham, and Grimson datasets. The ROC scores were shown in the legend box.
{: .fs-2 }

 ---

### &nbsp; {#F:S15}
{: .no_toc }
![Figure S15]({{ figS15 }}){:width="{{ page.figs.figS15[1] }}"}

#### **Figure S15**. Benchmarks on the Selbach dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Selbach dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. The benchmarks used for the evaluation were, **(A)** ROC with TargetScan dataset, **(B)** ROC with miRanda dataset, and **(C)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S16}
{: .no_toc }
![Figure S16]({{ figS16 }}){:width="{{ page.figs.figS16[1] }}"}

#### **Figure S16**. Benchmarks on the Baek dataset.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Baek dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with TargetScan dataset, **(B)** ROC with miRanda dataset, and **(C)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S17}
{: .no_toc }
![Figure S17]({{ figS17 }}){:width="{{ page.figs.figS17[1] }}"}

#### **Figure S17**. Benchmarks on the Linsley dataset with positive record threshold by log ratio -0.1.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Linsley dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. Positive records (down-regulated) were selected by log ratio value -0.1 instead of the default value -0.2. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, **(C)** ROC with 7mer + Conservation, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S18}
{: .no_toc }
![Figure S18]({{ figS18 }}){:width="{{ page.figs.figS18[1] }}"}

#### **Figure S18**. Benchmarks on the Linley dataset with positive record threshold by log ratio -0.3.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Linsley dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. Positive records (down-regulated) were selected by log ratio value -0.3 instead of the default value -0.2. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, **(C)** ROC with 7mer + Conservation, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S19}
{: .no_toc }
![Figure S19]({{ figS19 }}){:width="{{ page.figs.figS19[1] }}"}

#### **Figure S19**. Benchmarks on the Selbach dataset with positive record threshold by log ratio -0.1.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Selbach dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. Positive records (down-regulated) were selected by log ratio value -0.1 instead of the default value -0.2. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, **(C)** ROC with 7mer + Conservation, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S20}
{: .no_toc }
![Figure S20]({{ figS20 }}){:width="{{ page.figs.figS20[1] }}"}

#### **Figure S20**. Benchmarks on the Selbach dataset with positive record threshold by log ratio -0.3.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Selbach dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. Positive records (down-regulated) were selected by log ratio value -0.3 instead of the default value -0.2. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, **(C)** ROC with 7mer + Conservation, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S21}
{: .no_toc }
![Figure S21]({{ figS21 }}){:width="{{ page.figs.figS21[1] }}"}

#### **Figure S21**. Benchmarks on the Baek dataset with positive record threshold by log ratio -0.1.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Baek dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. Positive records (down-regulated) were selected by log ratio value -0.1 instead of the default value -0.2. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, **(C)** ROC with 7mer + Conservation, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

### &nbsp; {#F:S22}
{: .no_toc }
![Figure S22]({{ figS22 }}){:width="{{ page.figs.figS22[1] }}"}

#### **Figure S22**. Benchmarks on the Baek dataset with positive record threshold by log ratio -0.3.
{: .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Baek dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. Positive records (down-regulated) were selected by log ratio value -0.3 instead of the default value -0.2. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, **(C)** ROC with 7mer + Conservation, **(D)** ROC with TargetScan dataset, **(E)** ROC with miRanda dataset, and **(F)** ROC with PicTar dataset.
{: .fs-2 }

---

## References {#S:5}
{% bibliography --cited_in_order -f {{ bib }} %}
