---
layout: default
title: "Supplementary information"
parent: Biological experiments
description: "Supplementary information: ﻿﻿Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments"
comments: true
nav_order: 3
group: confounding
tabs:
  tabS1: tableS1
  tabS2: tableS2
  tabS3: tableS3
  tabS4: tableS4
  tabS5: tableS5
  tabS6: tableS6
  tabS7: tableS7
  tabS8: tableS8
  tabS9: tableS9
  tabS10: tableS10
  tabS11: tableS11
  tabS12: tableS12
  tabS13: tableS13
  tabS14: tableS14
  tabS15: tableS15
  tabS16: tableS16
  tabS17: tableS17
  tabS18: tableS18
  tabS19: tableS19
  tabS20: tableS20
  tabS21: tableS21
  tabS22: tableS22
  tabS23: tableS23
figs:
  figS1: [mirna-target-gene-expression-microarrays.webp, 800]
  figS2: [endogenous-exogenous-mirna-target-microarray-vs-proteomics.webp, 800]
  figS3: [mirna-target-counts-and-rnaseq-expression.webp, 500]
  figS4: [linear-regression-mirna-target-8-features-with-crossing.webp, 800]
  figS5: [linear-regression-mirna-target-9-features-with-crossing.webp, 800]
---

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
{% assign tabS17 = tab_arr[page.tabs.tabS17] %}
{% assign tabS18 = tab_arr[page.tabs.tabS18] %}
{% assign tabS19 = tab_arr[page.tabs.tabS19] %}
{% assign tabS20 = tab_arr[page.tabs.tabS20] %}
{% assign tabS21 = tab_arr[page.tabs.tabS21] %}
{% assign tabS22 = tab_arr[page.tabs.tabS22] %}
{% assign tabS23 = tab_arr[page.tabs.tabS23] %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture figS1 %}{{ fig_dir }}/{{ page.figs.figS1[0] }}{% endcapture %}
{% capture figS2 %}{{ fig_dir }}/{{ page.figs.figS2[0] }}{% endcapture %}
{% capture figS3 %}{{ fig_dir }}/{{ page.figs.figS3[0] }}{% endcapture %}
{% capture figS4 %}{{ fig_dir }}/{{ page.figs.figS4[0] }}{% endcapture %}
{% capture figS5 %}{{ fig_dir }}/{{ page.figs.figS5[0] }}{% endcapture %}

# ﻿Supplementary information: ﻿Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments
{: .no_toc .text-center }

Takay Saito<sup>1</sup> and Pål Sætrom<sup>1,2</sup>
{: .text-center }

<iframe src="https://widgets.figshare.com/articles/14923761/embed?show_title=0" width="100%" height="351" allowfullscreen frameborder="0"></iframe>

<div class="code-example">
<strong>Citation:</strong> <br />
Saito, T and Sætrom, P. Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments. <i>Silence</i> <strong>3,</strong> 3 (2012).
<a href="https://doi.org/10.1186/1758-907X-3-3">https://doi.org/10.1186/1758-907X-3-3</a>.
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

## Supplementary Tables {#S:1}
### **Table S1**. Summary of miRNA high-throughput experiments. {#T:S1}
{: .text-caption }

{% include tbl_simple.html data=tabS1 %}

* Type: types of experiments as Micrroarray overexpression (M), Proteomics overexpression (P), Microarray inhibition (M_OME), and Proteomics inhibition (P_LNA).letter-spacing
{: .fs-2 }

---

### **Table S2**. Samples and miRNAs of miRNA high-throughput experiments. {#T:S2}
{: .text-caption }

{% include tbl_simple.html data=tabS2 %}

* Sample ID: GEO Sample IDs for microarray experiments. Sample IDs are equivalent with Internal miRNA IDs for Baek MA, Baek, Selbach LNA, Selbach MA, and Selbach.
{: .fs-2 }

---

### **Table S3**. P-values of multiple Wilcoxon rank-sum tests on 5 subgroups of 3' UTR length. {#T:S3}
{: .text-caption }

{% include tbl_simple.html data=tabS3 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=50) 0.001, respectively.
{: .fs-2 }

---

