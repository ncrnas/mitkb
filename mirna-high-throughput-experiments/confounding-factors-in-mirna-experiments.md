---
layout: default
title: "Research: Confounding"
parent: Biological experiments
description: "﻿Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments"
nav_order: 2
group: confounding
folders:
  experiment: mirna-high-throughput-experiments
pages:
  suppl_info: confounding-factors-in-mirna-experiments-supplementary-information
tabs:
  tab1: table1
  tab2: table2
  tab3: table3
  tab4: table4
figs:
  fig1: [three-prime-length-conservation-expression.webp, 800]
  fig2: [endogenous-vs-exogenous-microrna-features.webp, 500]
  fig3: [mirna-target-features-microarray-vs-proteomics.webp, 800]
  fig4: [mirna-target-dilution-effect-log-ratio.webp, 500]
  fig5: [linear-regression-mirna-target-8-features.webp, 500]
  fig6: [linear-regression-mirna-target-9-features.webp, 500]
  fig7: [strong-mirna-target-factors-in-microarrays.webp, 500]
scholar:
  bibliography: confounding
---

{% capture page_suppl_info %}{{ site.baseurl }}/{{ page.folders.experiment }}/{{ page.pages.suppl_info }}{% endcapture %}

{% assign tab_arr = site.data[page.group] %}
{% assign tab1 = tab_arr[page.tabs.tab1] %}
{% assign tab2 = tab_arr[page.tabs.tab2] %}
{% assign tab3 = tab_arr[page.tabs.tab3] %}
{% assign tab4 = tab_arr[page.tabs.tab4] %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture fig1 %}{{ fig_dir }}/{{ page.figs.fig1[0] }}{% endcapture %}
{% capture fig2 %}{{ fig_dir }}/{{ page.figs.fig2[0] }}{% endcapture %}
{% capture fig3 %}{{ fig_dir }}/{{ page.figs.fig3[0] }}{% endcapture %}
{% capture fig4 %}{{ fig_dir }}/{{ page.figs.fig4[0] }}{% endcapture %}
{% capture fig5 %}{{ fig_dir }}/{{ page.figs.fig5[0] }}{% endcapture %}
{% capture fig6 %}{{ fig_dir }}/{{ page.figs.fig6[0] }}{% endcapture %}
{% capture fig7 %}{{ fig_dir }}/{{ page.figs.fig7[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# ﻿Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments
{: .no_toc .text-center }

Takay Saito<sup>1</sup> and Pål Sætrom<sup>1,2</sup>
{: .text-center }

<strong><sup>1</sup></strong>Department of Cancer Research and Molecular Medicine,  \
Norwegian University of Science and Technology, NO-7489 Trondheim, Norway \
<strong><sup>2</sup></strong>Department of Computer and Information Science, \
Norwegian University of Science and Technology, NO-7491 Trondheim, Norway
{: .fs-3 .text-center .text-grey-dk-000 }

<br />
[View PDF](https://link.springer.com/content/pdf/10.1186/1758-907X-3-3.pdf){: .btn }
<div class="code-example">
<strong>Citation:</strong> <br />
Saito, T and Sætrom, P. Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments. <i>Silence</i> <strong>3,</strong> 3 (2012).
<a href="https://doi.org/10.1186/1758-907X-3-3">https://doi.org/10.1186/1758-907X-3-3</a>.
</div>
{: .bg-grey-lt-000 .p-3 }

<br />

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Abstract {#S:1}
### Background
{: .no_toc }
MicroRNA (miRNA) target genes tend to have relatively long and conserved 3' UTRs, but to what degree these characteristics contribute to miRNA targeting is poorly understood. Different high-throughput experiments have for example shown that miRNAs preferentially regulate genes with both short and long 3' UTRs and that target site conservation is both important and irrelevant for miRNA targeting.

### Results
{: .no_toc }
We have analyzed several gene context-dependent features, including 3' UTR length, 3' UTR conservation, and mRNA expression levels, reported to have conflicting influence on miRNA regulation. By taking into account confounding factors such as technology-dependent experimental bias and competition between transfected and endogenous miRNAs, we show that two factors – target gene expression and competition – could explain most of the previously reported experimental differences. Moreover, we find that these and other target site-independent features explain about the same amount of variation in target gene expression as the target site-dependent features included in the TargetScan model.

### Conclusions
{: .no_toc }
Our results show that it is important to consider confounding factors when interpreting miRNA high throughput experiments and urge especial caution when using microarray data to compare average regulatory effects between groups of genes that have different average gene expression levels.

## Keywords
{: .no_toc }
microRNA targets, siRNA, microarray, proteomics, PAR-CLIP

## Background {#S:2}
MicroRNAs (miRNAs) are an abundant class of small non-coding RNAs (ncRNAs) that negatively regulate protein-coding genes {% cite Ambros2004 Bartel2004 -f {{ bib }} %}. MicroRNAs are involved in many important regulatory roles {% cite Hwang2007 Stefani2008 Croce2009 -f {{ bib }} %}, and current estimates indicate that miRNAs regulate at least 60% of the human protein-coding genes {% cite Friedman2009 -f {{ bib }} %}.

In animals, functional miRNA sites preferentially reside in 3' UTRs {% cite Bartel2009 -f {{ bib }} %}, and these sites are generally well conserved {% cite Friedman2009 -f {{ bib }} %}. Moreover, some ubiquitously expressed genes, such as housekeeping genes, have shorter 3' UTRs to potentially avoid miRNA regulation {% cite Bartel2004 Stark2005 -f {{ bib }} %}, whereas proliferating cells express mRNAs with shortened 3' UTRs to avoid miRNA regulation {% cite Sandberg2008 -f {{ bib }} %}. Hence, miRNA target genes are likely to have relatively long and conserved 3' UTRs. However, what degree the length and conservation of 3' UTR contribute to miRNA targeting is still poorly understood. To illustrate, data from Argonaute immunoprecipitation (RIP) in human and fly indicate that miRNAs target short 3' UTRs {% cite Hausser2009 Hong2009 -f {{ bib }} %}, whereas microarray data from miRNA transfection experiments and sequence data from Argonaute cross-linked immunoprecipitation (CLIP) experiments indicate that miRNAs target long 3' UTRs {% cite Wen2011 -f {{ bib }} %}. Wen and colleagues also found that target site conservation was more important for CLIP-supported target sites than for targets that were down-regulated in the transfection experiments {% cite Wen2011 -f {{ bib }} %}. Moreover, our previous study {% cite Saito2010 -f {{ bib }} %} showed that genes with a 3' UTR longer than 4000 nucleotides were less affected by ectopically expressed miRNAs than were genes with a shorter 3' UTR, and that target site conservation had little or no effect on our miRNA target prediction algorithm’s performance.

In addition to 3' UTR length and conservation, several other gene characteristics also affect miRNA regulation. For example, many miRNAs are known to regulate genes involved in cell development processes {% cite Stefani2008 -f {{ bib }} %}. Another example is that miRNAs appear to preferentially target genes with high CpG promoters {% cite Sinha2008 -f {{ bib }} %}. Also, as highly expressed genes transcribe a large number of mRNAs, the miRNA regulation of those mRNAs can be different from those of weakly expressed genes, although current analyses disagree on whether miRNAs affect highly expressed genes more or less than medium or lowly expressed genes {% cite Hafner2010 Larsson2010 -f {{ bib }} %}.

High throughput experiments based on microarrays or proteomics have been important for characterizing miRNA regulation {% cite Lim2005 Grimson2007 Baek2008 Selbach2008 -f {{ bib }} %}. Although these and more recent comparative studies {% cite Hausser2009 Wen2011 -f {{ bib }} %} found that some features such as seed complementarity and seed strength are consistently important for miRNA targeting, other features such as 3' UTR length and site conservation mentioned above differ between studies and technologies. There are at least three potential features that may contribute to the difference between miRNA high-throughput experiments. First, the number of genes that cover a microarray experiment is usually much larger than that of a proteomics experiment. For instance, Baek et al. {% cite Baek2008 -f {{ bib }} %} used both microarray and proteomics for their miRNA target gene analysis, and the number of genes detected for microarray and proteomics samples were about 20000 and 2000, respectively. Second, transfected (exogenous) miRNAs compete with endogenous miRNAs for the protein complex needed for miRNA regulation {% cite Khan2009 -f {{ bib }} %}. Therefore, genes targeted by endogenous miRNAs but not by the exogenous miRNA can be up-regulated. Third, the effect of miRNA regulation can be diluted by target abundance, which means that each target gene is less down-regulated when the miRNA has many highly expressed compared with few lowly expressed target genes {% cite Arvey2010 -f {{ bib }} %}. Common for these features is that they are target site-independent, but gene context-dependent.

In this study, we have investigated the effects on miRNA targeting of several such target site-independent but gene context-dependent features. We categorized these features into three types: (i) target mRNA features, as 3' UTR length, 3' UTR sequence conservation, and mRNA expression level; (ii) sample features, as the competition and dilution effects; and (iii) platform features, as different types of technologies and experimental methods. We found that two features – the competition effect between endogenous miRNAs and transfected miRNAs, and mRNA expression level – have a strong impact on results from high throughput experiments. Both features are confounding factors that explain many of the previously reported differences between different studies and high throughput technologies. Considering these confounding factors is important to analyze accurately and robustly different types of miRNA high-throughput experiments and to infer correctly the characteristics of miRNA regulation.

## Results and discussion {#S:3}
### Target mRNA features: Ectopic miRNA expression differentially affects subgroups of genes with differing 3' UTR length, 3' UTR conservation, and mRNA expression level. {#S:3-1}

As we expected that mRNAs targeted by miRNA have long and conserved 3' UTRs, we wanted to examine how these characteristics actually affect miRNA regulation. Specifically, we wondered whether there was a difference in how different gene groups, such as genes with long, medium, or short 3' UTRs or genes with high, medium, or low 3' UTR conservation, were affected by ectopic miRNA expression. To address this question, we used microarray and proteomics data from five and two miRNA transfection experiments, respectively, and microarray data from two miRNA inhibition experiments and analyzed the differences in gene expression log ratio values of predicted targets in the different gene groups (see [Methods](#S:5-1)). We also included microarray data from a siRNA transfection experiment, as siRNAs behave as miRNAs in terms of target recognition {% cite Birmingham2006 Jackson2006 -f {{ bib }} %}. In contrast to evolutionary selected miRNA targets, however, targets for artificially designed exogenous siRNAs should be evolutionary unbiased. The siRNA dataset therefore served as an estimate of the general regulatory effects of over-expressing small RNAs. In total, we used 10 different types of miRNA high-throughput experiments, which covered 140 samples and 70 miRNAs and siRNAs (Table [S1]({{ page_suppl_info }}#T:S1) and [S2]({{ page_suppl_info }}#T:S2)) in the Supplementary information).

We first, for each miRNA and siRNA, separated predicted miRNA or siRNA target genes from the rest. The predicted target genes were genes that have at least one canonical seed site in their 3' UTRs (see [Methods](#S:5-2)). We used the set of predicted miRNA or siRNA target genes to analyze miRNA down-regulation effects on three different target mRNA features: (i) 3' UTR length, (ii) 3' UTR conservation, and (iii) mRNA expression level as determined by RNA-Seq counts. We split these three features into smaller sub-groups as described in the [Methods](#S:5-2) section. We then used a one-sided Wilcoxon rank-sum test to determine whether the predicted target genes in one sub-group were significantly more down-regulated than the genes in the rest of the sub-groups (Fig. [1](#F:1)). To illustrate, Fig. [1](#F:1)A and [1](#F:2)B show the cumulative density plots of the log-ratio values for the 3' UTR length sub-groups on the Lim microarray and Selbach proteomics datasets. In the Lim dataset (Fig. [1](#F:1)A), the sub-group Med Short, representing genes with 3' UTRs in the range of 248-629 nts, was significantly left-shifted and therefore more down-regulated than the rest as indicated in the corresponding heatmap (Fig. [1](#F:1)C; p-value 4.02e-17; Table [S3]({{ page_suppl_info }}#T:S3) in the Supplementary information). In the Selbach proteomics dataset (Fig. [1](#F:1)B), the Short sub-group was most shifted to the left compared to the others, but the differences were not as significant as in the Lim dataset – likely due to the smaller dataset (Fig. [1](#F:1)C; p-value 0.02; Table [S3]({{ page_suppl_info }}#T:S3) in the Supplementary information). Tables [S3]({{ page_suppl_info }}#T:S3)-[S5]({{ page_suppl_info }}#T:S5) in the Supplementary Information summarize all p-values of one-sided Wilcoxon rank-sum test on 3' UTR length, 3' UTR conservation, and mRNA expression; Kolmogorov–Smirnov tests on the same sub-groups gave similar results (Tables [S6]({{ page_suppl_info }}#T:S6)-[S8]({{ page_suppl_info }}#T:S8) in the Supplementary Information). The following sections describe and discuss the results for each target mRNA feature.

#### &nbsp; {#F:1}
{: .no_toc }
![Figure 1]({{ fig1 }}){:width="{{ page.figs.fig1[1] }}"}

##### **Figure 1**. Heatmaps show effects of ectopic miRNA regulation for sub-groups of 3' UTR length, 3' UTR conservation, and mRNA expression level.
{: .no_toc .text-caption }
Three heat maps show -log (base 2) transformed p-values for **(C)** 3' UTR length, **(D)** 3' UTR conservation, and **(E)** mRNA expression. We added two cumulative density plots for Lim **(A)** and Selbach **(B)** to illustrate the multiple non-parametric tests for the sub-groups of 3' UTR lengths; “All” is the cumulative density for all the genes measured in the experiment and represents the reference distribution. “All” genes include both predicted miRNA target and non-target genes. Although the mRNA expression data **(E)** was cell type specific and for HeLa cells, we included the Linsley dataset (from HCT116 and DLD-1 colon tumor cells) in the heat map for comparison purpose (indicated with “*”). The color labels under the dendrogram represent green for microarray of transfection assay, gray for proteomics of transfection assay, and orange for both microarray and proteomics with inhibition assay.
{: .fs-2 }

---

### Target mRNA features: Predicted target genes with short 3' UTRs are more down-regulated than genes with long 3' UTRs. {#S:3-2}
We have previously reported that genes with very long 3' UTRs (>4000 nts) are poor targets for ectopically expressed miRNAs or siRNAs {% cite Saito2010 -f {{ bib }} %}. Consistent with this, there was no experiment that showed significant down-regulation for the Very Long sub-group (Fig. [1](#F:1)C , Table [S3]({{ page_suppl_info }}#T:S3) in the Supplementary information). Interestingly, genes with short or medium 3' UTRs (Short, Med Short, and Med Long) were significantly down-regulated compared to genes with long 3' UTRs (Long and Very Long) among nearly all of the experiments. We saw the strongest effect for 3' UTRs with sub-groups Med Short and Med Long, as one or both groups were significantly down-regulated compared to other predicted targets in 8 of 10 experiments (Table [S3]({{ page_suppl_info }}#T:S3) in the Supplementary Information). Between these two sub-groups, Med Short had lower p-values than Med Long in 7 of 10 experiments. Using the one-sided Kolmogorov–Smirnov test as an alternative test method also supported the same trends (Table [S6]({{ page_suppl_info }}#T:S6) in the Supplementary Information). These results indicate that miRNA or siRNA target genes with short 3' UTRs were generally more down-regulated than genes with long 3' UTRs.

### Target mRNA features: Conservation in 3' UTR regions has inconsistent regulatory effects. {#S:3-3}
Although the sub-group of highly conserved 3' UTR regions was strongly down-regulated in 5 of 10 experiments, the non-conserved sub-group was down-regulated in 2 of 10 experiments (Fig. [1](#F:1)D, Table [S4]({{ page_suppl_info }}#T:S4) in the Supplementary Information). One possible explanation for this inconsistent pattern could be the conservation levels of the miRNAs used in the experiments. Since highly conserved miRNAs tend to have more target genes than less-conserved miRNA, highly conserved miRNAs may be more affected by the reported target dilution effect {% cite Arvey2010 -f {{ bib }} %}. However, we found no significant correlations between the degree of miRNA conservation and the down-regulation effects (data not shown). Moreover, the siRNAs used in the Jackson experiment should be unaffected by 3' UTR conservation, but these siRNAs strongly down-regulated highly conserved 3' UTRs compared with other 3' UTRs. We observed the same inconsistency for 3' UTR conservation when testing with the one-sided Kolmogorov–Smirnov test (Table [S7]({{ page_suppl_info }}#T:S7) in the Supplementary Information). Thus, although highly conserved 3' UTRs in some cases can be better targets for ectopically expressed small RNAs, the inconsistent regulatory effects suggest that other factors are more important.

### Target mRNA features: Predicted target genes with high mRNA expression levels are more down-regulated than the genes with low mRNA expression levels. {#S:3-4}
A recent study showed that mRNA expression affects siRNA efficacy such that lowly expressed mRNAs are less affected by siRNAs than are highly expressed mRNAs {% cite Larsson2010 -f {{ bib }} %}. Consistent with these results, siRNA and miRNA target genes with high or medium expression as measured by RNA-seq {% cite Birney2007 -f {{ bib }} %} were significantly down-regulated compared to the rest of the sub-groups in the microarray experiments (Fig. [1](#F:1)E). We saw a very strong down-regulatory effect on mRNA expression with sub-groups Very High, High, and Medium, as one or more sub-groups were significantly down-regulated compared to other predicted targets in 7 of 10 experiments (Table [S5](({{ page_suppl_info }}#T:S5)) in the Supplementary Information). Moreover, there was no experiment that showed significant p-values for sub-groups Very Low and NoExp. One-sided Kolmogorov–Smirnov tests also gave similar results (Table [S8]({{ page_suppl_info }}#T:S8) in the Supplementary Information). These results indicate that predicted miRNA or siRNA target genes with high or moderate expression levels are generally more down-regulated than genes with low expression levels.

### Target mRNA features: Comparison tests on individual samples strongly support that the differences between subgroups are common for many miRNAs. {#S:3-5}
Our analyses so far showed clear differences in how ectopic miRNA and siRNA expression affected certain subgroups of genes. Since these differences were based on the average effects of multiple miRNAs, however, we could not exclude that these differences were due to a few miRNAs instead of being common effects for many miRNAs. To test this possibility, we repeated the tests of the three target mRNA features – 3' UTR length, 3' UTR conservation, and mRNA expression levels – individually on the 140 different samples (Table [S2]({{ page_suppl_info }}#T:S2) in the Supplementary Information). We then calculated the proportions of samples that showed significant p-values (Table [S9]({{ page_suppl_info }}#T:S9)-[S11]({{ page_suppl_info }}#T:S11) in the Supplementary Information) and defined these proportions as Sample level scores (see [Methods](#S:5-3)). Consequently, a subgroup with Sample level score = 0.5 would be significant in 70 (50%) of the individual experiments. To compare the trends of the test results between experiments and samples, we created two types of counts to represent the trends for both experiments and samples: (i) the number of experiments that had significant p-values from the test results of the experiments, and (ii) the number of experiments that had their Sample level scores greater than 0.5 (Table. [1](#T:1)). The trends of mRNA expression level for experiments and samples were very similar for (Pearson *r* = 0.91; p-value = 0.01), whereas the trends of other two features showed high but insignificant correlation coefficients (3' UTR length, *r* = 0.79, p-value = 0.11; 3' UTR conservation, *r* = 0.81, p-value = 0.19). The results show that many individual samples support the overall trends for each experiment set – especially for the mRNA expression level features.

---

#### **Table 1**. Multiple compassion tests at an individual sample level support the experimental level test results. {#T:1}
{: .no_toc .text-caption }

{% include tbl_simple.html data=tab1 %}

**Exp**: the number of experiments that have significant p-value. **Smp**: the number of experiments that have Sample level scores greater than 0.5.
{: .fs-2 }

---

### Sample features: Competition with endogenous miRNAs impacts exogenous miRNAs’ targeting of genes with long 3' UTRs. {#S:3-6}
Small RNA transfection perturbs endogenous miRNA regulation such that genes targeted by endogenous miRNAs can become up-regulated {% cite Khan2009 -f {{ bib }} %}. We therefore hypothesized that genes with long 3' UTRs had a net unaffected expression or reduced response because these genes potentially had more endogenous miRNA target sites than genes with short 3' UTRs. To test this hypothesis, we separated the genes into four groups based on whether the genes were predicted to be targeted by the exogenous miRNAs and by highly expressed endogenous miRNAs. Both the first (T +Endo) and the second (T -Endo) groups consist of genes targeted by exogenous miRNAs, whereas the third (NT +Endo) and the fourth (NT -Endo) groups consist of genes without exogenous miRNA targets. The second word in the group names indicates that the group contains either genes targeted by endogenous miRNAs (+Endo) or genes without endogenous miRNA targets (-Endo) (Table [S12]({{ page_suppl_info }}#T:S12) in the Supplementary Information; see [Methods](#S:5-2)). Specifically, we used two of the four groups, T -Endo and T +Endo, for statistical analysis. We only used 8 transfected experiments and excluded 2 inhibition experiments because Selbach locked nucleic acid (LNA) and Linsley 2'-O-methyl (OME) experiments inhibited endogenous miRNAs.

Consistent with our hypothesis, there were no T - Endo genes that belonged to the Very Long sub-group in any of the eight experiments (Fig. [2](#F:2)A; Table [S13]({{ page_suppl_info }}#T:S13) in the Supplementary Information). For the other sub-groups of 3' UTR length, we tested whether T -Endo genes were more down-regulated than T +Endo genes (Table [S13]({{ page_suppl_info }}#T:S13) in the Supplementary Information). Although the majority of experiments showed no significant differences for the subgroups, T -Endo genes were significantly more down-regulated than T +Endo genes for sub-group Long in three of eight experiments. Moreover, the only other significant difference was for the Med Long sub-group on the Selbach dataset, where T -Endo genes again were significantly more down-regulated than T +Endo genes. These results suggest that genes with a very long 3' UTR are less affected by exogenous miRNAs than are other genes because these genes have a higher chance of being under the influence of endogenous miRNAs.

#### &nbsp; {#F:2}
{: .no_toc }
![Figure 2]({{ fig2 }}){:width="{{ page.figs.fig2[1] }}"}

##### **Figure 2**. Endogenous miRNAs tend to target genes with long 3' UTRs and exogenous miRNAs target highly expressed genes that had a small influence of endogenous miRNAs.
{: .no_toc .text-caption }
Two cumulative density plots of the log-ratio values show the miRNA down-regulatory effects on sub-groups of **(A)** 3' UTR length with the Grimson dataset, and **(B)** mRNA expression level with the Jackson dataset for ectopically expressed miRNA or siRNA target genes that were separated into T +Endo (T +E), T -Endo (T -E), NT +Endo (NT + E), and NT -Endo (NT -E).
{: .fs-2 }

---

### Sample features: PAR-CLIP data show that endogenous miRNAs target most mRNAs with long 3' UTR. {#S:3-7}
To further test whether endogenous miRNAs target most mRNAs with very long 3' UTR, we analyzed the data from an experiment that used Photoactivatable-Ribonucleoside-Enhanced Crosslinking and Immunoprecipitation (PAR-CLIP) of the four human Argonautes (AGO1-4, also known as EIF2C1-4) to identify miRNA binding sites {% cite Hafner2010 -f {{ bib }} %}. We mapped PAR-CLIP-supported AGO binding sites in 3' UTR regions and for each of the five different sub-groups defined by 3' UTR length, we counted the number of genes with binding sites (Table. [2](#T:2)). We found more AGO binding sites in long 3' UTR genes (Very Long and Long) than in short 3' UTR genes (Med Long, Med Short, and Short) when compared with all available RefSeq genes (p-values < 2.2e-16, Fisher’s exact test for all four AGOs). Specifically, of the five subgroups, the genes with very long 3' UTRs (Very Long) had the highest fraction of genes with AGO binding sites and this fraction decreased with decreasing 3' UTR length (Table [2](#T:2)). These results support that endogenous miRNAs preferentially target mRNAs with very long 3' UTR.

---

#### **Table 2**. PAR-CLIP data show that endogenous miRNA tend to target mRNAs with long 3' UTR. {#T:2}
{: .no_toc .text-caption }

{% include tbl_simple.html data=tab2 %}

The table shows the total number of genes (AllRef) and the number of Argonaute-bound 3' UTRs (AGO1-4) for each sub-group defined by 3' UTR length (see Methods). Values in brackets indicate the percentage of all genes in the sub-group that have AGO binding sites.
{: .fs-2 }

---

### Sample features: Competition with endogenous miRNAs is not affected by evolutionary conservation levels of 3' UTRs. {#S:3-8}
The test results of mRNA target features showed no consistent evidence that genes in any sub-group of 3' UTR conservation were significantly more down-regulated than were the genes in the rest of the sub-groups (Table [S4]({{ page_suppl_info }}#T:S4) in the Supplementary Information). We therefore did not expect to find consistent patterns of interaction between the competition effect and 3' UTR conservation. Indeed, when we tested whether T -Endo genes were more down-regulated than T +Endo genes in the sub-groups of 3' UTR conservation, the test showed no consistent trends across sub-groups; rather, the tests indicated consistent differences between experiments, as all sub-groups were significant on the Lim, Jackson, and Selbach datasets (Table [S14]({{ page_suppl_info }}#T:S14) in the Supplementary Information). These results suggest that competition between endogenous and exogenous miRNAs is unaffected by the levels of evolutionary conservation on 3' UTRs.

### Sample features: Competition with endogenous miRNAs has a strong impact on genes with medium or higher mRNA expression levels {#S:3-9}
As endogenous miRNA regulation mostly reduces target mRNA expression {% cite Stark2005 Shkumatava2009 Guo2010 -f {{ bib }} %}, miRNA target genes with low mRNA expression levels would more likely be under strong regulation by endogenous miRNAs. Similarly, miRNA target genes with high mRNA expression would less likely be under strong endogenous miRNA regulation. Consequently, we expected lowly expressed mRNAs to be less affected by competition with exogenous miRNAs than were highly expressed mRNAs. Indeed, T -Endo genes were significantly more down-regulated than were T +Endo genes for high or moderate mRNA expression levels (Very High, High, and Medium; Fig. [2](#F:2)B; Table [S15]({{ page_suppl_info }}#T:S15) in the Supplementary Information). Moreover, no experiments showed significant down-regulation for low or no mRNA expression levels (Very Low and NoExp). As, according to our results, endogenous miRNAs preferentially target genes with long 3' UTRs, taken together, these results support that the genes with a very long 3' UTR are less affected by exogenous miRNAs because most of them are under the influence of endogenous miRNAs.

### Sample features: Tests on individual samples support that the competition effect is strongest for genes with strong mRNA expression levels {#S:3-10}
To further analyze the trends of competition effects on 3' UTR length, 3' UTR conservation, and mRNA expression level, we tested the difference of miRNA down-regulation between T -Endo and T +Endo genes on the 140 individual samples instead of the collective experiments. To compare the trends of the test results between experiments and samples, we again created two types of counts: (i) the number of experiments that had significant p-values from the test results of the experiments, and (ii) the number of experiments that had their Sample level scores greater than either 0.5 or 0 (Table [S16]({{ page_suppl_info }}#T:S16) in the Supplementary Information). With a strict threshold of Sample level scores (>0.5), the tests on samples showed no strong support for the trend observed when tested on the experiments. With a less strict threshold of Sample level scores (>0), the tests on samples supported the trend for mRNA expression level (Pearson *r* = 0.86; p-value = 0.03), whereas the 3' UTR length showed some but insignificant support of the experiment-level results (*r* = 0.47; p-value = 0.42). The 3' UTR conservation showed no correlation with the experiment-level results (*r* = -0.10; p-value = 0.9). Together, the results indicated that some samples support the result from the collective experiments that the competition effect more strongly affects genes with high compared with low mRNA expression level.

### Platform features: Microarray datasets can have cryptic bias towards detecting differential expression in highly expressed genes. {#S:3-11}
A recent study showed that mRNA expression affects siRNA efficacy such that lowly expressed mRNAs are less affected by siRNAs than are highly expressed mRNAs {% cite Larsson2010 -f {{ bib }} %}. Consistent with these results, siRNA and miRNA target genes with high or medium expression, as measured by RNA-seq {% cite Birney2007 -f {{ bib }} %}, were significantly down-regulated compared to the rest of the sub-groups in the microarray experiments (Fig. [1](#F:1)E). However, these trends were not apparent in the proteomics datasets, which instead showed significant effects on the lowly expressed genes (two of three experiments; Table [S5]({{ page_suppl_info }}#T:S5) in the Supplementary Information).

The cumulative density plots of log-ratio values for the Grimson microarray and Selbach proteomics datasets illustrate the differences (Fig. [3](#F:3)A, B). The three sub-groups of very high, high, and medium expression were left-shifted and therefore more strongly down-regulated relative to the other groups in the Grimson microarray dataset (Fig. [3](#F:3)A). Indeed, the groups’ expression level appeared to strictly determine the degree of down-regulation, as the very highly expressed genes were more left-shifted compared to the highly expressed genes and so on. In contrast, the Selbach proteomics datasets showed no such trends (Fig. [3](#F:3)B); the three sub-groups with the highest expression levels were similarly affected, whereas the lowly expressed genes were slightly more down-regulated than the other groups.

#### &nbsp; {#F:3}
{: .no_toc }
![Figure 3]({{ fig3 }}){:width="{{ page.figs.fig3[1] }}"}

##### **Figure 3**. Microarrays but not proteomics are biased towards detecting differential expression among highly expressed genes.
{: .no_toc .text-caption }
Cumulative density plots of log-ratio values for miRNA targets grouped by gene expression levels in **(A)** the Grimson and **(B)** the Selbach datasets. **(C)** Barplots show the ratio of the six sub-groups of mRNA expression levels subdivided by predicted exogenous and endogenous miRNA targeting in the Grimson and Selbach datasets for all genes (“All”) and down-regulated genes ("Down-reg", p < 0.01; log ratio (lr) < -0.01). **(D)** Scatter plots show log2 enrichment of down-regulated genes compared with all genes for the six sub-groups of mRNA expression levels in all studied datasets. Lines and shaded grays show respectively linear fits and standard errors for the microarray (red dots) and proteomics (blue triangles) experiments; p-values (lower left) are unadjusted p-values from Pearson correlation tests. Data points based on a single gene were excluded. The regression lines show that in the microarray but not the proteomics experiments, down-regulated genes are enriched among highly expressed genes and that this enrichment depends on gene expression levels.
{: .fs-2 }

---

As the proteomics experiments relied on detecting and identifying individual proteins, whereas microarrays use hybridization signals to infer gene expression, we reasoned that the differences might be explained by differences in the two methods’ sensitivity to detect highly and lowly expressed genes or to detect expression changes for highly and lowly expressed genes. Whereas the microarray signals were evenly distributed among all subgroups of gene expression levels, the proteomics data showed bias towards highly expressed genes and detected few very lowly expressed genes (Fig. [3](#F:3)C). These trends were apparent in the other microarray and proteomics datasets as well (Fig. [S1]({{ page_suppl_info }}#F:S1) in the Supplementary information). When considering expression changes, however, the proteomics data showed little bias and detected down-regulated genes independently of their expression level (Fig. [3](#F:3)D). The microarray data, in contrast, showed strong expression-related bias, such that down-regulated genes were enriched among the highly expressed genes and depleted among the lowly expressed genes.

Importantly, these results were independent of miRNA targeting, as subdividing the genes into four groups based on whether the genes contained predicted target sites for the exogenous miRNAs and highly expressed endogenous miRNAs gave similar results (Figs. [S2]({{ page_suppl_info }}#F:S2) in the Supplementary information). This grouping further illustrated the effects of miRNA targeting, however. Specifically, consistent with miRNAs inhibiting mRNA expression, the most highly expressed genes constituted a smaller percentage of the genes predicted to be targets for endogenous miRNA (T +Endo and NT +Endo, Fig. [3](#F:3)C) than of the genes predicted not to be targets (T -Endo and NT -Endo; Fig. [3](#F:3)C).

In summary, the exogenous miRNAs’ apparent strong effects on highly expressed genes within the microarray data can be explained by technology-related artefacts. Specifically, our results show that although microarrays detect lowly expressed genes, arrays have lower sensitivity for identifying differential expression for such genes than for highly expressed genes. This is consistent with previous results {% cite Evans2003 -f {{ bib }} %}. Proteomics data, in contrast, are biased towards highly expressed genes, but detect differential expression independently of gene expression levels. In other words, proteomics fails to detect many genes with low expression level but the sensitivity in detecting differentially expressed genes is similar among different expression levels, whereas microarrays can detect genes with low expression level but the sensitivity in detecting differential expression is low for these genes compared with highly expressed genes. Because of these differences, microarray but not proteomics data will show that miRNAs on average have a stronger effect on highly than on lowly expressed genes.

### Platform and Sample features: Competition with endogenous miRNAs has a stronger impact on regulation than have dilution from high overall target expression. {#S:3-12}
A recent study has reported that when over-expressing miRNAs, a high overall expression level of predicted targets reduces the miRNA’s average regulatory effect – the so-called target dilution effect {% cite Arvey2010 -f {{ bib }} %}. Arvey and colleagues mainly used the total mRNA expression level to test the dilution effect, but they also suggested that other approaches were almost equally effective, such as the total number of target sites {% cite Arvey2010 -f {{ bib }} %}. To test the dilution effect on the samples, we therefore used the number of target sites instead of total mRNA expression levels, as these values were very highly correlated (*r* = 0.973; Fig. [S3]({{ page_suppl_info }}#F:S3) in the Supplementary information) and also because mRNA expression data were unavailable for the HCT116 and DLD-1 cell-lines used in the Linsley experiment. Our results confirmed a significant correlation between the total number of target sites and the average log ratio of predicted miRNA targets (*r* = 0.369; p-value < 0.001; Fig. [4](#F:4)A).

#### &nbsp; {#F:4}
{: .no_toc }
![Figure 4]({{ fig4 }}){:width="{{ page.figs.fig4[1] }}"}

##### **Figure 4**. Genes without target sites for endogenous miRNAs show less dilution effects than does the complete set of potential targets.
{: .no_toc .text-caption }
**(A)** The scatter plot shows the average log ratios for predicted miRNA and siRNA targets as measured by microarrays of 90 over-expression experiments (55 miRNAs and 35 siRNAs) as a function of the miRNAs’ and siRNAs’ total number of target sites. The line is based on a linear regression and indicates that there is a significant correlation between the total number of target sites and average log ratio (*r* = 0.37; p < 0.001). **(B)** The scatter plot shows the average log ratios for the subset of genes that have no predicted target sites for endogenous miRNAs as a function of the miRNAs’ and siRNAs’ total number of target sites (*r* = 0.22; p = 0.068). Only the 70 samples assayed in HeLa were included. In both plots, red circles represent miRNAs, and blue triangles represent siRNAs.
{: .fs-2 }

---

Targeting by endogenous miRNAs influences both the genes’ expression levels before transfection (Fig. [3](#F:3)D) and response to exogenous miRNAs after transfection (Fig. [2](#F:2)). We therefore reasoned that part of the observed correlation could be related to interactions between endogenous miRNAs and the exogenous, ectopically expressed miRNA because some exogenous miRNA target genes also targeted by endogenous miRNAs were potentially up-regulated because of the competition effects. Such interactions could further be compounded by microarrays’ bias towards detecting differential expression among highly expressed genes (Fig. [3](#F:3)E). Arvey and colleagues based their conclusions on microarray data and they also reported that for most transfected miRNAs or siRNAs (15 of 181 tested; p-value = 2e-33, sign test), highly expressed genes are more down-regulated than are lowly expressed genes {% cite Arvey2010 -f {{ bib }} %}. To eliminate such interactions between the endogenous and exogenous miRNAs, we calculated the correlation between the total number of miRNA sites and the average log ratio of the genes that were predicted only to be targets for the exogenous miRNAs. The correlation was not significant (*r* = 0.22; p-value = 0.067; Fig. [4](#F:4)B), indicating that when considering the average effects of exogenous, ectopically expressed miRNAs, endogenous miRNA regulation (competition {% cite Khan2009 -f {{ bib }} %}) is more important than overall target expression levels (dilution).

### Regression analysis: Linear regression confirmed trends from individual feature analyses. {#S:3-13}
To further investigate how the different features collectively contributed to log ratio changes of gene expression, we built a linear regression model with eight factors per mRNA target. These eight factors represented our previous target, sample, and platform level features (Table [3](#T:3)). To create the model, we first calculated the eight factors for all predicted miRNA or siRNA target genes and transformed the factors’ value range to [0, 1], to make regression coefficient values easily comparable. Second, we negated all log-ratio values for the transfection experiments so that a positive coefficient meant that a high value for the factor contributed positively to gene down-regulation. Third, we built a linear regression model with the eight factors on the set of predicted miRNA and siRNA target genes from the 10 experiments (R<sup>2</sup> = 0.040; R<sup>2</sup> = 0.040, when adjusted by the number of records and the number of terms).

---

#### **Table 3**. Nine factors for linear regression. {#T:3}
{: .no_toc .text-caption }

{% include tbl_simple.html data=tab3 %}

All values are either in a range between 0 and 1 (0~1) or binary (0 or 1).
{: .fs-2 }

---

The model showed that seven of the factors significantly contributed to log ratio changes, although to different extents (Fig. [5](#F:5); Table [S17]({{ page_suppl_info }}#T:S17) in the Supplementary information). Consistent with published results that multiple miRNA target sites enhance miRNA down-regulation {% cite Guo2010 -f {{ bib }} %}, the number of target sites (#site_m) was the strongest factor, and consistent with our non-parametric tests, mRNA expression (exp) had the second largest coefficient. Furthermore, 3' UTR length (ln3), the number of target sites for endogenous miRNAs (#endo_m), and the total number of target sites per sample (#site_s) had strong negative coefficients, whereas transfection compared with inhibition experiments (e_oe) had, as expected, a positive coefficient. Partly contrary to the non-parametric analyses, however, 3' UTR conservation (cs3) was consistently and strongly associated with target knock-down, but this result likely reflects that highly conserved 3' UTRs were strongly associated with target knock-down in four of the ten experiments (Fig. [1](#F:1)).

#### &nbsp; {#F:5}
{: .no_toc }
![Figure 5]({{ fig5 }}){:width="{{ page.figs.fig5[1] }}"}

##### **Figure 5**. Coefficients of a linear regression with eight factors.
{: .no_toc .text-caption }
The dot plot shows the coefficients of the liner model with formula: -log ratio = ln3 + cs3 + exp +#site_m + #endo_m + #site_s + p_ma + e_oe. The dot size shows -log10 of the coefficient’s p-value. Positive coefficients associate with miRNA down-regulation.
{: .fs-2 }

---

### Regression analysis: Factor crossing in the linear model confirmed that several factors have combined effects on miRNA down-regulation. {#S:3-14}
Based on our analyses of the individual target, sample, and experiment features, we expected that some factor pairs such as exp and p_ma, #site_m and #endo_m, and cs3 and e_oe had strong combined effects. To investigate this possibility, we extended our simple linear model to include all second-order interactions, such as ln3 * cs3, ln3 * exp, and so on. This extension slightly increased the R<sup>2</sup> of the model (R<sup>2</sup> = 0.047; adjusted R<sup>2</sup> = 0.046).
Although directly comparing coefficients was less straightforward than for the simpler model without factor interactions because of different range distributions for combined factors, there were still several factors that had significantly higher or lower coefficients than the others (Fig. [S4]({{ page_suppl_info }}#F:S4) and Table [S18]({{ page_suppl_info }}#T:S18) in the Supplementary information). The number of target sites for the ectopically expressed miRNA or siRNA (#site_m) had the highest coefficient, whereas the interaction between #site_m and the number of target sites for endogenous miRNAs (#endo_m) had the lowest and most significant coefficient. Consistent with the number of target sites’ importance for regulation, most factor combinations that included #site_m were significant. These results confirm that the number of target sites (#site_m) is the most important factor to explain log ratio changes, but that several other interacting factors and especially competition with endogenous miRNAs (#endo_m) influence the resulting target knock-down.
Of the other factors, target expression (exp) was still among the most significant single factor. Moreover, consistent with our previous results, the coefficients for exp’s interaction with the two experiment factors (p_ma and e_oe) were strong, significant, and positive. In contrast, exp by itself or interacting with 3' UTR length (ln3) had a significant negative coefficient. Consequently, our results suggest that when experiment-related features are factored out, miRNAs do more strongly affect lowly than highly expressed genes.

As for the remaining features, both ln3 and cs3 showed significant interactions with expected features. Especially cs3 showed strong and significant interactions with many factors (all except ln3, exp, and p_ma), which likely explains the conflicting results for 3' UTR conservation in the individual feature analyses.

### Regression analysis: target site-dependent features, as modeled by TargetScan scores show strong interactions with site-independent features. {#S:3-15}
So far, our regression models and analyses considered all stringent seed sites as equally important target sites (see [Methods](#S:5-2)), but different features of individual target sites, such as the seed type, the site’s AU context, the site’s location in 3’ UTR, and additional pairing between the miRNA 3' end and mRNA, do affect miRNA targeting {% cite Grimson2007 -f {{ bib }} %}. We therefore extended our regression model to include TargetScan {% cite Grimson2007 -f {{ bib }} %} scores (see [Methods](#S:5-2)) to determine how the predicted effects of individual miRNA target sites affect and interact with the mRNA, sample, and platform level features in our model.

A simple regression model with only TargetScan scores had R<sup>2</sup> = 0.043, which was very similar to the previous models with eight factors (R<sup>2</sup> = 0.040 and R<sup>2</sup> = 0.046 for the simple and combined effects models, respectively). In contrast, a simple regression model that included all the nine factors showed increased R<sup>2</sup> (R<sup>2</sup> = 0.071; adjusted R<sup>2</sup> = 0.071). The most significant single factor in this model was TargetScan score (ts_score; Fig. [6](#F:6); Table [S19]({{ page_suppl_info }}#T:S19) in the Supplementary information). Most factors showed very similar trends compared with the previous model with eight factors (Fig. [5](#F:5)), except for the number of target sites for the ectopically expressed miRNA or siRNA (#site_m) which showed decreased importance. This decrease can be explained, however, by TargetScan modeling total mRNA regulation as the sum of the scores for individual target sites; TargetScan scores (ts_score) and the number of target sites for the ectopically expressed miRNA or siRNA (#site_m) are strongly correlated (*r* = 0.42; p-value < 2.2e-16).
Taking all second-order interactions into account further improved the model (R<sup>2</sup> = 0.093; adjusted R<sup>2</sup> = 0.092) and TargetScan score combined with most other factors (except #site_m) showed significant coefficients (Fig. [S5]({{ page_suppl_info }}#F:S5) and Table [S20]({{ page_suppl_info }}#T:S20) in the Supplementary information). Together, these results show that although target site-dependent features, such as those modeled by TargetScan, are important for miRNA targeting, target mRNA, sample, and platform level features are also important for correctly interpreting miRNA high-throughput experiments. Specifically, in our analyses, target site-dependent and -independent features explain about the same amount of variation in target gene expression.

#### &nbsp; {#F:6}
{: .no_toc }
![Figure 6]({{ fig6 }}){:width="{{ page.figs.fig6[1] }}"}

##### **Figure 6**. Coefficients of a linear regression with nine factors.
{: .no_toc .text-caption }
The dot plot shows the coefficients of the liner model with formula: -log ratio = ln3 + cs3 + exp +#site_m + #endo_m + #site_s + p_ma + e_oe + ts_score. The dot size shows -log10 of the coefficient’s p-value. Positive coefficients associate with miRNA down-regulation.
{: .fs-2 }

---

### CpG frequency, and Developmental and Housekeeping genes: Overall gene expression is a major confounding factor when analyzing microarray data. {#S:3-16}
As studies reported that miRNAs preferably target the high-CpG (CpGH) genes {% cite Sinha2008 -f {{ bib }} %} and developmentally regulated (Dev) genes {% cite Stefani2008 -f {{ bib }} %} and also tend to avoid targeting house-keeping (HK) genes {% cite Bartel2004 Stark2005 -f {{ bib }} %}, we expected the CpGH, Dev, and non-housekeeping (Non-HK) genes to be strongly down-regulated in the experimental data. To test miRNA down-regulation of these features, we split them into smaller sub-groups and used predicted miRNA or siRNA target genes to test whether any sub-group was more down-regulated than the others (Fig. [7]({{ page_suppl_info }}#F:S7)). As expected, the CpGH genes were significantly affected (Fig. [7]({{ page_suppl_info }}#F:S7)A; Tables [S21]({{ page_suppl_info }}#T:S21) in the Supplementary information), but we observed the opposite to the expected for the Dev and Non-HK genes (Fig. [7](#F:7)B,C; Tables [S22]({{ page_suppl_info }}#T:S22) and [S23]({{ page_suppl_info }}#T:S23) in the Supplementary information). Importantly, only the microarray data showed these unexpected differential effects. The proteomics data showed slightly stronger effects on the Dev and Non-HK genes, although only one of four comparisons was significant (Tables [S22]({{ page_suppl_info }}#T:S22) and [S23]({{ page_suppl_info }}#T:S23) in the Supplementary information). We therefore reasoned that the results could be related to the microarrays’ bias towards detecting differential expression among highly expressed genes.

#### &nbsp; {#F:7}
{: .no_toc }
![Figure 7]({{ fig7 }}){:width="{{ page.figs.fig7[1] }}"}

##### **Figure 7**. CpG-rich genes, non-developmental genes, and house-keeping genes appear to be strong miRNA targets in microarray experiments.
{: .no_toc .text-caption }
We subdivided all RefSeq genes into sub-groups based on three different features: CpG frequency (CpG), and whether the genes were developmental (Dev) and house-keeping (HK) genes (see Methods). See Fig. [1](#F:1) for a description of the heat maps.
{: .fs-2 }

---

Consistent with this hypothesis, non-parametric tests to find the characteristics of CpG, HK, and Dev showed that CpGH and HK genes had more highly expressed genes than the other sub-groups and also showed that Dev genes had more lowly expressed genes (Table [4](#T:4)). We therefore concluded that the genes’ overall expression level was the major factor behind the observed differences within the CpG, Dev, and HK groups.

---

#### **Table 4**. P-values of multiple Wilcoxon rank-sum tests on 3 miRNA target features for CpGH, House-keeping, and Developmental genes. {#T:4}
{: .no_toc .text-caption }

{% include tbl_simple.html data=tab4 %}

Lower p-values in the Greater column indicate that the gene set of the Gene type overall has longer 3' UTR lengths, more conserved 3' UTRs, or stronger mRNA expression than has the rest of the human protein coding genes. Lower p-values in the Less column indicates the opposite characteristics; that is, shorter 3' UTR lengths, less conserved 3' UTRs, or lower mRNA expression.
{: .fs-2 }

---

## Conclusions {#S:4}
We analyzed the average regulatory effects that ectopically expressed miRNAs or siRNAs have on large gene sets and identified two strong factors. First, competition between endogenous miRNAs and the ectopically expressed RNAs have a strong impact on targets’ regulatory response. Genes with very long 3' UTRs, for example, are likely targeted by endogenous miRNAs and therefore less affected by exogenous miRNAs than are genes with shorter 3' UTRs. Second, target gene expression is a strong confounding factor when analyzing microarray experiments. Target genes with strong expression levels were significantly down-regulated compared to other expressed genes only in the microarray experiments. One explanation is that some genes are highly expressed simply because they are less targeted by endogenous miRNAs, and, therefore, ectopically expressed miRNAs have stronger down-regularly effects on these genes. Consistent with this explanation, miRNA transfection experiments give stronger target expression changes than do miRNA inhibition experiments.

Another explanation is that microarrays, compared with high throughput proteomics, report significant expression data for many more lowly expressed genes. This technological difference means that microarrays can detect more differentially expressed genes than can high throughput proteomics. However, microarrays generally detect less differential expression for lowly expressed genes than for highly expressed genes. Consequently, microarrays will find a smaller fraction of the lowly expressed genes than of the highly expressed genes to be differentially expressed. The result is that when using microarray data to compare average down-regulation of miRNA-targets among house-keeping genes and developmentally regulated genes – genes that have high and low average expression levels, respectively – the average down-regulation is stronger for house-keeping genes than for developmental genes. This difference is contrary to the general consensus within the field {% cite Bartel2009 -f {{ bib }} %} and our analyses of high-throughput proteomics data which indicate that developmentally regulated genes are more likely miRNA targets than are house-keeping genes. Supporting this, our regression analysis shows that when such experiment-related confounding factors have been taken into account, miRNAs more effectively knock down lowly expressed than highly expressed genes.

These results suggest that it is important to consider multiple factors when it comes to assessing miRNA targeting effects. One example of this relates to the so-called target dilution effect. A previous analysis has reported that the total expression level of target candidates for ectopically expressed miRNAs affects the targets’ average knockdown such that high total expression gives low average knockdown {% cite Arvey2010 -f {{ bib }} %}. Our analyses, however, show that some of this dilution effect can be explained by interactions with endogenous miRNAs. Consequently, it is very important to consider what genes are already targeted by endogenous miRNAs when designing and interpreting high throughput miRNA or siRNA experiments.

In summary, our results can explain the results from several recent studies that have analyzed features that are important for miRNA regulation and found that the importance of 3' UTR length, conservation, and target gene expression depend on the technology used to measure miRNA targeting. Our results urge especial caution when using microarray data to compare average regulatory effects between groups of genes that have different average gene expression levels, such as high and low CpG genes and housekeeping and developmentally regulated genes.

## Methods {#S:5}
### Data retrieval {#S:5-1}
**miRNA annotation and miRNA seed types**: We downloaded the annotations of human miRNAs, mature miRNAs, and miRNA families from miRBase (release 12.0) {% cite Griffiths-Jones2008 -f {{ bib }} %}.

**Microarray and proteomics datasets**: We downloaded four microarray datasets, the Jackson {% cite Jackson2006 -f {{ bib }} %}, Lim {% cite Lim2005 -f {{ bib }} %},  Grimson {% cite Grimson2007 -f {{ bib }} %}, and Linsley {% cite Linsley2007 -f {{ bib }} %} from the Gene Expression Omnibus (GEO) database [GEO:GSE5814, GEO:GSE2075, GEO:GSE8501, GEO:GSE6838] {% cite Barrett2007 -f {{ bib }} %}, and two proteomics datasets, Selbach {% cite Selbach2008 -f {{ bib }} %} and Baek {% cite Baek2008 -f {{ bib }} %}, from the original publications along with the corresponding microarray datasets. In total, we used six microarray and two proteomics datasets. Samples from both microarray and proteomics used in this study are listed in Table [S2]({{ page_suppl_info }}#T:S2) in the Supplementary information.

**3' UTR sequence and conservation**: We downloaded the RefSeq transcripts (hg18), human chromosome sequences, and multiz 17-way {% cite Blanchette2004 -f {{ bib }} %} for conserved sequences from the University of California, Santa Cruz (UCSC) Genome Browser {% cite Kent2002 -f {{ bib }} %}. The positional data used to generate nucleotide sequences were the exon positions from RefSeq for the 3' UTR region. We selected the longest 3' UTRs when a RefSeq entry had multiple transcripts. In addition to the human sequences, we generated 3' UTR sequences conserved in human, mouse, and rat (HMR) from multiz 17-way.

**mRNA expression in HeLa**: We used replicate 1 of the ENCODE Caltech RNA-Seq data {% cite Birney2007 -f {{ bib }} %} from USCS for the mRNA expression in HeLa.

**House keeping and developmental genes**: We obtained housekeeping genes from a list generated by a Naive Bayes classifier {% cite DeFerrari2006 -f {{ bib }} %}, and the developmental genes from the Gene Ontology [GO:0032502] {% cite Ashburner2000 -f {{ bib }} %}.

**Endogenous miRNAs in HeLa**: We used the Mammalian microRNA Expression Atlas {% cite Landgraf2007 -f {{ bib }} %} to define the endogenous miRNAs in HeLa. For endogenous miRNAs, we selected the top 10 highly expressed miRNA families and used the miRNAs that belong to these miRNA families. We used three stringent seed types –  8mer, 7mer-A1, and 7mer-m8 – to search the candidate sites of the endogenous miRNAs.

**PAR-CLIP**: We obtained PAR-CLIP high-throughput sequencing data of all four AGO proteins from the GEO database [GEO:GSE21918] {% cite Hafner2010 -f {{ bib }} %}. We used positional information downloaded with the sequence reads and mapped these positions on 3' UTR regions of all RefSeq genes. We considered 3' UTRs that had at least one site with the number of mapped reads greater than or equal to five to have an AGO binding site.

### Data preparation {#S:5-2}
**Data preparation for microarray and proteomics data**: We used pre-processed data either from GEO or from the original publications. All log-ratio values that were pre-computed in log2 were transformed to log10. Log-ratio values of two inhibition experiments, Selbach LNA and Linsley OME, were negated because genes with positive log-ratio values were potential miRNA targets for these experiments.

**Predicted miRNA or siRNA targets**: We separated the genes of each high throughput experiment by target prediction into “Target” and “Non-target” genes. The target prediction method we uses was a simple stringent seed search on the 3' UTRs and a gene was defined as a “Target” when the gene contained a seed site for the miRNA or siRNA used in the experiment. We used the previously described three stringent seed types, 8mer, 7mer-A1, and 7mer-m8, to define miRNA targets {% cite Bartel2009 -f {{ bib }} %}.

**3' UTR sequence length**: For the 3' UTR sequence length, we made five sub-groups, Very Long (>4000 nts), Long (1373 ~ 4000 nts), Medium Long (630 ~ 1372 nts), Medium Short (248 ~ 629 nts), and Short (0 ~ 247 nts). The first group Very Long was decided from our previous study {% cite Saito2010 -f {{ bib }} %} because it showed that the genes with 3' UTR length longer than 4000 nucleotides were less targeted by miRNAs. We sorted the rest of the sequences by 3' UTR length and divided them into four equally sized sub-groups.

**3' UTR sequence conservation**: For the 3' UTR sequence conservation, we calculated the conservation scores for each sequence by counting the number of conserved nucleotides in the HMR sequences and then divided the resulting number by the length of the sequence. We sorted the sequences with non-zero scores and divided them into three equal sub-groups; High (>0.238), Medium (0.054 ~ 0.238), and Low (0 ~ 0.238). The sequences with zero scores were categorized as NoConsv.

**mRNA expression level**: We used the average number of tags from Caltech RNA-Seq as a measure (score) of mRNA expression levels. We sorted the mRNAs with non-zero expression scores by score and then divided them into five equally sized sub-groups; Very High (> 0.2007), High (0.0795 ~ 0.2007), Medium (0.0344 ~ 0.0795), Low (0.008 ~ 0.0344), and Very Low (0 ~ 0.008). The mRNAs with zero scores were categorized as NoExp.

**CpG frequency in promoters**: We defined the promoter regions as 1000 nucleotides upstream from the transcription start site. We used a moving window approach (500 nt window moving 5 nt at the time) to compute the CpG frequency and classified the CpG frequency as “high” when at least one 500-nucleotide-window contained >55% GC content and >75% CpG content, “low” when none of the windows contained >48% CpG content, and “medium” for the rest {% cite Weber2007 -f {{ bib }} %}.

**House keeping and developmental genes**: We mapped house-keeping and developmental genes to based on gene IDs RefSeq genes. Non-house keeping and non-developmental genes were the rest of the RefSeq genes that were not mapped.

**Endogenous miRNA targets**: We split “Target” and “Non-Target” genes into “With endogenous” and “Without endogenous” to make the T +Endo, T -Endo, NT +Endo, and NT -Endo gene groups, where “T” and “NT” represent “Target” and “Non-Target”, whereas “+Endo” and “-Endo” represent “With endogenous” and “Without endogenous”. We defined a gene as “With endogenous” when the gene was a predicted targeted for one or more of the top 10 most highly expressed endogenous miRNA families. The same approach as for predicting miRNA and siRNA targets was used to predict target genes for endogenous miRNAs.

**Total mRNA expression levels and total number of target sites for the dilution effects**: We calculated both the total mRNA expression and the number of target transcripts as previously described {% cite Arvey2010 -f {{ bib }} %}. The total mRNA expression was a sample level sum of the average number of tags from Caltech RNA-Seq for predicted miRNA or siRNA target genes. The total number of target sites was a sample level sum of the number of target sites in predicted miRNA or siRNA target genes.

**mRNA level TargetScan scores**: The stand alone version of TargetScan was downloaded from the TargetScan website ([http://www.targetscan.org](http://www.targetscan.org)). We then ran TargetScan on the 3' UTR sequences of the genes from the 10 miRNA high-throughput experiments with corresponding miRNA or siRNA sequences. The scores of target sites were aggregated by miRNA:mRNA pairs, and the aggregated scores were negated. Therefore, a high mRNA-level TargetScan score indicates that the mRNA is a strong candidate for miRNA down-regulation.

### Statistical analysis {#S:5-3}
**Non-parametric tests**: We used the log-ratio values from 10 different experiments (Table S1 in the Supplementary information) that contain 140 different samples (Table [S2]({{ page_suppl_info }}#T:S2) in the Supplementary information) to measure the contributions of different groups to miRNA targeting efficacy. To test the significance level between multiple groups, we performed both one-sided Wilcoxon rank-sum and one-sided Kolmogorov–Smirnov non-parametric multiple comparison tests on the log-ratio values.

**Sample level scores**: We performed non-parametric tests on 140 samples and counted the number of samples that had a significant p-value (<0.05) to calculate the proportion per experiment as Sample level score.

**PAR-CLIP analysis**: We merged the five sub-groups of 3' UTR lengths into the two bigger groups long (Very Long and Long) and short (Med Long, Med Short, and Short) for all RefSeq genes and identified potential miRNA target genes bound by the four AGOs. The numbers of bound genes in the long and short groups were compared between each AGO and all RefSeq genes by Fisher's exact test.

**Log2 enrichment of down-regulated genes**: The enrichment was calculated as the average log ratio values of down-regulated genes (p-value  < 0.01 and log ratio  < -0.01 for microarray, and log ratio  < -0.01 for proteomics) divided by the average log-ratio values of all genes.

**Linear regression**: All factors were normalized to the [0,1] value range before building linear regression models. The normalization was linear; that is,  (feature value - min) / (max - min), where min and max values were defined for each factor as ln (min: -2.0, max: 2.0), ln3 (min: 0, max: 1000), cs3 (min:0, max: 1), exp (min:6.1e-5, max: 64.0), #site_m (min: 0, max: 20), #endo_m (min: 0, max: 30), #endo_s (min: 0, max: 6000), and ts_score (min: 0.0, max: 2.0).

## Additional files {#S:6}
Additional file 1 – [Supplementary information]({{ page_suppl_info }}) [[PDF]({{ site.baseurl }}/assets/Saito_2012_Confounding_factors-supplementary_information.pdf)] \
Additional file 1 contains [Supplementary Table]({{ page_suppl_info }}#S:1) S1-S23 and [Supplementary Figures]({{ page_suppl_info }}#S:2) S1-S5.

## Competing interests {#S:7}
The authors declare that they have no competing interests.

## Authors' contributions {#S:8}
All authors contributed to the underlying ideas of the method and the analysis. TS implemented the initial model of statistical analyses. All authors contributed to the statistical analysis. The initial manuscript draft was written by TS, and refined by PS. All authors read and approved the final manuscript.

## Acknowledgements {#S:9}
We thank Morten Rye for assistance with RNAseq data analysis. This work was supported by the Functional Genomics Program (FUGE) of the Norwegian Research Council.

## References {#S:10}
{% bibliography --cited_in_order -f {{ bib }} %}
