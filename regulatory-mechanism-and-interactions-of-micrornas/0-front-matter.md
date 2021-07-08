---
layout: default
title: 0 Front matter
parent: Overview
nav_order: 1
description: "Front matter"
folders:
  thesis: regulatory-mechanism-and-interactions-of-micrornas
  prediction: mirna-target-prediction
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
pages:
  review: micrornas-targeting-and-target-prediction
  two_step_svm: two-step-svm-model
  confounding: confounding-factors-in-mirna-experiments
---

{% capture path_thesis %}{{ site.baseurl }}/{{ page.folders.thesis }}{% endcapture %}
{% capture path_prediction %}{{ site.baseurl }}/{{ page.folders.prediction }}{% endcapture %}
{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

# Computational analysis of regulatory mechanism and interactions of microRNAs
{: .no_toc .text-center }

Takay Saito
{: .text-center }

Faculty of Medicine  <br />
Norwegian University of Science and Technology
{: .fs-3 .text-center .text-grey-dk-000 }

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

## Abstract {#S:0.1}
For years, RNAs were thought to have only two broad functions in cells,
transmitting information between DNA and protein as messenger RNA
(mRNA), and playing structural, catalytic, information decoding roles in
protein synthesis as ribosomal RNA (rRNA) and transfer RNA (tRNA).
However, the discovery of RNA interference (RNAi) changed this picture.
RNAi is a regulatory process that uses small non-coding RNAs (ncRNAs)
to suppress gene expression at the post-transcriptional level. This discovery
led to identification of many classes of functional ncRNAs. MicroRNA
(miRNA) is a class of such ncRNAs with ∼22 nucleotides that are abundant
and found in most eukaryotic cells. This thesis focuses on revealing regulatory
roles and characteristics of miRNAs through bioinformatics approaches
by addressing three research questions.

The first research question is whether we can enhance miRNAs target prediction
in animals by considering multiple target sites. Many algorithms
exist for miRNA target predictions, but most algorithms do not consider
multiple target sites. Predicting accurate miRNA target genes is important
to infer miRNA regulatory roles since annotations of miRNA regulations
are still poor. To solve this possible fault, we developed a two step support
vector machine (SVM) model. Benchmark tests showed that our two step
model outperformed other existing miRNA target prediction algorithms.

The second research question is whether there are factors to explain differences
between different miRNA high-throughput experiments. There are
several high-throughput technologies widely used for miRNA experiments,
such as microarray and quantitative proteomics, but the results from these
technologies are often inconsistent. By statistically analyzing several such
high-throughput miRNA experiments, we revealed the characteristic of different
technologies and also identified several factors that cause the differences.

The third research question is whether miRNAs interact with other classes
of ncRNAs. There are strong evidences that some miRNAs are involved in
transcription by interacting with other ncRNAs. We investigated ncRNAs
in complex loci to find potential miRNA:ncRNA interactions. A complex
locus is a locus that contains multiple genes that interact between themselves.
We found evidence that some miRNAs are involved in transcriptional
regulation with ncRNAs in complex loci.

In summary, this thesis provides solutions for these research questions, and
it contributes to a better understanding of several important aspects of
miRNA characteristics and regulations. It also shows effective bioinformatics
approaches to develop a robust machine learning model and analyze
different miRNA high-throughput experiments.

## Acknowledgements {#S:0.2}
This thesis is based on four years of research funded by the Functional
Genomics Program of the Norwegian Research Council. During the course
of the research I have been helped by many individuals.

First and foremost, I would like to thank my two supervisors. I owe my
deepest gratitude to Pål Sætrom for his contributions of time, ideas, and
guidance to make this thesis possible. His wide knowledge and logical way
of thinking have been of great value to me. I also gratefully acknowledge
Finn Drabløs for his supervision. He has helped to make bioinformatics fun
for me throughout my PhD.

I am indebted to the members of the Bioinformatics and Gene Regulation
group for their contributions to providing an excellent working environment.
I am especially grateful to Laurent Thomas and Even Skaland for
their collaboration. I am also grateful to Tony Håndstad for his advice on
manuscript preparation.

I would like to thank my friends and colleagues for making my time at
NTNU tremendously enjoyable.

Lastly, I wish to thank my parents, Kikuo Saito and Mihoko Saito, for their
love and support. Arigatou.

## Contents {#S:0.3}

- [List of Figures](#S:0.4)

- [List of Tables](#S:0.5)

- [List of Papers](#S:0.6)

- [Glossary](#S:0.7)

1. [Introduction]({{ path_thesis }}/1-introduction/)

   - [1.1 Challenges]({{ path_thesis }}/1-introduction/#S:1.1)

   - [1.2 Goals]({{ path_thesis }}/1-introduction/#S:1.2)

   - [1.3 Thesis structure]({{ path_thesis }}/1-introduction/#S:1.3)

   - [References]({{ path_thesis }}/1-introduction/#S:1.4)

2. [Papers and their corresponding sub-goals]({{ path_thesis }}/2-papers-and-their-corresponding-sub-goals/)

   - [2.1 Three papers for the first sub-goal: miRNA target prediction]({{ path_thesis }}/2-papers-and-their-corresponding-sub-goals/#S:2.1)

   - [2.2 One paper for the second sub-goal: miRNA high-throughput experiments]({{ path_thesis }}/2-papers-and-their-corresponding-sub-goals/#S:2.2)

   - [2.3 One paper for the third sub-goal: miRNA and other ncRNAs]({{ path_thesis }}/2-papers-and-their-corresponding-sub-goals/#S:2.3)

3. [MicroRNAs and other non-coding RNAs]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/)

   - [3.1 Thousands of miRNAs have been identified since the first miRNA discovery of lin-4 in 1993]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.1)

   - [3.2 MicroRNA biogenesis involves multiple steps]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.2)

   - [3.3 RNA interference is the central mechanism for gene regulation by miRNAs and small interfering RNA]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.3)

   - [3.4 MicroRNAs have various regulatory roles that are associated with important physiological and pathological processes]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.4)

   - [3.5 Multiple properties of miRNA target recognition may enhance target efficacy in animal]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.5)

   - [3.6 MicroRNA binding also occurs outside of the 3' UTR]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.6)

   - [3.7 Some of coding and non-coding pairs of cis-NATs potentially may have regulatory interactions with miRNAs]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.7)

   - [3.8 Chromatin associated RNAs are potentially associated with the modification of chromatin structure]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.8)

   - [References]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#S:3.9)

4. [High-throughput biological experiments]({{ path_thesis }}/4-high-throughput-biological-experiments/)

   - [4.1 One microarray experiment can detect thousands of gene expressions]({{ path_thesis }}/4-high-throughput-biological-experiments/#S:4.1)

   - [4.2 The next generation sequencing methods are faster and more cost-effective than Sanger sequencing]({{ path_thesis }}/4-high-throughput-biological-experiments/#S:4.2)

   - [4.3 The second generation sequencing technologies can cover a wide range of applications]({{ path_thesis }}/4-high-throughput-biological-experiments/#S:4.3)

   - [4.4 Liquid chromatography-tandem mass spectrometry is a powerful tool to analyze quantitative proteomics]({{ path_thesis }}/4-high-throughput-biological-experiments/#S:4.4)

   - [4.5 Most preprocessed and raw data sets from high-throughput experiments are publicly available]({{ path_thesis }}/4-high-throughput-biological-experiments/#S:4.5)

   - [References]({{ path_thesis }}/4-high-throughput-biological-experiments/#S:4.6)

5. [Statistical tests and methods]({{ path_thesis }}/5-statistical-tests-and-methods/)

   - [5.1 Parametric statistics: Parameters and Hypothesis testing]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.1)

   - [5.2 Non-parametric statistical methods: Wilcoxon rank-sum and Kolmogorov-Smirnov tests]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.2)

   - [5.3 Resampling: Bootstrap and Permutation test]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.3)

   - [5.4 Multiple comparison tests: Analysis of variance, Bonferroni correction, and False discovery rate]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.4)

   - [5.5 Correlation: Pearson’s and Spearman’s correlation coefficients]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.5)

   - [5.6 Regression analysis: Multivariate linear regression]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.6)

   - [References]({{ path_thesis }}/5-statistical-tests-and-methods/#S:5.7)

6. [Machine learning theory and Support vector machine]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/)

   - [6.1 Machine learning: Supervised and Unsupervised]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.1)

   - [6.2 SVM: Theory]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.2)

   - [6.3 SVM: Linear SVM]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.3)

   - [6.4 SVM: Non-linear SVM]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.4)

   - [6.5 Classifier evaluation: Confusion matrix and Receiver operating characteristics]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.5)

   - [6.6 Training and Test data: Single dataset hold-out and k-fold cross validation]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.6)

   - [6.7 SVM: Data pre-processing]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.7)

   - [6.8 SVM: Model selection]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.8)

   - [6.9 SVM: Multiclass and Regression]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.9)

   - [6.10 Other supervised learning algorithms: Decision tree, Artificial neural network, Naive Bayesian, and k-nearest neighbor]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.10)

   - [References]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#S:6.11)