### **Table S4**. P-values of multiple Wilcoxon rank-sum tests on 4 subgroups of 3' UTR conservation. {#T:S4}
{: .text-caption }

{% include tbl_simple.html data=tabS4 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=40) 0.0013, respectively.
{: .fs-2 }

---

### **Table S5**. P-values of multiple Wilcoxon rank-sum tests on 6 subgroups of mRNA expression. {#T:S5}
{: .text-caption }

{% include tbl_simple.html data=tabS5 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=60) 0.00086, respectively.
{: .fs-2 }

† The expression levels were measured for the HeLa cells, but some other cell line was used in the Linsley experiment. It is included only for comparison purpose.
{: .fs-2 }

---

### **Table S6**. P-values of multiple Kolmogorov–Smirnov tests on 5 subgroups of 3' UTR length. {#T:S6}
{: .text-caption }

{% include tbl_simple.html data=tabS6 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=50) 0.001, respectively.
{: .fs-2 }

---

### **Table S7**. P-values of multiple Kolmogorov–Smirnov tests on 4 subgroups of 3' UTR conservation. {#T:S7}
{: .text-caption }

{% include tbl_simple.html data=tabS7 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=40) 0.0013, respectively.
{: .fs-2 }

---

### **Table S8**. P-values of multiple Kolmogorov–Smirnov tests on 6 subgroups of mRNA expression. {#T:S8}
{: .text-caption }

{% include tbl_simple.html data=tabS8 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=60) 0.00086, respectively.
{: .fs-2 }

† The expression levels were measured for the HeLa cells, but some other cell line was used in the Linsley experiment. It is included only for comparison purpose.
{: .fs-2 }

---

### **Table S9**. Sample level scores of Wilcoxon rank-sum tests on 3' UTR length. {#T:S9}
{: .text-caption }

{% include tbl_simple.html data=tabS9 %}

We performed the same Wilcoxon rank-sum tests as in Table S3 on samples instead of experiments. We then counted the number of samples that had a significant p-value (<0.05) to calculate the proportion per experiment as Sample level score. "\*" and "**" are added when the score is between 0 and 0.5, and >0.5, respectively.
{: .fs-2 }

---

### **Table S10**. Sample level scores of Wilcoxon rank-sum tests on 3' UTR conservation. {#T:S10}
{: .text-caption }

{% include tbl_simple.html data=tabS10 %}

We performed the same Wilcoxon rank-sum tests as in Table S4 on samples instead of experiments. We then counted the number of samples that had a significant p-value (<0.05) to calculate the proportion per experiment as Sample level score. "\*" and "**" are added when the score is between 0 and 0.5, and >0.5, respectively.
{: .fs-2 }

---

### **Table S11**. Sample level scores of Wilcoxon rank-sum tests on mRNA expression. {#T:S11}
{: .text-caption }

{% include tbl_simple.html data=tabS11 %}

We performed the same Wilcoxon rank-sum tests as in Table S5 on samples instead of experiments. We then counted the number of samples that had a significant p-value (<0.05) to calculate the proportion per experiment as Sample level score. "\*" and "**" are added when the score is between 0 and 0.5, and >0.5, respectively.
{: .fs-2 }

† The expression levels were measured for the HeLa cells, but some other cell line was used in the Linsley experiment. It is included only for comparison purpose.
{: .fs-2 }

---

### **Table S12**. The number of genes for four gene groups, T -Endo, T +Endo, NT -Endo, and NT -Endo, per experiment. {#T:S12}
{: .text-caption }

{% include tbl_simple.html data=tabS12 %}

---

### **Table S13**. P-values of multiple Wilcoxon rank-sum tests between T -Endo and T +Endo on 5 subgroups of 3' UTR length. {#T:S13}
{: .text-caption }

{% include tbl_simple.html data=tabS13 %}

Lower p-values indicate that a set of T -Endo genes is more down-regulated than T +Endo genes. “\*” and “**” are added when the p-value is less than 0.05 and Sidak adjusted (n=50) 0.001, respectively.
{: .fs-2 }

† Endogenous miRNAs of the HeLa cells were used to determine if a gene was influenced by any endogenous miRNAs or not (see the Methods). Although some other cell line was used in the Linsley experiment, it is included only for comparison purpose.
{: .fs-2 }

