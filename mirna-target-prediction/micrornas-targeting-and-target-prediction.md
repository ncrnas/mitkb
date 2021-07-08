---
layout: default
title: "Review: miRNA target"
parent: Target prediction
description: "MicroRNAs: targeting and target prediction"
nav_order: 1
group: review
tabs:
  tab1: table1
  tab1_attr: {use_refs: true, refs: Refs, tx_align: true}
  tab1_refs: Refs
  tab2_head: table2_header
  tab2_body: table2_body
  tab2_body_attr: {url_col: url, valid_col: valid}
figs:
  fig1: [microrna-target-features.webp, 500]
scholar:
  bibliography: review
---

{% assign tab_arr = site.data[page.group] %}
{% assign tab1 = tab_arr[page.tabs.tab1] %}
{% assign tab2_head = tab_arr[page.tabs.tab2_head] %}
{% assign tab2_body = tab_arr[page.tabs.tab2_body] %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture fig1 %}{{ fig_dir }}/{{ page.figs.fig1[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# MicroRNAs - targeting and target prediction
{: .no_toc .text-center }

Takay Saito<sup>a</sup> and Pål Sætrom<sup>a,b</sup>
{: .text-center }

<strong><sup>a</sup></strong>Department of Cancer Research and Molecular Medicine,  \
Norwegian University of Science and Technology, NO-7489 Trondheim, Norway \
<strong><sup>b</sup></strong>Department of Computer and Information Science, \
Norwegian University of Science and Technology, NO-7491 Trondheim, Norway
{: .fs-3 .text-center .text-grey-dk-000 }

<br />
[View PDF](https://arxiv.org/pdf/1507.01804.pdf){: .btn }
<div class="code-example">
<strong>Note:</strong> The web version of the article was created
based on the preprint version uploaded to
<a href="https://arxiv.org/abs/1507.01804">arXiv</a>. <br />
Preprint submitted to New Biotechnology: November 2009, <br />
Published: July 2010,
DOI: <a href="https://doi.org/10.1016/j.nbt.2010.02.016">https://doi.org/10.1016/j.nbt.2010.02.016</a>.
</div>
{: .bg-grey-lt-000 .p-3 }

<div class="code-example">
<strong>Citation:</strong> <br />
Saito, T and Sætrom, P. (2010). MicroRNAs–targeting and target prediction.
New biotechnology 27 (3), 243-249.
<a href="https://doi.org/10.1016/j.nbt.2010.02.016">https://doi.org/10.1016/j.nbt.2010.02.016</a>.
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
MicroRNAs (miRNAs) are a class of small noncoding RNAs that can
regulate many genes by base pairing to sites in mRNAs. The
functionality of miRNAs overlaps that of short interfering RNAs
(siRNAs), and many features of miRNA targeting have been revealed
experimentally by studying miRNA-mimicking siRNAs. This review
outlines the features associated with animal miRNA targeting and
describes currently available prediction tools.

## Introduction {#S:2}
MicroRNAs (miRNAs) were identified as a large sub-class of ncRNAs in 2001.
Since then, an increasing number of studies have firmly
established miRNAs' importance in gene regulation in general and animal
development and disease in particular
{% cite Ambros2004 Soifer2007 Croce2009 Stefani2008 Bartel2004 -f {{ bib }} %}.
miRNAs regulate protein-coding genes post-transcriptionally by guiding a
protein complex known as the RNA-induced silencing complex (RISC) to
messenger RNAs (mRNAs) with partial complementarity to the miRNA
{% cite Carthew2009 -f {{ bib }} %}. Through mechanisms not completely understood, RISC then
inhibits protein translation and causes mRNA degradation
{% cite Bartel2009 Filipowicz2008 -f {{ bib }} %}. Current estimates indicate that miRNAs
regulate at least 60% of the human protein-coding genes through this
post-transcriptional gene silencing (PTGS) {% cite Friedman2009 -f {{ bib }} %}.

Incorporated into RISC, miRNAs are functionally equivalent to short
interfering RNAs (siRNAs) {% cite Hamilton1999 Zamore2000 -f {{ bib }} %}. The main
difference between these RNAs is that miRNAs are processed from
imperfect hairpin structures, whereas siRNAs are processed from long
double-stranded RNAs {% cite Kim2009 Winter2009 -f {{ bib }} %}. Moreover, animal miRNAs
typically target imperfect sites, whereas siRNAs target sites with
near-perfect complementarity. SiRNAs do target imperfect sites as well,
however, and this miRNA-like targeting is the major source of siRNA
off-target effects {% cite Birmingham2006 Jackson2006 Jackson2003 -f {{ bib }} %}.

The list of known miRNAs is large and increasing. Currently, the
official miRNA database miRBase lists 721 human miRNAs
(<http://www.mirbase.org>; Release 14) {% cite Griffiths-Jones2008 -f {{ bib }} %}, but
estimates indicate that the human genome contains more than 1000 miRNAs.
As only a few regulatory targets are known, predicting and validating
miRNA targets is one of the major hurdles in understanding miRNA
biology. Here, we review the [features important for miRNA targeting](#S:3) and
the [bioinformatics tools](#S:4) available for predicting miRNA targets.

## miRNA target features {#S:3}
Identifying miRNA targets in animals has been very challenging. This is
mainly because the limited complementarity between miRNAs and their
targets, which might lead to the finding of hundreds of potential miRNA
targets per miRNA. Therefore, many studies have been conducted, both
experimentally and computationally, to reveal more efficient approaches
for miRNA target recognition. We have divided the miRNA target features
reported in these studies into six categories, [miRNA:mRNA pairing](#S:3a),
[site location](#S:3b), [conservation](#S:3c), [site accessibility](#S:3d),
[multiple sites](#S:3e) and [expression profile](#S:3f).

### miRNA:mRNA pairing: ‘Seed site’ is the most important feature for target recognition {#S:3a}
miRNA targets commonly have at least one region that has Watson-Crick
pairing to the 5' part of miRNA. This 5' part, located at positions
2-7 from the 5' end of miRNA, is known as the ‘seed’, as RISC uses
these positions as a nucleation signal for recognizing target mRNAs
{% cite Stark2003 Rajewsky2004 Lewis2003 -f {{ bib }} %}. The corresponding sites in mRNA
are referred to as ‘seed sites’. A stringent-seed site has perfect
Watson-Crick pairing and can be divided into four ‘seed’ types -- 8mer,
7mer-m8, 7mer-A1 and 6mer -- depending on the combination of the
nucleotide of position 1 and pairing at position 8 (Fig. [1](#F:1)a). 8mer has
both an adenine at position 1 of the target site and base pairing at
position 8. 7mer-A1 has an adenine at position 1, while 7mer-m8 has base
pairing at position 8. 6mer has neither an adenine at position 1 nor
base pairing at position 8 {% cite Grimson2007 -f {{ bib }} %}. An adenine on the target site
corresponding to position 1 of miRNA is known to increase efficiency of
target recognition {% cite Lewis2005 -f {{ bib }} %}.

#### &nbsp; {#F:1}
{: .no_toc }
![Figure 1]({{ fig1 }}){:width="{{ page.figs.fig1[1] }}"}

##### **Figure 1**. Types of miRNA target sites and multiple sites.
{: .no_toc .text-caption }
**(a)** Stringent-seed site. 7mer-A1 is shown as an example.
Vertical lines indicate Watson-Crick paring. \
**(b)** Moderate-stringent-seed site. BM is shown as an example. \
**(c)** 3'-supplementary site. More than 3-4 nucleotide paring required. \
**(d)** Optimal distance of two miRNA target sites.
{: .fs-2 }

---

In addition to this stringent-seed matching, moderate-stringent-seed
matching is also functional because RISC can tolerate small mismatches
or G:U wobble pairing within the seed region (Fig. [1](#F:1)b). This
moderate-stringent-seed matching has five ‘seed’ types: GUM, GUT, BM, BT
and LP, defined regarding to the mismatch type. GUM has one G:U wobble
and the uracil on the seed site of miRNA, whereas GUT has the uracil on
the target site of mRNA. BM has one bulge and the mismatch is on the
seed site, whereas BT has the mismatch on the target site. LP has only
one loop {% cite Gaidatzis2007 -f {{ bib }} %}. Furthermore, RISC can recognize offset sites
that are located at positions 3-10. Offset sites can be either stringent
or moderate-stringent-seed matching {% cite Hammell2008 -f {{ bib }} %}.

Watson-Crick pairing in the 3' part of miRNA is known to enhance the
site recognition efficacy in miRNA targets that have seed pairing
{% cite Grimson2007 -f {{ bib }} %}. The preferable nucleotide number of matches in the 3'
part differs between the site that has stringent-seed pairing and the
one that has moderate-stringent-seed pairing. Stringent-seeds require
3-4 matches in the positions 13-16, whereas moderate-stringent-seeds
require 4-5 matches in the positions 13-19. Sites with this additional
3' pairing are called 3'-supplementary (Fig. [1](#F:1)c) and
3'-compensatory sites {% cite Bartel2009 -f {{ bib }} %}.

It is difficult to measure the efficacy level of each seed type
precisely, but several microarray and conservation enrichment studies
have revealed hierarchies of relative efficacies. These hierarchies can
be described as ‘Stringent seed’ > ‘Stringent seed in offset’ >
‘Moderate-stringent seed’ > ‘Moderate-stringent in offset’; 8mer >
7mer-m8 > 7mer-A1 > 6mer in the stringent-seed types; and Bulge >
G:U wobble > Loop in the moderate-stringent-seed types
{% cite Bartel2009 Hammell2008 -f {{ bib }} %}. Moreover, multiple sites are more efficient
than single sites {% cite Saetrom2007 -f {{ bib }} %}.

The advantages and disadvantages of using different set of seed types
are that considering only stringent-seed types increases specificity but
might miss many potential targets, whereas considering both stringent
and moderate-stringent-seed types increase sensitivity but might also
increase the number of false positives.

### Site location: most target sites reside within 3' untranslated region (UTR) of target genes {#S:3b}
Several studies have reported that most target sites can be found in the
3' UTR segment of the target genes, even though miRNA-loaded RISC in
theory can bind any segment of mRNA. Target genes tend to have longer
3' UTR, whereas ubiquitously expressed genes, such as house-keeping
genes, have shorter 3' UTR -- potentially to avoid being regulated by
miRNAs {% cite Stark2005 -f {{ bib }} %}. Target sites are not evenly distributed within 3'
UTR, but are located near both ends when the length of 3' UTR is
≥2000 nucleotides. For shorter 3' UTRs, sites
tend to be near the stop codon {% cite Gaidatzis2007 -f {{ bib }} %}. Sites are not located
too close to the stop codon, however, but 15-20 nucleotides away from
the stop codon {% cite Grimson2007 -f {{ bib }} %}. In addition, some genes have alternative
splicing in their 3' UTR segments, especially genes with long 3'
UTRs. These genes might therefore have different potential target sites
for alternatively spliced 3' UTRs {% cite Majoros2007 -f {{ bib }} %}. Finally, alternative
polyadenylation sites can shorten 3' UTRs and affect miRNA regulation
{% cite Sandberg2008 -f {{ bib }} %}.

Although functional miRNA sites are preferentially located in 3' UTR,
seed sites in the coding sequence (CDS) and 5' UTR regions can also
give downregulation {% cite Lytle2007 Kloosterman2004 -f {{ bib }} %}. Why does RISC then
appear to prefer the 3' UTR? The most probable explanation is that
RISC competes with other protein complexes, such as ribosomes in CDS and
translation initiation complexes in 5' UTR; see discussion in the
following section
‘[Multiple sites: cooperativity enhances site efficacy](#S:3e)’.
The 3' UTR might simply be more accessible for long-term
binding than the two other mRNA regions {% cite Bartel2004 -f {{ bib }} %}.

Despite this general trend for 3' UTR targeting, there are some
notable exceptions. One recent study reported that many miRNAs
preferentially target 5' UTR sites with high complementarity to the
miRNAs' 3' end in a species-specific manner {% cite Lee2009 -f {{ bib }} %}. The targets
also showed signs of weaker interactions between the miRNA seed sequence
and the 3' UTR. The authors proposed that these sites represented a
new miRNA target class called ‘miBridge’, in which one miRNA
simultaneously interacts with a seed pairing site in 3' UTR and a 3'
pairing site in 5' UTR. The molecular mechanisms behind and the
biological extent of these miBridge targets are still unknown, however.

Most miRNA target prediction studies only focus on the 3' UTR, which
results in that all the available data are biased toward 3' UTR.
Moreover, few studies consider alternative splicing or polyadenylation
because of shortcomings in current annotations. As transcript usage
often depends on cellular context -- for example, whether the cell is
proliferating or terminally differentiated -- future tools for miRNA
target analyses should probably use available information about cellular
state to increase prediction performance.

### Conservation: miRNAs and their targets are conserved among related species {#S:3c}
miRNA families are comprised of miRNAs that have the same seed site, and
are well conserved among related species. In addition, miRNA families
have targets that are conserved among related species {% cite Friedman2009 -f {{ bib }} %}.
There are also species-specific miRNAs and targets, and one study showed
that about 30% of the experimentally validated target genes might not be
well conserved {% cite Sethupathy2006 -f {{ bib }} %}.

siRNA off-target effects occur no matter whether the site is conserved
or not {% cite Burchard2009 -f {{ bib }} %}, therefore searching for all potential target
sequences without considering evolutionally conservational might
increase siRNA off-target detection efficacy.

Applying a filter that requires predicted target sites to be conserved
can decrease the false-positive rate, but such a filter is effective
only for conserved miRNAs. It is important to identify targets both with
and without conservation -- especially when species-specific miRNAs or
siRNA off-targets is of interest.

### Site accessibility: mRNA secondary structure affects site accessibility {#S:3d}
The mRNA secondary structure is very important for miRNA targeting. An
effective miRNA:mRNA interaction needs an open structure on the target
site to begin the hybridization reaction. After binding, RISC can
disrupt the secondary structure on the site to elongate hybridization
{% cite Long2007 Kertesz2007 -f {{ bib }} %}. Minimum free energy is usually used to
estimate the secondary structure and RNA hybridization, but the amount
of A:Us surrounding the site can also be used to estimate the site
accessibility. Effective target sites often have A:U rich context in
approximately 30 nucleotides upstream and downstream from the seed
matching region of the target site {% cite Grimson2007 -f {{ bib }} %}.

Calculating the minimum free energy of accessibility and hybridization
with the mRNA secondary structure requires analyzing different mRNA
folding patterns. This requires enormous amounts of computing power, as
finding the most stable RNA structure is a computational problem that
scales with the cube of the length of the RNA sequence {% cite Eddy2004 -f {{ bib }} %}.
Hence, finding hybridization sites in long 3' UTRs tends to be time
consuming. Moreover, the current thermodynamic models used in RNA
secondary structure prediction algorithms are only 90-95% accurate,
which results in that the algorithms tend to have only 50-70% of the
base pairs correct {% cite Eddy2004 -f {{ bib }} %}. Thus, despite being theoretically sound,
calculating site accessibility has limited practical value when
predicting miRNA target sites; heuristics that are easy to compute, such
as local A:U context, have similar performance.

### Multiple sites: cooperativity enhances site efficacy {#S:3e}
Strong miRNA targets tend to have multiple target sites instead of one
single site {% cite John2004 -f {{ bib }} %}. Considering the number of putative miRNA sites
per mRNA can therefore significantly enhance target prediction.

Although the general effect of multiple sites appears to be additive,
miRNA targeting can also be synergistic. Our previous study showed that
two target sites within optimal distance enhance target site efficacy.
The preferable optimal length is between 17 and 35 nucleotides, but the
length between 14 and 46 nucleotides also enhances the efficacy (Fig. [1](#F:1)d).
This co-operability is functional between the same miRNAs as well as two
different miRNAs {% cite Saetrom2007 -f {{ bib }} %}. Multiple sites involving more than two
sites can also contribute to the enhancement {% cite Doench2004 -f {{ bib }} %}.

The exact mechanism underlying the synergism remains unknown. As
translational suppression is a relatively slow process compared with
RISC's catalytic cleavage {% cite Haley2004 -f {{ bib }} %}, however, multiple RISC complexes
bound at closely spaced target sites might cooperatively stabilize each
other at the sites or possibly accelerate the regulatory process. This
could explain why miRNAs prefer targets in 3' UTRs, as ribosomes would
displace RISC from sites in CDS before RISC could effect translational
suppression. Indeed, a cluster of rare codons that stall the ribosome
can, when placed in front of a nonfunctional miRNA site in CDS, change
the site to a functional site {% cite Gu2009 -f {{ bib }} %}. Moreover, the genes that
currently have verified miRNA target sites in CDS tend to have either
one very strong target site {% cite Duursma2008 Elcheva2009 -f {{ bib }} %} or multiple,
closely spaced sites {% cite Tay2008 Forman2008 -f {{ bib }} %}.

### Expression profile: miRNA:mRNA pairs are negatively correlated in expression profiles {#S:3f}
One miRNA can potentially regulate many genes; therefore, expression
profiles of mRNAs might vary substantially depending on the miRNA
expression levels. Many miRNAs are also expressed differently in
different tissues. Consequently, if negatively correlated expression
levels of a miRNA:mRNA pair are detected across different tissue
profiles, the mRNA of the pair is probably targeted by the miRNA
{% cite Rajewsky2006 Lim2005 -f {{ bib }} %}. Filtering putative targets based on
expression profile correlations is an effective approach to reduce the
false-positive rate. Although the majority of miRNA targets appear to be
regulated both at the mRNA and protein level, some targets only show an
effect at the protein level, however {% cite Selbach2008 Baek2008 -f {{ bib }} %}.
Researchers should therefore be aware that such filtering will exclude
potential targets.

## Target prediction tools {#S:4}
Many target prediction tools have been developed (Table [1](#T:1)),
but the types of methods applied, the miRNA
and mRNA sequences used and the output prediction data and performance
evaluation vary widely between tools. Direct comparison of prediction
performance among tools is not straight forward because the set of
predicted target genes from different tools do not overlap well. What is
clear, however, is that conventional tools with simple stringent-seed
search are prone to high false-positive rates. Therefore, most tools are
designed to reduce the false-positive rate and maximize the accuracy at
the same time. We have compared the currently available tools based on
the target features the tools use in their predictions (Table [1](#T:1)),
and the tools' availability (Table [2](#T:2)).
Availability is especially important for
researchers that are using their own miRNA or mRNA annotations, or are
working in a nonstandard species. In these cases, only tools that can be
downloaded or allows the user to input own miRNAs and mRNAs can be used.

<br />

#### **Table 1**. List of miRNA target prediction tools. {#T:1}
{: .no_toc .text-caption }

{% include tbl_simple.html data=tab1 attr=page.tabs.tab1_attr %}

<sup><strong>a</strong></sup>miRNA:mRNA pairing. ●: stringent seeds, ○:
moderately stringent seeds, Blank: seed sites not considered.\
<sup><strong>b</strong></sup>Site location. ●: target positions considered,
Blank: target positions not considered.\
<sup><strong>c</strong></sup>Conservation. ●: with/without conservation filter,
○: with conservation filter, Blank: conservation not considered.\
<sup><strong>d</strong></sup>Site accessibility. ●: site accessibility with
minimum free energy considered, ○: A:U rich flanking considered,
Blank: site accessibility not considered.\
<sup><strong>e</strong></sup>Multiple sites. ●: multiple sites considered,
○: the number of putative sites consided, Blank: multiple
co-operability not considered.\
<sup><strong>f</strong></sup>Expression profile. ●: expression profiles used,
Blank: expression profiles not used.
{: .fs-2 }

---

#### **Table 2**. Resource availability for miRNA target prediction tools. {#T:2}
{: .no_toc .text-caption }

<table>
{% include tbl_header.html data=tab2_head %}
{% include tbl_body_url.html data=tab2_body attr=page.tabs.tab2_body_attr %}
</table>

<sup><strong>a</strong></sup>Both species of pre-computed prediction and the species
available on the web tool are listed. Letters indicate the species: fly
(f), worm (w), human (h), mouse (m), rat (r), chicken (c), zebra fish
(z), and dog (d). Cells are left empty when no information is
available.\
<sup><strong>b</strong></sup>Yes/No indicate whether own miRNA sequences can be used on
the web interface or not.\
<sup><strong>c</strong></sup>Yes/No indicate whether own mRNA sequences can be used on
the web interface or not.\
<sup><strong>d</strong></sup>SW: Software availability (executable or source code).
{: .fs-2 }

---

Most tools rely on either one or a combination of seed matching, site
accessibility and evolutionary conservation features, although some
recently developed tools use expression profiles. No tools have
successfully incorporated some of the important features, such as
optimal distances of multiple miRNA sites or supplementary sites in CDS
and 5' UTR.

TargetScan {% cite Friedman2009 Grimson2007 Lewis2005 -f {{ bib }} %}, PicTar
{% cite Chen2006 Grun2005 Krek2005 Lall2006 -f {{ bib }} %} , miRanda
{% cite John2004 Betel2008 -f {{ bib }} %}, RNAhybrid {% cite Kruger2006 Rehmsmeier2004 -f {{ bib }} %} and
PITA {% cite Kertesz2007 -f {{ bib }} %} have been frequently used for performance
comparisons or as preprocessors for other tools to obtain initial
putative target sites. Of the five, TargetScan often shows the best
performance in comparisons. TargetScan considers only stringent seeds,
however, and therefore ignores many potential targets.

## Summary {#S:5}
Finding true functional miRNA targets is still challenging even though
many biological features of miRNA targeting have been revealed
experimentally and computationally. Building a model with more features
might achieve higher accuracy and enhance site recognition efficacy, but
its implementation might also become more complex. None of the existing
prediction tools has been able to incorporate all currently known
features. We expect that a new approach that can combine the features
from the six categories we have shown will significantly improve
computational miRNA target prediction.

Another important problem that has hardly been addressed is predicting
target interactions between different miRNAs. Different miRNAs can
cooperatively regulate individual targets, but miRNA expression
signatures differ between cell types and cellular conditions.
Determining how varying miRNA expression affects target regulation in
cancerous versus normal cells, for example, will therefore be a major
problem in the coming years.

## References {#S:6}
{% bibliography --cited_in_order -f {{ bib }} %}
