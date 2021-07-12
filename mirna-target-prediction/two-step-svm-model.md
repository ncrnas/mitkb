---
layout: default
title: "Research: Two-step SVM"
parent: Target prediction
description: "A two-step site and mRNA-level model for predicting microRNA targets"
comments: true
nav_order: 2
group: two-step-svm
folders:
  prediction: mirna-target-prediction
pages:
  suppl_info: two-step-svm-model-supplementary-information
tabs:
  tab1: table1
figs:
  fig1: [microrna-seed-types.webp, 500]
  fig2: [roc-curves-target-site-mrna-levels.webp, 500]
  fig3: [roc-curves-svm-microarray-experiments.webp, 500]
  fig4: [microrna-three-prime-utr-length-vs-site-count.webp, 500]
  fig5: [microrna-target-prediction-benchmark.webp, 800]
  fig6: [microrna-target-prediction-benchmark-proteomics.webp, 800]
scholar:
  bibliography: two_step_svm
---

{% capture page_suppl_info %}{{ site.baseurl }}/{{ page.folders.prediction }}/{{ page.pages.suppl_info }}{% endcapture %}

{% assign tab_arr = site.data[page.group] %}
{% assign tab1 = tab_arr[page.tabs.tab1] %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture fig1 %}{{ fig_dir }}/{{ page.figs.fig1[0] }}{% endcapture %}
{% capture fig2 %}{{ fig_dir }}/{{ page.figs.fig2[0] }}{% endcapture %}
{% capture fig3 %}{{ fig_dir }}/{{ page.figs.fig3[0] }}{% endcapture %}
{% capture fig4 %}{{ fig_dir }}/{{ page.figs.fig4[0] }}{% endcapture %}
{% capture fig5 %}{{ fig_dir }}/{{ page.figs.fig5[0] }}{% endcapture %}
{% capture fig6 %}{{ fig_dir }}/{{ page.figs.fig6[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# A two-step site and mRNA-level model for predicting microRNA targets
{: .no_toc .text-center }

Takay Saito<sup>1</sup> and Pål Sætrom<sup>1,2</sup>
{: .text-center }

<strong><sup>1</sup></strong>Department of Cancer Research and Molecular Medicine,  \
Norwegian University of Science and Technology, NO-7489 Trondheim, Norway \
<strong><sup>2</sup></strong>Department of Computer and Information Science, \
Norwegian University of Science and Technology, NO-7491 Trondheim, Norway
{: .fs-3 .text-center .text-grey-dk-000 }

<br />
[View PDF](https://bmcbioinformatics.biomedcentral.com/track/pdf/10.1186/1471-2105-11-612.pdf){: .btn }
<div class="code-example">
<strong>Citation:</strong> <br />
Saito, T and Sætrom, P. A two-step site and mRNA-level model for predicting microRNA targets.
<i>BMC Bioinformatics</i> <strong>11,</strong> 612 (2010).
<a href="https://doi.org/10.1186/1471-2105-11-612">https://doi.org/10.1186/1471-2105-11-612</a>.
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
Despite experiments showing that the number of microRNA (miRNA) target sites is critical for miRNA targeting, most existing methods focus on identifying individual miRNA target sites and do not model contributions of multiple target sites to miRNA regulation. To address this possible fault, we developed a miRNA target prediction model that recognizes the individual characteristics of functional binding sites and the global characteristics of miRNA-targeted mRNAs.

### Results
{: .no_toc }
Benchmark experiments showed that this two-step model generally had a higher overall performance than other established miRNA target prediction algorithms and that the model was especially suited to identify true miRNA targets among genes that all contain conserved target sites.

### Conclusions
{: .no_toc }
This improved performance could partly be explained by the model not relying on conservation when predicting targets. The critical factors for the model’s performance, however, were mRNA-level features that characterized the number and strength of individual target sites within the mRNA. The model is available for online predictions or as pre-computed predictions on the human genome (http://tare.medisin.ntnu.no/mirna_target).

## Background {#S:2}
MicroRNAs (miRNAs) are a class of non-coding RNAs that can regulate many protein coding genes by base-paring to messenger RNA (mRNA) targets {% cite Bartel2004 -f {{ bib }} %}. Their roles in gene regulation have been identified in numerous biological processes, such as developmental timing, apoptosis, and cell proliferation {% cite Ambros2004 Stefani2008 -f {{ bib }} %}. The precise mechanism of miRNA targeting is unknown, but animal miRNAs have a small region called ”seed” site (Figure [1](#F:1)), which is located at positions 2-7 of the 5' end of miRNAs and is known to contribute to target recognition significantly {% cite Rajewsky2006 -f {{ bib }} %}. Most target sites are found in the mRNA 3' untranslated region (UTR) {% cite Bartel2004 Lim2005 Grimson2007 -f {{ bib }} %} and are well conserved among closely related species {% cite Ambros2004 -f {{ bib }} %}. A high number of coding genes, except for those with short 3' UTRs such as house keeping genes, are likely regulated by one or multiple miRNAs {% cite Stark2005 -f {{ bib }} %}.

#### &nbsp; {#F:1}
{: .no_toc }
![Figure 1]({{ fig1 }}){:width="{{ page.figs.fig1[1] }}"}

##### **Figure 1**. miRNA seed types.
{: .no_toc .text-caption }
Nine seed types are categorized in two groups; “Stringent” (8mer, 7mer-A1, and 7mer-m8) and “Non-stringent” (6mer, GUM, GUT, LP, BM and BT). GUM and GUT allow one GU wobble in the seed region. GUM has the U on miRNA whereas GUT has the U on the target. LP, BM and BT allow one mismatch. LP has one loop, BM has one bulge on miRNA, and BT has one bulge on the target.
{: .fs-2 }

---

Because of the important genome-wide regulatory roles of miRNAs, many computational approaches have been developed to obtain high-throughput genome-wide miRNA target predictions in animals {% cite Rajewsky2006 Bartel2009 Saito2010 -f {{ bib }} %}. Most existing algorithms first perform sequence search on 3' UTRs to find regions that have complementarity to miRNAs preferably at their seed sites. As this initial step usually results in thousands of potential target sites and many false positives, most algorithms take additional features into consideration; for example, evolutionary conservation filters can decrease the false positive rate, but such filters are effective only for conserved miRNAs with sites of conserved function. Several other features have been experimentally and computationally identified, and we have categorized them into two groups: (i) individual target site level features and (ii) global mRNA level features. The six target site level features currently known are (i.a) site conservation, (i.b) additional base paring in 3' portion of miRNA, especially at positions 13-16 of miRNA {% cite Lewis2003 Grimson2007 -f {{ bib }} %}, (i.c) AU-rich context within 30 nucleotides upstream and downstream from the seed site {% cite Grimson2007 -f {{ bib }} %}, (i.d) avoidance of the region from the stop codon to 15nt downstream in 3' UTR {% cite Grimson2007 Majoros2007 -f {{ bib }} %}, (i.e) tendency of targeting near both ends of 3' UTR when the length of the 3' UTR is >2000 {% cite Gaidatzis2007 Grimson2007 -f {{ bib }} %}, and (i.f) site accessibility {% cite Kertesz2007 Long2007 -f {{ bib }} %}. Furthermore, there are three known mRNA level features: (ii.a) high cooperativity of two miRNA target sites when the distance between them is 17-35 nt {% cite Saetrom2007 -f {{ bib }} %}, (ii.b) length of 3' UTR {% cite Rajewsky2006 -f {{ bib }} %}, and (ii.c) the number of potential target sites per 3' UTR {% cite Enright2003 -f {{ bib }} %}.

Although some algorithms base their predictions on only one of these additional features, such as conservation {% cite Gaidatzis2007 -f {{ bib }} %} or accessibility {% cite Kertesz2007 Long2007 -f {{ bib }} %}, the algorithms commonly use different combinations of features {% cite Saito2010 -f {{ bib }} %}. Most existing algorithms focus on identifying individual target sites, however; few model miRNA targeting at the level of the mRNA and only PicTar tries to explicitly model the contribution of multiple target sites to miRNA regulation {% cite Krek2005 -f {{ bib }} %}.

Here, we describe a novel two-step classification model that recognizes the individual characteristics of functional binding sites and the global properties of mRNAs regulated by candidate miRNAs. We base the model on support vector machines (SVM) {% cite Vapnik1998 -f {{ bib }} %}, use large-scale microarray datasets to train and test the model, and benchmark the model against five popular algorithms – TargetScan {% cite Grimson2007 -f {{ bib }} %}, miRanda (MicroCosm) {% cite Enright2003 Griffiths-Jones2008 -f {{ bib }} %}, PicTar, PITA {% cite Kertesz2007 -f {{ bib }} %}, and mirTarget2 {% cite Wang2008 -f {{ bib }} %}. As these five algorithms represent different prediction strategies and can have different strengths and weaknesses, we have used six different benchmarks that account for overall predictions, highly specific predictions, predictions of conserved sites, and method-specific data variations. Our method performs better than or equivalent to the other existing algorithms in the six benchmarks when tested on different cross-validation experiments or on an independent test set.

## Results and Discussion {#S:3}
Our goal was to create and test a miRNA target prediction approach that modeled both the characteristics of individual target sites and the global properties of mRNAs regulated by candidate miRNAs. Although there are few experimentally validated miRNA targets, several datasets from microarray experiments where miRNAs were ectopically expressed are available for public use {% cite Lim2005 Grimson2007 Linsley2007 -f {{ bib }} %}. High-throughput proteomics experiments have shown that most miRNA targets are regulated at both the mRNA and protein level {% cite Baek2008 Selbach2008 -f {{ bib }} %}, which means that these microarray data are relevant and useful for developing miRNA targeting models. In addition, there are several microarray experiments for small interfering RNA (siRNA) off-target effects {% cite Birmingham2006 Jackson2006 -f {{ bib }} %}. Transfected siRNAs are known to act like miRNAs {% cite Hamilton1999 Zamore2000 -f {{ bib }} %} and degrade numerous unintended (off-target) mRNAs. Consequently, microarray datasets for siRNA off-targets can be used to reveal aspects of miRNA regulation. Unlike miRNA target sites, however, off-target sites for such artificial and exogenous siRNAs are not evolutionary conserved.

We collected four such microarray datasets – two miRNA and two siRNA datasets – to use as training data to develop our method. Based on an analysis of how different seed types covered the positive and negative target candidates within these datasets (see Additional file 1:[Supplementary Results]({{ page_suppl_info }}#S:2-1)), we chose to develop a target-site model that included both stringent and non-stringent seed sites. Our hypothesis was that by including non-stringent seed sites and training two separate SVMs on target site and mRNA-level features, we would create an accurate miRNA target prediction method with high sensitivity and overall prediction performance.

### SVM prediction performs well with target site features {#S:3-1}
The first step of our two-step SVM classification approach was to construct a target site level classifier that can separate positive target sites from negative target sites. To construct this target site level classifier, we included several features known or presumed predictive of miRNA targeting (Additional file 1:Table [S1]({{ page_suppl_info }}#T:S1)). Four sub-steps were applied and then iterated until the most effective classifier was found. First, 10-fold cross-validation was performed to evaluate the prediction ability. Second, a receiver operating characteristic (ROC) curve was plotted to visualize the result of the 10-fold cross-validation and the area under the ROC curve (AUC) was used as a performance measure. The ROC curve and its AUC value, or “ROC score”, is a simple but powerful measure of overall classification performance as the curve shows a classifier’s sensitivity and specificity across all thresholds. Third, as an SVM can take both linear and non-linear kernels with different parameters, models with different kernels were assessed. Fourth, to check the classifier’s robustness across different experimental settings, classifiers were constructed from only three microarray experiments instead of four and tested on the remaining microarray set.

These iterative tests found that a classifier with non-linear, homogeneous polynomial kernel (parameters degree 5 and cost factor 2) showed the best performance with the ROC score 0.70 (Figure [2](#F:2)A). The small standard errors in the ROC plot indicated that all classifiers from this 10-fold cross-validation had similar prediction power and that the models gave robust classifications. This conclusion was supported by similar results for models trained on three of the four microarray experiments (Additional file 1:Figure [S1]({{ page_suppl_info }}#F:S1)). Moreover, all the four classifiers from different combinations of three microarray datasets could classify the remaining one dataset with good ROC scores (Figure [3](#F:3)A-D). These results indicated that our target site level classifiers were stable and accurate across experimental conditions, irrespective of whether the sequences were miRNAs or siRNAs.

#### &nbsp; {#F:2}
{: .no_toc }
![Figure 2]({{ fig2 }}){:width="{{ page.figs.fig2[1] }}"}

##### **Figure 2**. Target site and mRNA level classifiers provide robust and accurate predictions.
{: .no_toc .text-caption }
The ROC curve shows the average true positive rate (sensitivity) vs. false positive rate of the10-fold cross-validations for the target site **(A)** and mRNA level **(B)** classifiers. Error bars show standard errors; the dotted line illustrates random prediction; AUC indicates the average and the standard error of the average of the area under the curve (AUC; ROC Score) of the ten individual cross-validation test results.
{: .fs-2 }

---

#### &nbsp; {#F:3}
{: .no_toc }
![Figure 3]({{ fig3 }}){:width="{{ page.figs.fig3[1] }}"}

##### **Figure 3**. Target site and mRNA level classifiers generalize to microarray datasets not seen during training.
{: .no_toc .text-caption }
The ROC graphs show the performance of four target site level classifiers **(A-D)** and four mRNA level classifiers **(E-H)** trained on three microarray datasets and tested on the remaining one dataset. Dotted lines illustrate random prediction. The ROC score is shown in the box. TPR indicates True positive rate, while FPR indicates False positive rate. Figure headings state the dataset used for testing.
{: .fs-2 }

---

### Seed type shows the strongest influence on target site level training {#S:3-2}
It is important to identify the influence of the features on the SVM’s prediction accuracy, as this can reveal new information about miRNA target recognition. To evaluate the influence of all the target site level features used in our model, 10-fold cross-validation was performed repeatedly with eliminating only one feature at a time, and then ROC scores were compared. These experiments showed that the “seed type” was the strongest feature with a reduced ROC score of 0.03 (Additional file 1:Table [S2]({{ page_suppl_info }}#T:S2)). Reduced ROC scores indicate that the feature is important, as the SVM would have more prediction power with the feature included. Other features showed little or no decline of ROC scores, but none had substantial negative effects.

### Genes with long 3' UTRs tend to have few positive target sites in microarray experiments {#S:3-3}
While constructing and analyzing the mRNA level training data, we noticed that genes with more than 8 potential target sites appeared to be underrepresented among the positives. This was contrary to our expectations, as experimental data indicate that additional target sites give increased target repression {% cite Doench2003 -f {{ bib }} %}. Additional analyses revealed two trends. First, genes with long 3' UTRs (>5000nt) did generally not appear to be miRNA targets – irrespective of the genes’ number of potential miRNA target sites (Figure [4](#F:4)). Second, positive targets generally had a higher density of potential target sites (Kolmogorov-Smirnov test, p-value: 4e-11) – that is, number of sites divided by the 3' UTR length – than negative target candidates had (Additional file 1:Figure [S2]({{ page_suppl_info }}#F:S2)).

#### &nbsp; {#F:4}
{: .no_toc }
![Figure 4]({{ fig4 }}){:width="{{ page.figs.fig4[1] }}"}

##### **Figure 4**. Fewer positive target sites for genes with long 3' UTRs.
{: .no_toc .text-caption }
The boxplot shows the lengths of 3' UTRs grouped by the number of potential target sites in the training dataset. Red boxes represent down regulated UTRs, whereas blue boxes represent unaffected UTRs. No down-regulated genes have more than 8 potential target sites and few down-regulated genes have long 3' UTRs (>5000nt). The range of potential target site number is from 1 to 28 plus 32 and 38.
{: .fs-2 }

---

One possible explanation for this result is competition between transfected RNAs and endogenous miRNAs {% cite Khan2009 -f {{ bib }} %}. Genes with long 3' UTRs tend to be targeted by several endogenous miRNAs, therefore the transfected RNAs may have less effect on these genes. Another possible explanation for this result is that genes with long 3' UTRs have fewer target sites within these active regions because active sites are preferentially located close to the stop codon or poly-A site within long 3' UTRs {% cite Grimson2007 -f {{ bib }} %}. However, we found that the positive targets and negative target candidates had a similar number of target sites within the regions close to the stop codon and poly-A site (data not shown). Thus, a high density of target sites within the middle region of long 3' UTRs appeared to be important for target regulation.

We used two approaches to take this unexpected distribution of true positive targets into consideration. First, a new binary feature was introduced to distinguish the genes with less than 7 potential target sites from the others. Second, 1000 randomly selected non-target genes with more than 7 target sites were explicitly added to the training data. Because of a practical limitation on the maximum number of training data, most of these none-target genes with long 3' UTRs would otherwise have been excluded if we had constructed the training data by random sampling. These two approaches had a positive effect on target predictions for genes with many target site candidates (Additional file 1:Figure [S3]({{ page_suppl_info }}#F:S3)).

### mRNA features improve SVM predictions {#S:3-4}
The second step of our two-step SVM classification approach was to construct an mRNA level classifier that can separate down-regulated genes from non down-regulated genes. This subdivision enabled us to incorporate features related to the predicted strength of individual target sites and the distance between these sites that had not been used in other algorithms before (Additional file 1:Table [S3]({{ page_suppl_info }}#T:S3)). We used the same four steps as for the target site level to find the most effective mRNA level classifier.

The classifier showed the best performance when a linear kernel with default parameters was used (ROC score 0.80). As for the target site level, the ROC curve for the classifier had small standard errors, indicating robust classifications (Figure [2](#F:2)B). Target predictions also retained good performance with classifiers trained with only three microarray datasets (Additional file 1:Figure [S4]({{ page_suppl_info }}#F:S4)). These classifiers could also predict the remaining data set with good accuracy (Figure [3](#F:3)E-H), but the classifiers showed increased variation between the datasets compared with the corresponding target site level classifiers. Whereas the mRNA level classifiers greatly improved upon the target site level classifiers’ performance on the miRNA data (compare panels B and F, and D and H in Figure [3](#F:3)), the mRNA level classifiers gave smaller improvements on the siRNA data (panels A and E, and C and G in Figure [3](#F:3)). Thus, the targets for exogenous siRNAs were more difficult to predict than the targets for endogenous miRNAs were – at least in the datasets used in these experiments. This could not be explained by different preferences for strand loading between the miRNAs and siRNAs, as removing the siRNAs where the intended guide strand was not clearly preferred for RISC incorporation did not improve the SVM’s performance (data not shown). Despite these differences, the mRNA level classifier showed good improvement compared with the target site level classifier and could predict target genes with high accuracy.

### Number and strength of putative miRNA target sites strongly predict miRNA regulation {#S:3-5}
As for the target site level features, we wanted to determine to what extent the different mRNA level features influenced target predictions. We therefore performed a similar evaluation of feature influence for the mRNA level. The result showed that the “distribution of discriminant values” was the strongest feature with a reduced ROC score of 0.04 (Additional file 1:Table [S4]({{ page_suppl_info }}#T:S4)). Eliminating other features had little effect on the ROC scores, but additional analyses showed that at least the target-site distance features contributed to separate the down-regulated from the unaffected genes (see Additional file 1:[Supplementary Results]({{ page_suppl_info }}#S:2-2)). As the “distribution” feature essentially counted the number of high-scoring putative target sites within the mRNA, these results showed that strong target sites are important for miRNA regulation.

The target site level feature analyses indicated that target site accessibility and conservation had little or no effect on the SVM’s predictive performance and additional analyses at the mRNA level confirmed these results (see Additional file 1:[Supplementary Results]({{ page_suppl_info }}#S:2-3)). As computing site accessibility and conservation require substantial computational resources, we excluded these features from the final model. Recently, a tool based on support vector regression (SVR) reported improved target prediction performance {% cite Betel2010 -f {{ bib }} %}. We also tested whether using SVR instead of classification would further improve the results, but instead found that SVR gave reduced performance (see Additional file 1:[Supplementary Results]({{ page_suppl_info }}#S:2-4)).

### Two-step SVM shows strong prediction ability and outperforms other algorithms when tested on independent dataset {#S:3-6}
Both the 10-fold cross-validation and single dataset hold-out experiments showed that the two-step SVM classifiers could predict miRNA target sites in unseen data with high accuracy. Nevertheless, to further test the SVM classifiers, we evaluated the classifiers on an independent test set and compared their performance with those of other existing target prediction algorithms. We included seven popular miRNA target prediction algorithms – PITA All, PITA Top, TargetScan, TargetScan with conserved genes, miRanda (MicroCosm), mirTarget2, and PicTar – in the comparisons, and used the Linsley dataset because only mirTarget2 had used this microarray dataset as a training set. The predictions of three algorithms – our SVM approach, PITA All, and TargetScan – were generated without conservation information, but the predictions of the other algorithms were generated with conservation information as features or filters. We included mirTarget2 as a reference – despite mirTarget2 using the Linsley dataset for training – because the algorithm, similar to our two-step SVM, adopted a machine learning approach.

The algorithms’ predictions had little overlap because all algorithms used different definitions of potential target sites. Hence, it was important to use different datasets to assess and compare the algorithms’ prediction performance precisely. We used six types of datasets as benchmarks; these were, ROC with All genes, ROC10*n, ROC with 7mer + Conservation, and ROC with TargetScan, miRanda, and PicTar datasets (see Additional file 1:[Supplementary Methods]({{ page_suppl_info }}#S:1-3)).

The “ROC with All genes” dataset was comprised of all the records from the microarray dataset. Down regulated (positive) and unaffected (negative) genes were decided solely by the microarray results regardless of seed matching or any other definitions set by different algorithms. The purpose of using this dataset was to evaluate the algorithms’ overall performance on the entire microarray experiment. The resulting ROC curves showed that our SVM approach outperformed the other seven algorithms in terms of sensitivity and overall target recognition (Figure [5](#F:5)A). The number of positive genes found by our SVM approach was 564, which was the largest among all the algorithms (Additional file 1:Table [S5]({{ page_suppl_info }}#T:S5)). In comparison, PITA All found a similar number of positive genes, but its predictions were less specific than our SVM’s predictions were. At similar true positive rates, PITA All returned more false positives, which resulted in a difference in ROC score of 0.05 between SVM and PITA All. Similar to PITA, miRanda returned less specific predictions than the other algorithms did, although miRanda’s predictions were more specific than PITA All’s at similar true positive rates. miRanda also had the lowest sensitivity of the different algorithms. Apart from differences in sensitivity, the remaining algorithms had similar prediction specificities; mirTarget2 appeared to give slightly more specific predictions than the other algorithms did, but our SVM appeared to have the highest specificity of the methods for which the Linsley set truly was an independent test set. These differences were small, however, and only apparent for the algorithms’ most sensitive predictions.

#### &nbsp; {#F:5}
{: .no_toc }
![Figure 5]({{ fig5 }}){:width="{{ page.figs.fig5[1] }}"}

##### **Figure 5**. Benchmarks show the performances of 8 different prediction algorithms.
{: .no_toc .text-caption }
Receiver operating characteristic (ROC) graphs show the performances of 8 different target prediction algorithms – SVM, PITA All (PITA), PITA Top (PITA_top), TargetScan (TargetS), TargetScan with conserved genes (TargetS_c), MicroCosm miRanda (miRanda), mirTarget2 and PicTar – on the Linsley dataset. Dotted lines illustrate random prediction. The ROC scores are shown in the legend box. The benchmarks used for the evaluation were **(A)** ROC with All genes, **(B)** ROC10*n, and **(C)** ROC with 7mer + Conservation.
{: .fs-2 }

---

To elucidate the algorithms’ performance at highly specific target predictions, we turned to the “ROC10\*n” benchmark (Figure [5](#F:5)B), which is a modified version of ROC50 {% cite Gribskov1996 -f {{ bib }} %} that shows the algorithms’ performance up to 10 \* n false positive predictions (n is the number of miRNAs in the dataset; n = 9 for the Linsley set). Although the SVM’s ROC10\*n score is slightly lower than those of the two TargetScan versions and mirTarget2, the SVM again has the highest sensitivity of the algorithms (excluding mirTarget2 and PicTar). Similarly, PITA All again shows very low sensitivity, whereas PicTar and miRanda have similar performance. Thus, the results from the ROC10*n benchmark indicate that our SVM approach has very good performance with top scored genes (Figure [5](#F:5)B).

As many of the algorithms only considered stringent seed types and filtered predictions based on conservation, we constructed the “ROC with 7mer + Conservation” benchmark. The benchmark only consisted of the genes with stringent seeds found in conserved regions. Consequently, the benchmark essentially only considered the most likely candidate miRNA target genes and showed how good the different algorithms are at finding the real targets among genes that all are likely targets. Despite that our approach was not optimized for this type of dataset, the SVM delivered more sensitive and specific predictions than the other methods (Figure [5](#F:5)C; again excluding mirTarget2). Interestingly, the algorithms optimized for recognizing conserved stringent seed targets – TargetScan with conserved genes, PITA Top and PicTar – all had markedly lower performance than the SVM. One likely explanation for this result is that other non-conserved seeds within the genes are important for miRNA targeting as well. Supporting this hypothesis, TargetScan – which also considers non-conserved seeds – had a markedly better performance than TargetScan with conserved genes. miRanda showed especially poor performance on the conservation benchmark, but this was likely because the miRanda predictions had very few overlaps with the benchmark dataset due to different conservation filtering. Indeed, miRanda had better performance on its method-specific benchmarks (Additional file 1:Figure [S5]({{ page_suppl_info }}#F:S5), [S7]({{ page_suppl_info }}#F:S7), and [S9]({{ page_suppl_info }}#F:S9). The three method-specific benchmarks that use different definitions of sequence conservation and separate benchmark tests on the four training datasets also showed similar results as the 7mer + Conservation benchmark (Additional file 1:Figure [S5]({{ page_suppl_info }}#F:S5)-[S9]({{ page_suppl_info }}#F:S9)). Thus, lack of conservation does not guarantee lack of function, and effectively incorporating all seed types in a common prediction framework, such as our SVM, appears to be essential for correctly prioritizing lists of candidate miRNA targets.

### Two-step SVM’s improved performance holds when detecting protein level targets {#S:3-7}
Although several recent studies have suggested the possibility of mRNA repression as miRNA’s major regulatory mode {% cite Baek2008 Selbach2008 -f {{ bib }} %}, it is still interesting to verify the prediction power at both mRNA and protein levels. We therefore used two publically available proteomics datasets of miRNA targeting, Baek {% cite Baek2008 -f {{ bib }} %} and Selbach {% cite Selbach2008 -f {{ bib }} %}, as training sets to create a new proteomics-based two-step SVM classifier and as independent datasets to test the mRNA-based two-step SVM classifier. The proteomics-based SVM showed comparable performance to the mRNA-based SVM (Additional file 1:Figure [S14]({{ page_suppl_info }}#F:S14)), which indicated that features important for predicting mRNA-level miRNA targets are also relevant for predicting protein-level targets. Indeed, when we benchmarked the mRNA-based classifiers against the Selbach and Baek datasets, the SVM outperformed the other seven algorithms in most cases and especially on the ROC10*n benchmarks (Figure [6](#F:6); Table [1](#T:1)). Note that on these two sets, which were true independent test sets for mirTarget2 and therefore should be more representative of the method’s performance than the Linsley set, mirTarget2 had similar or slightly lower performance than the two TargetScan versions. These results as well as additional benchmark results (Additional file 1:Figure [S15]({{ page_suppl_info }}#F:S15), [S16]({{ page_suppl_info }}#F:S16); Table [S8]({{ page_suppl_info }}#T:S8), [S9]({{ page_suppl_info }}#T:S9)) suggest that our two-step SVM approach is also effective at detecting target genes at protein level.

#### &nbsp; {#F:6}
{: .no_toc }
![Figure 6]({{ fig6 }}){:width="{{ page.figs.fig6[1] }}"}

##### **Figure 6**. Benchmark results on proteomics data confirms the two-step SVM’s strong performance.
{: .no_toc .text-caption }
Receiver operating characteristic (ROC) graphs show the performance of 8 different target prediction algorithms on the two proteomics datasets, Selbach **(A, B, and C)** and Baek **(D, E, and F)**. The benchmarks used for the evaluation were **(A)** and **(D)**
ROC with All genes, **(B)** and **(E)** ROC10*n, **(C)** and **(F)** ROC with 7mer +
Conservation. See Figure [5](#F:5) for details regarding the algorithms.
{: .fs-2 }

---

#### **Table 1**. ROC scores of one transcriptomics and two proteomics datasets. {#T:1}
{: .no_toc .text-caption }

{% include tbl_simple.html data=tab1 %}

Three benchmarks, All, ROC10*n, 7m+C (7mer+Conservation), were performed on one transcripomics (Linsley) and two proteomics (Baek and Selback) datasets. The ROC scores were calculated for eight algorithms, SVM, PITA, TScan (TargetScan), miRan (miRanda), PITAT (PITA Top), TS_C (TargetScan with conserved genes), mirT2 (mirTarget2) and PicTa (PicTar).
{: .fs-2 }

---

### Different criteria of dataset selection do not affect SVM performance {#S:3-8}
We trained and tested our model with alternative data selection criteria to analyze the influence of data selection on the target prediction power. We verified two data selection criteria, (i) inclusion and exclusion of up regulated targets in the negative record sets, and (ii) different log ratio threshold values to create positive record sets. The results suggest that our SVM approach is very flexible and robust, and it can retain its performance even when trained and tested on datasets created by different parameter settings (see Additional file 1:[Supplementary Results]({{ page_suppl_info }}#S:2-5)).

## Conclusions {#S:4}
We have presented and evaluated a novel two-step SVM-based miRNA target prediction model that recognizes the individual characteristics of functional binding sites and the global characteristics of miRNA-targeted mRNAs. When tested on several different benchmarks, the model generally outperformed other well-known miRNA target prediction algorithms. In particular, the two-step SVM showed a much stronger ability to identify true miRNA targets among genes that all are likely targets with conserved stringent seed sites.

The model relies on several target site and mRNA characteristics and its design is flexible so that it is easy to integrate new characteristics when such are reported. Our current model does not include target site accessibility and conservation information, however, as our tests showed that these were not important features in our model. This result is very important for genome-wide analysis because assessing target site conservation and especially target site accessibility have high computational costs. Consequently, the model can for example be used online for identifying siRNA off-targets.

By modeling miRNA targeting in two steps – recognition of individual target sites and regulation of mRNA – we have incorporated several new characteristics neglected by other tools, such as miRNAs’ distance dependence for synergistic regulation. Moreover, through this two-step modeling, we have introduced several features that effectively capture the number and relative strength of individual target sites within target candidates. Our results show that these features are the most important characteristics for identifying miRNA-regulated genes.

A potential limitation is that our model is trained on data from over-expression experiments, which to some extent are affected by interactions with endogenous miRNAs {% cite Khan2009 -f {{ bib }} %}. Including data from Argonaute (AGO) pull-down {% cite Karginov2007 Hendrickson2008 Chi2009 Hafner2010 -f {{ bib }} %} or miRNA knock-down {% cite Linsley2007 Baek2008 Selbach2008 -f {{ bib }} %} experiments could reduce potential bias from such interactions, but may also introduce additional bias. Most of the current AGO pull-down experiments were, for example, done with ectopically expressed and tagged AGO-fusion proteins {% cite Karginov2007 Hendrickson2008 Hafner2010 -f {{ bib }} %}. As for miRNA knock-down, there are currently few datasets available.

Another potential limitation is that our model was trained on data from human cell lines. Although the miRNA regulatory mechanisms appear to be shared in animals, we cannot discount species-specific variation, which may result in the current human-optimized model having sub-optimal performance in, for example, invertebrates. Testing and optimizing the model on high-throughput data from additional species – especially species that are remotely related to humans – would therefore be interesting future work.

Even though our new model represents a significant step towards accurate miRNA target prediction, it is still challenging to achieve very precise target predictions because many miRNAs have spatial, temporal, or cell-type-specific expression. Integrating target predictions with expression profiles of miRNAs and putative targets can be one way to improve predictions; for example, by taking into account miRNA saturation {% cite Khan2009 -f {{ bib }} %}, target concentration {% cite Arvey2010 -f {{ bib }} %}, or expression of RNA binding proteins {% cite Jacobsen2010 -f {{ bib }} %}. Our two-step SVM should be ideal for such analyses, as it has a high sensitivity and better overall performance compared with existing target prediction methods.

## Methods {#S:5}
### Datasets {#S:5-1}
We downloaded the Jackson {% cite Jackson2006 -f {{ bib }} %}, Lim {% cite Lim2005 -f {{ bib }} %},  Grimson {% cite Grimson2007 -f {{ bib }} %}, and Linsley {% cite Linsley2007 -f {{ bib }} %} datasets from the Gene Expression Omnibus (GEO) database [GEO:GSE5814, GEO:GSE2075, GEO:GSE8501, GEO:GSE6838] {% cite Barrett2007 -f {{ bib }} %} and the Birmingham {% cite Birmingham2006 -f {{ bib }} %} dataset from the ArrayExpress database [ArrayExpress:E-MEXP-668] {% cite Parkinson2009 -f {{ bib }} %}. We mapped microarray probes to human RefSeq transcripts (hg18) based on GEO and ArrayExpress annotations and downloaded 3' UTR sequences from the University of California, Santa Cruz {% cite UCSC2010 -f {{ bib }} %}. Two proteomics datasets, Selbach {% cite Selbach2008 -f {{ bib }} %} and Baek {% cite Baek2008 -f {{ bib }} %}, were obtained from the original publications along with miRBase and RefSeq IDs. MicroRNA and siRNA sequence data (Additional file 1:Table [S6]({{ page_suppl_info }}#T:S6)) were obtained from miRBase (release 14.0) {% cite Griffiths-Jones2008 -f {{ bib }} %} and from the original publications, respectively. We used several criteria, including p-values and log intensity ratios (see Additional file 1:[Supplementary Methods]({{ page_suppl_info }}#S:1-1)), to divided the data into positive (down-regulated) and negative genes.

### Construction of target site level features {#S:5-2}
Potential target sites were identified by nine seed types (8mer, 7mer-A1, 7mer-m8, 6mer, GUM, GUT, LP, BM and BT) in human 3' UTRs between position 15 from the stop codon and the 3' end. Partially overlapping sites were only allowed among the sites with 8mer, 7mer-A1, 7mer-m8, and 6mer. The precedence of selecting a target site among overlapping sites was defined as 8mer = 7mer-A1 = 7mer-m8 = 6mer > GUM > GUT > LP > BM > BT. Consequently, if a GUM and GUT site overlapped, the GUM site was selected. Target sites and their corresponding miRNAs were aligned using the emboss needle software {% cite Rice2000 -f {{ bib }} %}; see Additional file 1:Table [S7]({{ page_suppl_info }}#T:S7) for needle parameters.
We used 24 target site level features (Additional file 1:Table [S1]({{ page_suppl_info }}#T:S1)). Site accessibility features were created by the PITA software (version 3) by considering either no flanking regions or flanking regions consisting of 3 nts upstream and 15 nts downstream of the site {% cite Kertesz2007 -f {{ bib }} %}. Evolutionary conservation scores were calculated from phastCons 44, phyloP 44, and multiz 17-way {% cite Blanchette2004 Siepel2005 Pollard2010 -f {{ bib }} %} scores downloaded from UCSC. The phastCons 44 scores were used to calculate the average score of the whole target site (position 1 to 20), whereas the phyloP 44 scores were used as the conservation scores of the seed site (position 1 to 8). All feature values were normalized into values ranged between -1 and 1 by a linear transform based on the feature’s minimum and maximum values among the sites in the training set.

### Construction of mRNA level features {#S:5-3}
Construction of mRNA level training data was done in three steps. First, discriminant values, which are the output values from SVM classification, were obtained from the target site level 10-fold cross-validation test sets. In our model, these discriminant values represented the predicted regulatory strength of each target site. Second, discriminant values were matched to mRNAs such that an mRNA with for example three miRNA target sites would have three discriminant values – one value for each site. Third, the discriminant values and other information about the target sites and the 3' UTR were used to calculate 17 mRNA level features (Additional file 1:Table [S3]({{ page_suppl_info }}#T:S3)).

SVMs require fixed-length feature vectors, but the number of target sites varies between mRNAs. Consequently, to represent the number and predicted strength of individual target sites within a given mRNA, we used a feature representation that encoded the overall distribution of target site level discriminant values. For each mRNA, this feature consisted of 16 values that counted the number of target site discriminant values that fell within given percentile ranges of the overall discriminant value distribution. Specifically, two feature values counted the number of upper and lower extreme discriminant values greater than and less than two standard deviations away from the distribution mean. The remaining 14 feature values counted the number of discriminant values falling within the bins defined by the 25.00, 43.75, 57.81, 68.36, 76.27, 82.20, 86.65, 89.99, 92.49, 94.37, 95.78, 97.19, 98.6, and 100 percentiles when the upper and lower extreme values were removed from the discriminant value distribution. We used these percentile thresholds because we expected a high resolution at the upper tail of the discriminant value distribution to be useful for predictions. Supporting this hypothesis, replacing these 14 thresholds with 14 uniformly spaced thresholds gave markedly poorer SVM performance (data not shown).

### Target site / mRNA level training {#S:5-4}
We used the PyML library (Version 0.72) {% cite PyML2010 -f {{ bib }} %} for SVM training, 10-fold cross-validation, classification, and evaluation, and the R package ROCR {% cite Sing2005 -f {{ bib }} %} to plot Receiver Operating Characteristics (ROC) curves and to calculate the area under the ROC curve (AUC).
To optimize our model, we tested a linear kernel and three non-linear kernels – Gaussian, homogeneous polynomial, and inhomogeneous polynomial. In addition to the four kernel types, three parameters – cost factor (C), gamma (γ), and degree (d) – were tested. The parameter ranges were C = 2(2n - 5) (0 ≤ n ≤ 11), γ = 2(2n - 13) (0 ≤ n ≤ 10), and d = n (2 ≤ n ≤ 8) as previously recommended {% cite Hsu2003 -f {{ bib }} %}.

### Data retrieval for benchmarks {#S:5-5}
Prediction data were downloaded from the PITA, TargetScan, MicroCosm, miRDB, and PicTar websites (see Additional file 1:[Supplementary Methods]({{ page_suppl_info }}#S:1-2)).

## Additional files {#S:6}
Additional file 1 – [Supplementary information]({{ page_suppl_info }}) \
File name: [supplementary_information.pdf]({{ site.baseurl }}/assets/Saito_2010_Two_step_SVM_supplementary_information.pdf) \
File format: PDF \
The file contains five sections of supplementary information, and the sections are: [Supplementary Methods]({{ page_suppl_info }}#S:1) (3 subsections), [Supplementary Results]({{ page_suppl_info }}#S:2) (6 subsections), [Supplementary Tables]({{ page_suppl_info }}#S:3) (15 tables), [Supplementary Figures]({{ page_suppl_info }}#S:4) (22 figures), and the [Reference]({{ page_suppl_info }}#S:5).

## Authors' contributions {#S:7}
Both authors contributed to the underlying ideas of the method and the analysis. TS implemented the model. The initial manuscript draft was written by TS, and refined by PS. Both authors read and approved the final manuscript.

## Acknowledgements {#S:8}
This work was supported by the Functional Genomics Program (FUGE) of the Norwegian Research Council.

## References {#S:9}
{% bibliography --cited_in_order -f {{ bib }} %}