†† Two inhibition experiments, Selbach LNA and Linsley OME, were excluded as they inhibited endogenous miRNAs in the HeLa cells.
{: .fs-2 }

---

### **Table S14**. P-values of multiple Wilcoxon rank-sum tests between T -Endo and T +Endo on 5 subgroups of 3' UTR conservation. {#T:S14}
{: .text-caption }

{% include tbl_simple.html data=tabS14 %}

Lower p-values indicate that a set of T -Endo genes is more down-regulated than T +Endo genes. “\*” and “**” are added when the p-value is less than 0.05 and Sidak adjusted (n=40) 0.0013, respectively.
{: .fs-2 }

† Endogenous miRNAs of the HeLa cells were used to determine if a gene was influenced by any endogenous miRNAs or not (see the Methods). Although some other cell line was used in the Linsley experiment, it is included only for comparison purpose.
{: .fs-2 }

†† Two inhibition experiments, Selbach LNA and Linsley OME, were excluded as they inhibited endogenous miRNAs in the HeLa cells.
{: .fs-2 }

---

### **Table S15**. P-values of multiple Wilcoxon rank-sum tests between T -Endo and T +Endo on 5 subgroups of mRNA expression. {#T:S15}
{: .text-caption }

{% include tbl_simple.html data=tabS15 %}

Lower p-values indicate that a set of T -Endo genes is more down-regulated than T +Endo genes. “\*” and “**” are added when the p-value is less than 0.05 and Sidak adjusted (n=60) 0.00086, respectively.
{: .fs-2 }

† Endogenous miRNAs of the HeLa cells were used to determine if a gene was influenced by any endogenous miRNAs or not (see the Methods). Although some other cell line was used in the Linsley experiment, it is included only for comparison purpose.
{: .fs-2 }

†† Two inhibition experiments, Selbach LNA and Linsley OME, were excluded as they inhibited endogenous miRNAs in the HeLa cells.
{: .fs-2 }

---

### **Table S16**. Comparisons of Wilcoxon rank-sum tests for T -Endo against T +Endo between experimental and individual sample levels. {#T:S16}
{: .text-caption }

{% include tbl_simple.html data=tabS16 %}

Expr: the number of experiments that have significant p-value. Smpl: the number of experiments that have Sample level scores greater than either 0.0 (>0.0) or 0.5 (>0.5).
{: .fs-2 }

---

### **Table S17**. Coefficients and p-values of linear regression with eight factors. {#T:S17}
{: .text-caption }

{% include tbl_simple.html data=tabS17 %}

---

### **Table S18**. Coefficients and p-values of linear regression with eight factors and factor crossing. {#T:S18}
{: .text-caption }

{% include tbl_simple.html data=tabS18 %}

---

### **Table S19**. Coefficients and p-values of linear regression with nine factors. {#T:S19}
{: .text-caption }

{% include tbl_simple.html data=tabS19 %}

---

### **Table S20**. Coefficients and p-values of linear regression with nine factors and factor crossing. {#T:S20}
{: .text-caption }

{% include tbl_simple.html data=tabS20 %}

---

### **Table S21**. P-values of multiple Wilcoxon rank-sum tests on 3 subgroups of CpG frequency. {#T:S21}
{: .text-caption }

{% include tbl_simple.html data=tabS21 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=30) 0.0017, respectively.
{: .fs-2 }

---

### **Table S22**. P-values of multiple Wilcoxon rank-sum tests on 2 subgroups of developmental genes. {#T:S22}
{: .text-caption }

{% include tbl_simple.html data=tabS22 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=20) 0.0026, respectively.
{: .fs-2 }

---

### **Table S23**. P-values of multiple Wilcoxon rank-sum tests on 2 subgroups of housekeeping genes. {#T:S23}
{: .text-caption }

{% include tbl_simple.html data=tabS23 %}

Lower p-values indicate that a set of genes in one sub-group is more down-regulated than a set of genes in the rest of subgroups. "\*" and "**" are added when the p-value is less than 0.05 and Sidak adjusted (n=20) 0.0026, respectively.
{: .fs-2 }

---

## Supplementary Figures  {#S:2}

