---
layout: default
title: 4 Biological experiments
parent: Overview
nav_order: 5
description: "High-throughput biological experiments"
comments: true
group: thesis
folders:
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
figs:
  fig4_1: [two-color-microarray.webp, 484]
scholar:
  bibliography: thesis_4
---

{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture fig4_1 %}{{ fig_dir }}/{{ page.figs.fig4_1[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# 4 High-throughput biological experiments
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

Emerging high-throughput technologies have enabled genome-wide analyses
of various biological data, such as different cell lines, tissues, and
species, under different conditions. This chapter explains several
high-throughput technologies for transcriptomic and proteomic analyses
used in our research. We used both microarray and quantitative
proteomics data to achieve all three sub-goals, but we used next
generation sequence data only for the second and third sub-goals:
*[miRNA high-throughput experiments]({{ path_experiment }}/)*,
and *[miRNA and other ncRNAs]({{ path_ncrna }}/)*.

## 4.1 One microarray experiment can detect thousands of gene expressions simultaneously {#S:4.1}

Microarrays can capture the expression levels of many genes in a single
set of experiments. The microarray technology enables a high-throughput
transcriptome-wide analysis, which is hard to achieve with other
techniques for gene expression analyses, such as Northern blot
{% cite Alwine1977 -f {{ bib }} %} or reverse transcription quantitative polymerase chain
reaction (RT-qPCR) {% cite Becker-Andre1989 Noonan1990 -f {{ bib }} %}. The Northern blot
is a qualitative but low-throughput technique that requires the use of
electrophoresis and large amounts of the input RNA {% cite Morozova2009 -f {{ bib }} %}.
RT-qPCR can achieve higher throughput levels with less amount of the
input RNA than Northern blot, but the throughput remains on the order of
hundreds of known transcripts at a time
{% cite Morozova2009 VanGuilder2008 -f {{ bib }} %}.

Although several types of microarray technologies exist, the DNA
microarray is usually used for the transcriptome analysis. One
microarray chip usually consists of thousands of spots, and each spot
contains DNA oligonucleotides of a specific sequence
{% cite Quackenbush2006d -f {{ bib }} %}. These DNA oligonucleotides are suitable for
hybridization with DNA or RNA isolated from cells. Isolated RNAs are
chemically labeled before hybridization. These labels, such as
fluorescence dyes, are used to detect signal intensities of spots and
determine the relative mRNA abundance among samples. One of the major
DNA microarray applications is to measure the relative difference of
mRNA abundance between two samples. For example, Figure
[4.1](#F:4.1) shows the procedure of a two-color microarray system
{% cite Quackenbush2006d -f {{ bib }} %}. Another popular microarray design is one-color
microarray system, and data quality is essentially equivalent between
one- and two-color approaches {% cite Patterson2006 -f {{ bib }} %}.

### &nbsp; {#F:4.1}
{: .no_toc }
![Figure 4.1]({{ fig4_1 }}){:width="{{ page.figs.fig4_1[1] }}"}

#### **Figure 4.1**. Microarray procedure.
{: .no_toc .text-caption }
Two samples are compared by a two-color DNA
microarray. Sample RNA represents a sample of interest, whereas
Reference RNA represents a control sample for comparison. Sample RNA is
dyed red by Cy5, and Reference RNA is dyed green by Cy3. These two
samples are combined and hybridized with DNA oligonucleotides on the
chip. Color intensity is measured to estimate relative RNA expression
levels of the two samples.
{: .fs-2 }

---

After measuring the intensity levels, the raw data usually go through
normalization and transformation {% cite Quackenbush2002 -f {{ bib }} %}, and this whole
process is usually called the pre-processing of microarray data. The
pre-processing of the raw data is very important to reduce the noise in
each sample at the local level and among multiple samples at the global
level. In addition to detecting relative RNA expression levels, the DNA
microarray can be used for other applications, such as the detection of
single-nucleotide polymorphisms (SNPs), and alternative splicing events
{% cite Mockler2005 Morozova2009 -f {{ bib }} %}.

Two major drawbacks of microarray technologies are the limited ability
to detect novel transcripts and noisy data even after pre-processing
{% cite Morozova2009 -f {{ bib }} %}. Nonetheless, the microarray technology is still widely
used for many transcriptomics analyses because of the ability to measure
the expression of thousands of genes simultaneously at relatively low
cost.

## 4.2 The next generation sequencing methods are faster and more cost-effective than Sanger sequencing {#S:4.2}

As an alternative approach to the microarray technology, DNA sequencing
approaches are also widely used for transcriptome analysis. The
advantage of these sequencing methods is the ability to identify new
transcripts and measure the abundance of transcripts directly
{% cite Morozova2009 -f {{ bib }} %}. First generation sequencing methods relied on the
Sanger method {% cite Sanger1977 -f {{ bib }} %}. Since the original Sanger method uses the
full-length complementary DNA (FLcDNA), it involves a complex *in vivo*
cloning step that usually results in very high cost. Therefore, the
original Sanger method is normally limited only to novel transcript
discovery and annotation {% cite Morozova2009 -f {{ bib }} %}.

Two examples of Sanger method applications are expressed sequence tag
(EST) {% cite Adams1991 -f {{ bib }} %} and Serial Analysis of Gene Expression (SAGE)
{% cite Velculescu1995 -f {{ bib }} %}. Both approaches use shorter tags, which are short
sub-sequences of the cDNA sequence, rather than the FLcDNAs. ESTs are
short tags generated from either 3' or 5' end of a cDNA
clone. Even though the sequencing cost is reduced by ESTs compared with
FLcDNAs, it is still too expensive for the whole transcriptome analysis
{% cite Morozova2009 -f {{ bib }} %}. SAGE is a method that uses short tags generated from
3' ends of mRNA transcripts. SAGE is suitable for estimating
transcript abundance due to high redundancy of sequencing reads
{% cite Morozova2009 -f {{ bib }} %}. However, SAGE is still costly for the transcriptome
analysis because it still relies on labor intensive *in vivo* cloning
procedures {% cite Morozova2009 -f {{ bib }} %}.

The next generation, or the second generation, sequencing methods have
substantially improved upon the Sanger method. They produce millions of
short reads in a relatively short period of time {% cite Voelkerding2010 -f {{ bib }} %}
depending on several criteria, such as read length, sequence coverage,
and the size of the genome of interest (Table [4.1](#T:4.1)).
The reads are assembled computationally afterwards if necessary. The
major contribution to this enhancement is to parallelize the sequencing
process {% cite Hall2007 -f {{ bib }} %}, though other features, such as the usage of
PCR-based amplification instead of costly and labor intensive *in vivo*
cloning, also contribute {% cite Morozova2009 -f {{ bib }} %}. Three popular commercially
available next generation sequencing technologies are, Roche 454
([http://454.com](https://en.wikipedia.org/wiki/454_Life_Sciences)),
Illumina (<https://www.illumina.com>), and Applied
Biosystems SOLiD (<https://www.appliedbiosystems.com>) (Table [4.1](#T:4.1)).
The second generation sequencing can be used for all the applications
that are based on the Sanger method, including EST and SAGE. Some
applications that are based on the second generation sequencing are
explained in the next section.

<br />
### **Table 4.1**. Next generation sequencing technologies. {#T:4.1}
{: .no_toc .text-caption }
The table shows three examples of commercially available next generation sequencing
technologies with specifications obtained from their corresponding web
sites as of March 2011. "bp" and "Gb" represent base pairs and giga base
pairs respectively. The product type with the best specification is
selected for each technology. Both 2 × n and n × m
represent the read length of the pair end approach where n and m are
read lengths in base pairs.
{: .fs-2 }

|                         | **Roche 454**  | **Illumina** | **SOLiD**      |
|-------------------------|----------------|--------------|----------------|
| **Product type**        | GS FLX         | HiSeq 2000   | 5500xl         |
| **Read length**         | 400 bp         | 1 × 35 bp    | 75 bp          |
|                         |                | 2 × 50 bp    | 75 bp × 35 bp  |
|                         |                | 2 × 100 bp   | 60 bp × 60 bp  |
| **Throughput per day**  | 1 Gb           | 25 Gb        | 20-30 Gb       |

---

Third generation sequencing techniques will be available in the near
future. The main feature of the third generation is the ability to
sequence the whole single molecule instead of breaking down the molecule
into short reads, therefore the read lengths should be much longer than
those of the second generation sequencing technologies. Several strong
candidates that may lead the third generation sequencing are Pacific
Bioscience SMRT Sequencing (<https://www.pacificbiosciences.com>), Oxford
Nanopore technologies (<https://www.nanoporetech.com/>), and Life
technologies Single Molecule Sequencing
(<https://www.lifetechnologies.com>).

## 4.3 The second generation sequencing technologies can cover a wide range of applications {#S:4.3}

The second generation sequencing can be used in many different
applications because of its high-throughput and cost effectiveness. For
example, the applications can be transcript rearrangement discovery,
single-nucleotide variation profiling, and non-coding RNA discovery
{% cite Morozova2009 -f {{ bib }} %}. Two such applications, RNA-Seq and CLIP (Cross-Linking
and ImmunoPrecipitation)-Seq, are very powerful and useful for
transcriptomic analyses.

RNA-Seq or the whole transcriptome shotgun sequencing (WTSS) is a
technique that uses the second generation sequencing technology to
produce sequence reads at the whole transcriptome level
{% cite Morin2008 Nagalakshmi2008 -f {{ bib }} %}. Since the second generation sequencing
technology can yield sufficient sequencing depth, which represents the
total number of sequence reads generated from a sequencing library
{% cite Morozova2009 -f {{ bib }} %}, RNA-Seq can be used for gene expression profiling with
high accuracy.

CLIP-Seq {% cite Sanford2009 -f {{ bib }} %}, also called HITS-CLIP (High throughput
sequencing CLIP) {% cite Licatalosi2008 -f {{ bib }} %}, is a technique that employs three
important steps, cross-linking, immunoprecipitation, and next generation
sequencing. It can be used to tag and pull-down RNA-interacting proteins
of interest and infer the interactions between RNAs and RNA-binding
proteins. Firstly, RNA binding proteins and their target RNA regions are
cross-linked by ultraviolet (UV) light, and the antibodies for the
proteins are used for immunoprecipitation {% cite Jensen2008 -f {{ bib }} %}. Subsequently,
the RNA transcripts pulled down with the proteins go through the second
generation sequencing procedure {% cite Sanford2009 -f {{ bib }} %}. RIP (Ribonucleoprotein
ImmunoPrecipitation)-Seq is similar to CLIP-Seq {% cite Wong2009b -f {{ bib }} %}, but it
uses chemical cross-linkers such as formaldehyde instead of UV
cross-linking {% cite Niranjanakumari2002 Conrad2008 -f {{ bib }} %}. This cross-linking is
reversible, and it is subject to potential reassociation between RNAs
and RNA-binding proteins after cell lysis in some cases {% cite Mili2004 -f {{ bib }} %}.

## 4.4 Liquid chromatography-tandem mass spectrometry is a powerful tool to analyze quantitative proteomics {#S:4.4}

In recent years, several new technologies for the identification and
quantification of proteins have emerged. Most of them are based on
mass-spectrometry (MS), which is a technique that ionizes molecules and
measures the mass-to-charge ratio by detecting them in an
electromagnetic field {% cite Boggess2001 -f {{ bib }} %}. Although there are many variants
of MS-based technologies {% cite Mallick2010 -f {{ bib }} %}, the Liquid
chromatography-tandem mass spectrometry (LC-MS/MS) with stable isotope
labeling with amino acids in cell culture (SILAC) {% cite Ong2002 -f {{ bib }} %} approach is
widely used in detecting protein expression profiles.

LC-MS/MS uses high-performance liquid chromatography that can separate a
mixture of molecules with very small particles and a high pressure
before the MS/MS phase. MS/MS, or tandem mass spectrometry, involves two
steps of MS selections. The first MS can be used for the quantification
of peptides, and the second MS can be used for the identification of the
peptides {% cite Mallick2010 -f {{ bib }} %}.

LC-MS/MS is usually combined with either labeling or labeling-free
methods for a quantification approach. For example, SILAC tends to be
used for small changes (10%-50%), and isotope tags for relative and
absolute quantification (iTRAQ), which is another labeling method, tends
to be used for moderate changes (50%-200%) {% cite Mallick2010 -f {{ bib }} %}. Moreover, a
labeling-free method using spectrum counts can be used for large
changes (>100%) {% cite Mallick2010 -f {{ bib }} %}. Among them, SILAC is a simple
but very powerful method for quantitative proteomics {% cite Ong2005 -f {{ bib }} %}. The
SILAC procedure uses two different stable amino acid isotopes, as
"light" and "heavy" labels. The relative abundance of proteins can be
detected by comparing the intensities of isotope clusters
{% cite Mallick2010 Ong2005 -f {{ bib }} %}.

The coverage of protein identification in the genome is usually less
than 10% for higher organisms {% cite Bantscheff2007a -f {{ bib }} %} due to enormous
molecular complexity and the dynamic nature of proteins, such as
post-translational modifications and protein stability {% cite Mallick2010 -f {{ bib }} %}.
However, the protein coverage of quantification is even lower than the
protein identification. One possible explanation for this low coverage
is that protein quantification requires much higher data quality, in
terms of information content, than protein identification
{% cite Bantscheff2007a -f {{ bib }} %}.

## 4.5 Most preprocessed and raw data sets from high-throughput experiments are publicly available {#S:4.5}

Two major repositories for microarray experiment data are ArrayExpress
(<https://www.ebi.ac.uk/arrayexpress>) {% cite Parkinson2011 -f {{ bib }} %} at European
Bioinformatics Institute (EBI), and Gene Expression Omnibus (GEO)
(<https://www.ncbi.nlm.nih.gov/geo>) {% cite Barrett2006 -f {{ bib }} %} at National Center
for Biotechnology Information (NCBI). Both repositories encourage
submitters to supply Minimum Information About a Microarray Experiment
(MIAME) {% cite Brazma2001 -f {{ bib }} %} compliant data. MIAME is a standard for the
microarray data formats.
caption
The major repository for the next generation sequencing data is the
Sequence Read Archive (SRA), which is operated by the International
Nucleotide Sequence Database Collaboration (INSDC) {% cite Leinonen2011 -f {{ bib }} %}.
However, due to a rapid growth of next generation sequencing data and
budget constrains, NCBI, which is the main member of INSDS, currently
accepts limited types and forms of the next generation sequencing data.

There are no central repositories for quantitative proteomics data, but
many small and medium scale public repositories are available instead.
Some of the examples of such repositories {% cite Mead2009 -f {{ bib }} %} are Proteomics
IDEntifications database (PRIDE) {% cite Jones2006 -f {{ bib }} %}, the Global Proteome
Machine database (GPMDB) {% cite Craig2004 -f {{ bib }} %}, and PeptideAtlas {% cite Deutsch2010 -f {{ bib }} %}.

## References {#S:4.6}
{% bibliography --cited_in_order -f {{ bib }} %}