7. [Computational implementation]({{ path_thesis }}/7-computational-implementation/)

   - [7.1 Software development methodologies: Rapid application development and Test-driven development]({{ path_thesis }}/7-computational-implementation/#S:7.1)

   - [7.2 Programming languages: Object-oriented programming and Python]({{ path_thesis }}/7-computational-implementation/#S:7.2)

   - [7.3 Statistical programming languages: R and other statistical computing languages]({{ path_thesis }}/7-computational-implementation/#S:7.3)

   - [7.4 Data storage: Text files and MySQL]({{ path_thesis }}/7-computational-implementation/#S:7.4)

   - [References]({{ path_thesis }}/7-computational-implementation/#S:7.5)

8. [Future perspectives]({{ path_thesis }}/8-future-perspectives/)


## List of Figures {#S:0.4}

  - [1.1 PubMed query]({{ path_thesis }}/1-introduction/#F:1.1)

  - [3.1 MicroRNA biogenesis]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#F:3.1)

  - [3.2 miRNA target]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#F:3.2)

  - [3.3 miRNA seed types]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#F:3.3)

  - [3.4 Complex loci]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#F:3.4)

  - [3.5 miRNA regulation on cis-NAT]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#F:3.5)

  - [3.6 CARs]({{ path_thesis }}/3-micrornas-and-other-non-coding-rnas/#F:3.6)

  - [4.1 Microarray procedure]({{ path_thesis }}/4-high-throughput-biological-experiments/#F:4.1)

  - [6.1 SVM hyperplanes and maximum margin]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#F:6.1)

  - [6.2 Linear kernel with soft margin]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#F:6.2)

  - [6.3 Non-linear kernels]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#F:6.3)

  - [6.4 ROC curves and AUC scores]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#F:6.4)


## List of Tables {#S:0.5}

  - [2.1 Papers and corresponding sub-goals of our research]({{ path_thesis }}/2-papers-and-their-corresponding-sub-goals/#T:2.1)

  - [4.1 Next generation sequencing technologies]({{ path_thesis }}/4-high-throughput-biological-experiments/#T:4.1)

  - [5.1 Four possible outcomes of hypothesis testing]({{ path_thesis }}/5-statistical-tests-and-methods/#T:5.1)

  - [6.1 Confusion matrix]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#T:6.1)

  - [6.2 Performance measures from confusion matrix]({{ path_thesis }}/6-machine-learning-theory-and-support-vector-machine/#T:6.2)

  - [7.1 Programming languages]({{ path_thesis }}/7-computational-implementation/#T:7.1)

  - [7.2 Programming languages for statistical analysis]({{ path_thesis }}/7-computational-implementation/#T:7.2)

  - [7.3 Relational databases]({{ path_thesis }}/7-computational-implementation/#T:7.3)


## List of Papers {#S:0.6}

[Paper 1]({{ path_prediction }}/{{ page.pages.review }}/)
: **MicroRNAs - targeting and target prediction**
: Takaya Saito and Pål Sætrom
: New biotechnology 2010
: DOI: [10.1016/j.nbt.2010.02.016](https://doi.org/10.1016/j.nbt.2010.02.016)

[Paper 2]({{ path_prediction }}/{{ page.pages.two_step_svm }}/)
: **A two step site and mRNA-level model for predicting microRNA targets**
: Takaya Saito and Pål Sætrom
: BMC bioinformatics 2010
: DOI: [10.1186/1471-2105-11-612](https://doi.org/10.1186/1471-2105-11-612)

[Paper 3]({{ path_experiment }}/{{ page.pages.confounding }}/)
: **Target gene expression levels and competition between transfected and endogenous microRNAs are strong confounding factors in microRNA high-throughput experiments**
: Takaya Saito and Pål Sætrom
: Silence 2012
: DOI: [10.1186/1758-907X-3-3](https://doi.org/10.1186/1758-907x-3-3)

Paper 4
: **MicroRNAs affect gene expression by targeting cis-transcribed non-coding RNAs**
: Takaya Saito, Even Skaland, and Pål Sætrom
: (Submitted)

Paper 5
: **Inferring causative variants in microRNA target sites**
: Laurent F. Thomas, Takaya Saito, and Pål Sætrom
: Nucleic Acids Research 2011
: DOI: [10.1093/nar/gkr414](https://dx.doi.org/10.1093%2Fnar%2Fgkr414)


## Glossary {#S:0.7}

3' UTR
: Three prime untranslated region; non-coding regions of mRNA on the 3' end

5' UTR
: Five prime untranslated region; non-coding regions of mRNA on the 5' end

A
: Adenine; a purine nucleobase paired with thymine in DNA and uracil in RNA

ACC
: Accuracy; (TP + TN) / (P + N) in a binary classification model

ADTree
: Alternating decision tree; a machine learning algorithm that combines more than one decision tree

Agile
: Agile software development; a type of RAD methodology

Ago
: Argonaut protein; a key component of the RISC complex

ANN
: Artificial neural network; a machine learning method that mimics biological neural networks

ANOVA
: Analysis of variance; a statistical method to infer differences among multiple groups

AU rich
: Adenine:Uracil rich; nucleotide sequences with many adenines and uracils

AUC
: Area under the ROC curve; a performance measure to evaluate the ROC curves

<i>C. elegans</i>
: <i>Caenorhabditis elegans</i> transparent roundworm about 1 mm in length

bp
: Base pair; a unit for nucleotide length with a base pair as a Watson and Crick pair

C
: Cytosine; a pyrimidine nucleobase paired with guanine

CAR
: Chromatin associated RNA; experimentally validated non-coding RNAs that amirna-target-predictionre associated with chromatin

cis-NAT
: Cis-natural antisense transcript; a pair of sense and anti-sense transcript that overlap each other in the same locus

CLIP
: Cross-linking and immunoprecipitation; a technique used to pull down RNA-protein complexes

CROC
: concentrated ROC; a version of ROC for evaluating early retrieval performance

Cy3
: Cyanine 3; a green fluorescent dye used in the microarray assay

Cy5
: Cyanine 5; a red fluorescent dye used in the microarray assay

cDNA
: Complementary DNA; DNA synthesized from mRNA by reverse transcriptase

CDS
: Coding sequence; coding region of mRNA

CNS
: Central nervous system; the central part of the nervous system in the brain

DGCR8
: DiGeorge syndrome critical region gene 8; a protein that recognizes a miRNA stem loop in pri-miRNA

DNA
: Deoxyribonucleic acid; a nucleic acid that contains genetic information

dsRNA
: Double-stranded RNA; RNA with two complementary strands

EBI
: European bioinformatics institute; a center for research and services in bioinformatics in Europe

ERR
: Error rate; (FP + FN) / (P + N)  in a binary classification model

FDR
: False discovery rate; FP / (FP + TN)

EST
: Expressed sequence tag; a short sub-sequence of a cDNA sequence

FLcDNA
: Full-length cDNA; full-length cDNA used by the Sanger sequencing method

FN
: False negative; prediction outcome is false while the actual value is true

FP
: False positive; prediction outcome is true while the actual value is false

G
: Guanine; a purine nucleobase paired with cytosine

Gb
: Giga base pair; 1,000,000,000 bp

GEO
: Gene expression omnibus; a public repository for microarray data

GFF
: General feature format; a text file format for genomic positional information

GPMDB
: Global Proteome Machine database; a public repository for proteomics data

G:U wobble
: Guanine:Uracil wobble; guanine and uracil wobble paring

GTP
: Guanosine triphosphate; a purine nucleotide that is used for energy transfer within the cell

HITS
: High throughput sequencing; the next generation sequencing

iTRAQ
: Isotope tags for relative and absolute quantification; a non-gel-based technique for quantifying proteins

INSDC
: International nucleotide sequence database collaboration; a group that organizes SRA repositories

K-S test
: Kolmogorov-Smirnov test; a non-parametric statistical method

<i>k</i>-NN
: <i>k</i>-nearest neighbor; a type of machine learning algorithm

LC-MS/MS
: Liquid chromatography-tandem mass spectrometry; MS/MS with liquid chromatography. Liquid chromatography separates ions or molecules dissolved in a solvent

ML
: Machine learning; a class of computational algorithms that can imitate learning

MAF
: Multiple alignment format; a text file format for multiple alignments

MIAME
: Minimum information about a microarray experiment; a standard for reporting microarray experiments

miRISCs
: miRNA RISC; RISC loaded with miRNA

miRNA
: Micro RNA; a class of small ncRNA that regulates protein expression

MS
: Mass-spectrometry; a technique that measures the mass-to-charge ratio of charged particles

MS/MS
: Tandem mass spectrometry; a technique that involves multiple steps of mass spectrometry

N
: Negative; actual negative values in a binary classification model

NB
: Naive Bayes; a type of statistical learning algorithm that uses Bayes' theorem

NCBI
: National center for biotechnology information; U.S. government-funded national resource for molecular biology information

NPV
: Negative predictive value; TN / (TN + FN) in a binary classification model

OOP
: Object-oriented programming; a computer programming paradigm

P
: Positive; actual positive values in a binary classification model

PCR
: Polymerase chain reaction; a technique used to amplify DNA sequences

piRNA
: Piwi-interacting RNA; siRNA/miRNA like ncRNAs found in germline cells

Pol II
: RNA polymerase II; an enzyme that synthesizes several types of RNAs

Pol III
: RNA polymerase III; an enzyme that synthesizes rRNA, tRNA and other small RNAs

PRIDE
: Proteomics identifications database; a public repository for proteomics data

RDB
: Relational database; a computational data storage method. Data are stored in tables with a collection of relations

RIP
: Ribonucleoprotein immunoprecipitation; a technique used to pull down RNA-protein complexes

ncRNA
: Non-protein-coding RNA; functional RNA that is not translated into protein

pri-miRNA
: primary miRNA; a RNA molecule that contains one or more miRNA stem loops

pre-miRNA
: precursor miRNA; miRNA precursor with a hairpin stem loop, that is exported into cytoplasm

PRC
: Precision; equivalent to PPV or Positive predictive value

PPV
: Positive predictive value; TP / (TP + FP) in a binary classification model

QP
: Quadratic programming; A class of optimization algorithms to maximize a quadratic function subject to linear constrains

RAD
: Rapid application development; a software development methodology

Ran
: Ras-related nuclear protein; a GTP binding protein that is involved in transport between nucleus and cytoplasm

RNA
: Ribonucleic acid; a nucleic acid that catalyzes with many biological molecules

RBF
: Radial basis function; a real-valued function whose value depends only on the distance from the origin

RNAi
: RNA interference; a regulatory process that suppresses gene expression at the post-transcriptional level with small RNAs

RNase
: Ribonuclease; an enzyme that degrades RNAs into smaller components

rRNA
: Ribosomal RNA; RNA components of the ribosome

RISC
: RNA-induced silencing complex; a key multiprotein complex in RNAi

RITS
: RNA-induced initiation of transcriptional gene-silencing; a complex involved in regulation of chromatin structure

RT-qPCR
: Reverse transcription quantitative PCR; a variant of PCR that can be used to measure RNA expression levels

ROC
: Receiver operating characteristics; a graph that shows true positive rate versus false positive rate

SAGE
: Serial Analysis of Gene Expression; a sequencing technique that uses short tags generated from $3^\prime$ ends of mRNA transcripts

siRISC
: siRNA RISC; RISC loaded with siRNA

siRNA
: Small interfering RNA; small ncRNAs involved in RNAi for gene silencing

SILAC
: Stable isotope labeling with amino acids in cell culture; a technique for in vivo incorporation of a label into proteins

SRA
: Sequence read archive; data repository for next generation sequencing data

SRM
: Structural Risk Minimization; a machine learning principle

SN
: Sensitivity; TP / P in a binary classification model

SP
: Specificity; TN / N in a binary classification model

SQL
: Structured query language; a language used with RDB

SNP
: Single-nucleotide polymorphism; DNA polymorphism with a single nucleotide difference between members of a species

ssRNA
: Single-stranded RNA; RNA with one strand

SVM
: Support vector machine; a machine learning algorithm that guarantees the maximum margin between decision boundaries

SVR
: Support vector regression; a version of SVM for regression

TNR
: True negative rate; equivalent to SP or Specificity

TPR
: True positive rate; equivalent to SN or Sensitivity

TDD
: Test-driven development; a type of RAD methodology

tRNA
: Transfer RNA; transfer a specific amino acid for protein synthesis

TN
: True negative; prediction outcome is false while the actual value is false

TP
: True positive; prediction outcome is true while the actual value is true

U
: Uracil; a pyrimidine nucleobase paired with adenine in RNA

UV
: Ultraviolet; electromagnetic radiation with shorter wavelength than visible light

VC dimension
: Vapnik Chervonenkis dimension; a measure of capacity for the data point separation by hyperplanes

WTSS
: Whole transcriptome shotgun sequencing; high throughput technique at the whole transcriptome level with next generation sequencing

XP
: Extreme programming; a type of RAD methodology