### &nbsp; {#F:S1}
{: .no_toc }
![Figure S1]({{ figS1 }}){:width="{{ page.figs.figS1[1] }}"}

#### **Figure S1**. mRNA expression levels from 6 microarray and 2 proteomics experiments.
{: .text-caption }
We calculated the ratios of tag counts of RNASeq for each sub-group relative to the total counts for 6 microarray (A-G) and 2 proteomics (G and H) experiments. The experiment data were divided into four by exogenous miRNA targets (T) and non-targets (NT), as well as endogenous miRNA targets (+E) and non-targets (-E).
{: .fs-2 }

\* Endogenous miRNAs of the HeLa cells were used to determine if a gene was influenced by any endogenous miRNAs or not (see the Methods). Although some other cell line was used in the Linsley experiment, it is included only for comparison purpose.
{: .fs-2 }

† As two inhibition experiments, Selbach LNA and Linsley OME, inhibited endogenous miRNAs in the HeLa cells, there were no genes categorized as T -Endo.
{: .fs-2 }

---

### &nbsp; {#F:S2}
{: .no_toc }
![Figure S2]({{ figS2 }}){:width="{{ page.figs.figS2[1] }}"}

#### **Figure S2**. Log2 enrichment of down-regulated genes compared with all genes mRNA.
{: .text-caption }
Scatter plots show log2 enrichment of down-regulated genes compared with all genes for the six sub-groups of mRNA expression levels in all studied datasets subdivided by predicted exogenous and endogenous miRNA targeting. Lines and shaded grays show respectively linear fits and standard errors for the microarray (red dots) and proteomics (blue triangles) experiments; p-values (lower left) are unadjusted p-values from Pearson correlation tests. Data points based on a single gene were excluded. The regression lines show that in the microarray but not the proteomics experiments, down-regulated genes are enriched among highly expressed genes and that this enrichment depends on gene expression levels.
{: .fs-2 }

---

### &nbsp; {#F:S3}
{: .no_toc }
![Figure S3]({{ figS3 }}){:width="{{ page.figs.figS3[1] }}"}

#### **Figure S3**. Scatter plot of the total tag counts versus total number of miRNA target sites.
{: .text-caption }
We plotted a scatter plots to check the correlation between mRNA expression level and the number of miRNA target sites. The plot shows the total tag counts and the total number of miRNA target sites from 67 samples with 32 miRNAs and 35 siRNAs. The line was drawn by Pearson’s correlation (r = 0.973 and p 2.2e-16). Only the samples assayed in HeLa were included. Red circles represent miRNAs, whereas blue triangles represent siRNAs.
{: .fs-2 }

---

### &nbsp; {#F:S4}
{: .no_toc }
![Figure S4]({{ figS4 }}){:width="{{ page.figs.figS4[1] }}"}

#### **Figure S4**. Coefficients of a linear regression with eight factors and factor crossing.
{: .text-caption }
The dot plot shows the coefficients of the liner model with formula: -logratio = (ln3 + cs3 + exp + #site_m + #endo_m + #site_s + p_ma + e_oe)^2. The ^ operator extracts all eight factors as well as all possible combinations of second order interactions, such as ln3 * cs3 (ln3:cs3), ln3 * exp (ln3:exp), and so on. The size of dots indicates -log10p as the negation of the logarithm of p-values to base 10. Positive coefficients associate with miRNA down-regulation.
{: .fs-2 }

---

### &nbsp; {#F:S5}
{: .no_toc }
![Figure S5]({{ figS5 }}){:width="{{ page.figs.figS5[1] }}"}

#### **Figure S5**. Coefficients of a linear regression with nine factors and factor crossing.
{: .text-caption }
The dot plot shows the coefficients of the liner model with formula: -logratio = (ln3 + cs3 + exp + #site_m + #endo_m + #site_s + p_ma + e_oe + ts_score)^2. The ^ operator extracts all eight factors as well as all possible combinations of second order interactions, such as ln3 * cs3 (ln3:cs3), ln3 * exp (ln3:exp), and so on. The size of dots indicates -log10p as the negation of the logarithm of p-values to base 10. Positive coefficients associate with miRNA down-regulation.
{: .fs-2 }
