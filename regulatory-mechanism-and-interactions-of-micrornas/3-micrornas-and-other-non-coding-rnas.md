---
layout: default
title: 3 miRNAs and ncRNAs
parent: Overview
nav_order: 4
description: "MicroRNAs and other non-coding RNAs"
group: thesis
folders:
  ncrna: mirna-and-other-ncrnas
figs:
  fig3_1: [microrna-biogenesis.webp, 546]
  fig3_2: [types-of-microrna-targeting.webp, 473]
  fig3_3: [types-of-microrna-seed-sequences.webp, 400]
  fig3_4: [complex-loci.webp, 297]
  fig3_5: [microrna-regulation-on-cis-nat.webp, 438]
  fig3_6: [chromatin-associated-rna.webp, 301]
scholar:
  bibliography: thesis_3
---

{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

{% capture fig_dir %}{{ site.baseurl }}/assets/images/{{ page.group }}{% endcapture %}
{% capture fig3_1 %}{{ fig_dir }}/{{ page.figs.fig3_1[0] }}{% endcapture %}
{% capture fig3_2 %}{{ fig_dir }}/{{ page.figs.fig3_2[0] }}{% endcapture %}
{% capture fig3_3 %}{{ fig_dir }}/{{ page.figs.fig3_3[0] }}{% endcapture %}
{% capture fig3_4 %}{{ fig_dir }}/{{ page.figs.fig3_4[0] }}{% endcapture %}
{% capture fig3_5 %}{{ fig_dir }}/{{ page.figs.fig3_5[0] }}{% endcapture %}
{% capture fig3_6 %}{{ fig_dir }}/{{ page.figs.fig3_6[0] }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# 3 MicroRNAs and other non-coding RNAs
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

Since our main goal is to reveal the miRNA regulation and
characteristics, this chapter introduces several different aspects of
miRNAs, such as the history of miRNA discovery, miRNA biogenesis, and
mechanism of miRNA regulation. In addition to miRNAs, it also describes
several other classes of ncRNAs and their potential interactions with
miRNAs. Specifically, analysis on such ncRNAs is the main objective of
the third sub-goal: *[miRNA and other ncRNAs]({{ path_ncrna }}/)*.

## 3.1 Thousands of miRNAs have been identified since the first miRNA discovery of *lin-4* in 1993 {#T:3.1}

In 1993, Lee et al. found that *lin-4*, a gene involved in development
timing in *C. elegans*, produces a small ncRNA instead of a messenger
RNA (mRNA) {% cite Lee1993 -f {{ bib }} %}. *lin-4* was known to regulate *lin-14*, but the
protein product of *lin-4* had been undetected. The result of an
alignment analysis indicated that *lin-4* has multiple complementary
sites on the 3' UTR of *lin-14* {% cite Lee1993 -f {{ bib }} %}. Further experiment
revealed that this small ncRNA produced by *lin-4* can directly suppress
the expression of *lin-14* by base-paring on the 3' UTR. This
was the first discovery of this functional ncRNA with about 22
nucleotides that regulates specific protein expression by base-paring on
the 3' UTR of its target mRNA {% cite Bartel2004 -f {{ bib }} %}. However, there were
no other *lin-4*-like small ncRNAs identified, and this peculiar
regulation of *lin-4* was recognized as a rare case {% cite Bartel2004 -f {{ bib }} %}.

Meanwhile, Fire et al. reported that they observed a gene silencing
effect after injecting double-stranded RNAs (dsRNAs) into *C. elegans*
{% cite Fire1998 -f {{ bib }} %} in 1998. They coined the term, RNA interference (RNAi), to
describe this gene-silencing mechanism. Soon thereafter, RNAi was found
to silence genes at the post-transcriptional level with small RNA
molecules with 20-25 nucleotides, called small interfering RNAs (siRNAs)
{% cite Hamilton1999 Elbashir2001 Mello2004 -f {{ bib }} %}.

Then, nearly seven years after the discovery of *lin-4*, Reinhart et al.
identified a *lin-4*-like small ncRNA, *let-7*, in *C. elegans* in 2000
{% cite Reinhart2000 -f {{ bib }} %}. They revealed that *let-7* is also an ncRNA with about
22 nucleotides that regulates specific protein expression by base-paring
on the 3' UTR. Since *let-7* has homologs in various species,
this discovery led to identification of many other *let-7*- and
*lin-4*-like small ncRNAs in other animals, including human and
*Drosophila* {% cite Pasquinelli2000 -f {{ bib }} %}. The term microRNA (miRNA) was coined to
refer to these small ncRNAs of about 22 nucleotide length
{% cite Lagos-Quintana2001 Lau2001 Lee2001 -f {{ bib }} %}. Moreover, like siRNAs, miRNAs
appeared to use the RNAi pathway to regulated genes at the
post-transcriptional level {% cite Bartel2004 -f {{ bib }} %}.

Today, miRNAs are recognized as a very common class of ncRNAs that can
regulate protein expression
{% cite Lagos-Quintana2001 Lau2001 Lee2001 Bartel2004 -f {{ bib }} %}. For instance,
miRBase
{% cite Griffiths-Jones2004 Griffiths-Jones2006 Griffiths-Jones2008 Kozomara2011 -f {{ bib }} %},
which is the main database for miRNA annotations, contains 15172 entries
in 142 species as of release 16, 2010. They are abundant and found
mostly in eukaryotes as well as in some viruses. MicroRNAs are known to
play many important regulatory roles in eukaryotes {% cite Bartel2004 -f {{ bib }} %},
whereas some viruses encode viral miRNA genes that potentially regulate
fundamental cellular processes both in the viruses and in their host
cells {% cite Nair2006 Boss2009 -f {{ bib }} %}.

## 3.2 MicroRNA biogenesis involves multiple steps {#T:3.2}

Although the precise mechanism of miRNA biogenesis is unknown, Figure
[3.1](#F:3.1) shows the most widely accepted view of the miRNA biogenesis to date. The
biogenesis involves multiple processes both in the nucleus and the
cytoplasm.

### &nbsp; {#F:3.1}
{: .no_toc }
![Figure 3.1]({{ fig3_1 }}){:width="{{ page.figs.fig3_1[1] }}"}

#### **Figure 3.1**. MicroRNA biogenesis.
{: .no_toc .text-caption }
The figure shows the overview of miRNA
biogenesis. Pol II transcribes ssRNA from DNA. The ssRNA forms
pri-miRNA, that is further processed to a hairpin loop structure called
pre-miRNA by DGCR8 and Drosha. Exportin 5 together with Ran-GTP exports
pre-miRNA into the cytoplasm. Dicer cleaves pre-miRNA to form miRNA
duplex. Only one strand of the miRNA duplex is usually bound to the
Argonaute protein and loaded into the RISC
complex.
{: .fs-2 }

---

First, RNA polymerase II (Pol II) transcribes a miRNA gene on the
chromosome from DNA to single-stranded RNA (ssRNA) with 5' cap
and poly-A tail {% cite Lee2004 -f {{ bib }} %}. This ssRNA called primary miRNA (pri-miRNA)
can be several hundreds or thousands nucleotides long, and it may
contain one or more hairpin loops {% cite Lee2002 -f {{ bib }} %}. An enzyme called DiGeorge
Syndrome Critical Region 8 (DGCR8) recognizes the hairpin loop in
pri-miRNA, and a DGCR8 associated enzyme, called Drosha, cleaves the
hairpin from the pri-miRNA
{% cite Lee2003 Denli2004 Gregory2004 Han2004 Landthaler2004 -f {{ bib }} %}. This
cleavage results in a hairpin structure with approximately 60
nucleotides called precursor miRNA (pre-miRNA)
{% cite Saetrom2006 Lee2003 Zeng2003 Batuwita2009 -f {{ bib }} %}. Exportin 5 together
with Ran-GTP exports pre-miRNAs from the nucleus to the cytoplasm
{% cite Lund2004 Yi2003 -f {{ bib }} %}.

In the cytoplasm, a Ribonuclease (RNase) III enzyme, called Dicer,
cleaves the loop of pre-miRNA and produces a miRNA:miRNA\* duplex with
approximately 22 nucleotides {% cite Lee2003 -f {{ bib }} %}. Only one strand of this duplex
usually becomes a mature miRNA as a guide to the target mRNA, and the
other strand, defined as miRNA star-strand or miRNA\* {% cite Lau2001 -f {{ bib }} %}, is
eventually degraded {% cite Bartel2004 -f {{ bib }} %}. The mechanism of the strand selection
is unclear, but a strand that is less thermodynamically stable at its
5' end appears to be favored in some cases
{% cite Tomari2005 Kim2005 -f {{ bib }} %}. Argonaute (Ago) proteins are key proteins for
miRNA targeting {% cite Fagard2000b -f {{ bib }} %}. Ago2, which is one of the Ago clade
proteins, is mainly associated with mature miRNAs in mammals
{% cite Carthew2009 -f {{ bib }} %}. A protein complex called RNA-Induced Silencing Complex
(RISC) {% cite Hammond2000 -f {{ bib }} %} that incorporates Ago2, uses the mature miRNA as a
guide to bind and then catalyze specific target mRNAs {% cite Carthew2009 -f {{ bib }} %}.

Moreover, there are several known alternative pathways for miRNA
biogenesis. For instance, some intronic miRNAs bypass Drosha processing
by directly forming a pre-miRNA-like hairpin structure. These intronic
miRNAs are defined as mitrons {% cite Okamura2007 Ruby2007 -f {{ bib }} %} first identified
in *Drosophila* and *C. elegans* {% cite Ruby2007 -f {{ bib }} %}, and also found in mammals
{% cite Berezikov2007 -f {{ bib }} %}. Another example of alternative miRNA pathways is that
RNA polymerase III (Pol III) instead of Pol II transcribes some miRNAs
{% cite Bartel2004 -f {{ bib }} %}, especially those residing upstream of Alu sequences
{% cite Borchert2006 -f {{ bib }} %}. Alu sequences or Alu elements are abundant mobile
elements especially found in the primate genomes {% cite Batzer2002 -f {{ bib }} %}.

## 3.3 RNA interference is the central mechanism for gene regulation by miRNAs and small interfering RNA {#T:3.3}

MicroRNAs and siRNA regulate and control gene expression through RNAi
{% cite Mello2004 Carthew2009 -f {{ bib }} %}. Although siRNAs have biochemically
indistinguishable mature forms of ssRNAs from those of miRNAs, the siRNA
biogenesis pathway to its mature form is different from that of miRNA
{% cite Bartel2004 -f {{ bib }} %}. Dicer processes siRNA precursors, such as long dsRNAs or
small hairpin RNAs (shRNAs), and cleaves them into a ~22 nt dsRNA with 2-nt 3' overhangs
{% cite Bartel2004 Paddison2002 Carthew2009 -f {{ bib }} %}. This dsRNA form of siRNA is
essentially equivalent with the miRNA:miRNA\* duplex.

Major functionalities of siRNAs and miRNAs are that siRNAs are defenders
against foreign or invasive nucleic acid molecules such as viruses,
transposons, and transgenes {% cite Mello2004 -f {{ bib }} %}, whereas miRNAs are regulators
of endogenous protein-coding genes {% cite Carthew2009 -f {{ bib }} %}. Moreover, exogenous
siRNAs are widely used in gene knockdown experiments, and they are
potentially useful for gene therapy. Exogenous siRNAs are directly
introduced into the cytoplasm or taken up from the environment
{% cite Mello2004 Carthew2009 -f {{ bib }} %}.

The central mechanism of RNAi is that si/miRNAs loaded in RISC act like
guides to bind the sites of their target mRNAs. The RISCs loaded with
miRNAs are called miRISCs, whereas the RISCs with siRNAs are called
siRISCs {% cite Carthew2009 -f {{ bib }} %}. RNAi has several different gene silencing modes
(Fig. [3.2](#F:3.2)). The common gene silencing mode for siRNAs
and plant miRNAs is cleaving mRNAs that have near-perfect complementary
sites with the si/miRNAs (Fig. [3.2](#F:3.2)){% cite Bartel2004 -f {{ bib }} %}.
Two known gene silencing modes for animal miRNAs are
transcriptional repression and mRNA degradation (Fig. [3.2](#F:3.2)).
In either mode, miRNAs mainly target mRNAs
that have partial complementary sites on their 3' UTRs
{% cite Bartel2004 -f {{ bib }} %}. Although translational repression was initially thought
as the major regulatory model of animal miRNAs, a recent study used
ribosome profiling assay and reported that most target genes of animal
miRNAs were actually degraded {% cite Guo2010 -f {{ bib }} %}. The precise mechanism of this
degradation is still unclear, but it is possibly associated with
deadenylation, decapping, and exonucleolytic digestion of the mRNA
{% cite Behm-Ansmant2006a Giraldez2006 Wu2006 -f {{ bib }} %}.

### &nbsp; {#F:3.2}
{: .no_toc }
![Figure 3.2]({{ fig3_2 }}){:width="{{ page.figs.fig3_2[1] }}"}

#### **Figure 3.2**. miRNA target.
{: .no_toc .text-caption }
The figure shows three examples of RNAi regulation
by miRISC and siRISC. The long curved line represents mRNA that is
separated into three regions, 5' UTR, CDS, and 3' UTR.
Ribosomes synthesize peptides while moving through the mRNA from
5' to 3' direction. One siRISC binds on the CDS and two
miRISCs bind on the 3' UTR of mRNA, in this example. Plant miRNA
and siRNA have nearly perfect complementary which results in mRNA
cleavage. Animal miRNAs require only partial complementary, and they
either repress translation or contribute to mRNA
degradation.
{: .fs-2 }

---

Moreover, exogenous siRNAs are known to act like miRNAs and
down-regulate numerous unintended mRNAs in the same way as miRNA gene
silencing. This unintended effect is called siRNA off-targeting
{% cite Jackson2003 -f {{ bib }} %}. Considering this siRNA off-targeting is very important
to design effective exogenous siRNAs.

## 3.4 MicroRNAs have various regulatory roles that are associated with important physiological and pathological processes {#T:3.4}

Many miRNAs play important regulatory roles by negatively controlling
the expression level of mRNAs {% cite Bartel2004 -f {{ bib }} %}, and current estimates
indicate that at least 60% of human protein-coding genes are under some
influence of miRNAs {% cite Friedman2009 -f {{ bib }} %}. Many miRNAs, like *lin-4* and
*let-7*, are involved in cell development processes {% cite Stefani2008 -f {{ bib }} %}.
Other experimentally validated miRNA regulatory roles can be found in
many cellular processes, such as growth control, differentiation, stem
cell and germline proliferation, and apoptosis {% cite Alvarez-Garcia2005 -f {{ bib }} %}.
However, annotations of many miRNA regulations are still poor,
therefore, predicting accurate miRNA target genes is important to infer
miRNA regulatory roles.

MicroRNAs are also associated with human diseases because of their wide
range of gene regulatory roles {% cite Alvarez-Garcia2005 -f {{ bib }} %}. Several studies
revealed miRNA involved diseases, such as cancer {% cite He2005 Lu2005 -f {{ bib }} %},
heart disease {% cite Chen2008 Zhao2007 -f {{ bib }} %}, DiGeorge syndrome
{% cite Alvarez-Garcia2005 -f {{ bib }} %}, Alzheimer's disease, and central nerve system
(CNS) disorders {% cite Maes2009 -f {{ bib }} %}. Moreover, some viruses encode viral miRNA
genes {% cite Nair2006 -f {{ bib }} %}. These viral miRNAs potentially regulate fundamental
cellular processes both in the viruses and in their host cells
{% cite Boss2009 -f {{ bib }} %}.

## 3.5 Multiple properties of miRNA target recognition may enhance target efficacy in animal {#T:3.5}

Since most animal miRNAs have only partial complementary to their target
mRNAs {% cite Bartel2009 -f {{ bib }} %}, miRNA targeting usually requires additional
features for better target recognition. The most important feature is
the seed type, which is the region for the partial complementary. The
seed site contains six nucleotides from position 2 to 7 of the miRNA
{% cite Lewis2003 Brennecke2005 Bartel2009 -f {{ bib }} %}, as the position begins with 1
at the 5' end of the miRNA. Even though the definition of the
seed site is ubiquitous, the definition of the seed types is different
among different studies. Figure [3.3](#F:3.3)
shows nine common seed types that are widely accepted in many studies.
Seed types consist of stringent and non-stringent groups. Three seed
types, 7mer-A1, 7mer-m8, and 8mer, belong to the stringent group (Fig.
[3.3](#F:3.3)). These seed types have perfect Watson-Crick
paring in their seed sites, and they are usually stronger than those in
the non-stringent groups in terms of miRNA target recognition
{% cite Bartel2009 -f {{ bib }} %}. 7mer-A1 has an adenine (A) at position 1 of the target
mRNA. An adenine at position 1 of the mRNA is known to enhance miRNA
target recognition {% cite Lewis2005 -f {{ bib }} %}. 7mer-m8 has paring at position 8. 8mer
has an adenine at position 1 and paring at position 8. The non-stringent
group consists of 6mer, two G:U wobble, one loop, and two bulge types
(Fig. [3.3](#F:3.3)) {% cite Gaidatzis2007 -f {{ bib }} %}. They are less effective
than the stringent group, but they are still functional since miRISC can
tolerate some mismatches {% cite Ellwanger2011 -f {{ bib }} %}. 6mer has perfect seed paring,
whereas the other types are equivalent to 8mers except one mismatch or
wobble paring. LP has a loop in the seed site. GUM has a G:U wobble site
on the miRNA whereas GUT has a wobble site on the target mRNA.
Similarly, BM has a bulge on the miRNA whereas BT has a bulge on the
target mRNA.

### &nbsp; {#F:3.3}
{: .no_toc }
![Figure 3.3]({{ fig3_3 }}){:width="{{ page.figs.fig3_3[1] }}"}

#### **Figure 3.3**. miRNA seed types.
{: .no_toc .text-caption }
Examples of three stringent seed types (8mer,
7mer-A1, and 7mer-m8), and six non-stringent seed types (6mer, GUM, GUT,
LP, BM, and MT). The strand on the top of each seed type represents
position 1-8/9 of miRNA, and the bottom strand represents target
mRNAs.
{: .fs-2 }

---

Additional paring at the 3' part of miRNAs can increase the
efficacy of miRNA repression, and it can also compensate for a seed
mismatch to create a functional site {% cite Bartel2009 -f {{ bib }} %}. Three to four
matches at position 13-16 for stringent seeds, and four to five matches
at position 13-19 for non-stringent seeds are known as 3'
supplementary and 3' compensatory paring, respectively
{% cite Grimson2007 Bartel2009 -f {{ bib }} %}.

Many target sites are well conserved among closely related species
{% cite Friedman2009 -f {{ bib }} %}. However, there are many approaches to define "well
conserved" targets. For instance, some use perfect seed matches among
several species {% cite Krek2005 Enright2003 Lall2006 -f {{ bib }} %}, whereas others use
pre-defined conservation scores calculated by global phylogenetic
analysis {% cite Betel2010 Kertesz2007 -f {{ bib }} %}. Moreover, even though many targets
are well conserved, some targets are also species-specific. For
instance, one study predicted that about 30% of all experimentally
validated targets are poorly conserved {% cite Sethupathy2006 -f {{ bib }} %}.

The site accessibility of miRISC can be measured by computing the
secondary structure of target sites through minimum free energy
approaches. The site accessibility is potentially a very strong feature
to predict true miRNA target sites because it is directly linked to
target recognition. However, the precise mechanism of miRISC access on
its targets is unknown, and developing a precise prediction model with
mRNA secondary structure calculation usually requires huge computational
power. Some models used elaborate two step approaches with the first
step as initial forming of miRNA:mRNA complex, and the second step as
hybrid elongation to form the complete miRNA:mRNA complex
{% cite Kertesz2007 Long2007 -f {{ bib }} %}. An alternative feature to site accessibility
is to measure the occurrence of AU rich elements both upstream and
downstream of the seed site {% cite Grimson2007 -f {{ bib }} %}. Thermodynamic stabilities of
AU base pairs are much lower than that of GC base pairs, and it can be a
reason that sites surrounded by AU-rich context has better site
accessibility for miRISCs. Moreover, this AU rich approach is
computationally inexpensive with a good prediction performance
{% cite Grimson2007 -f {{ bib }} %}. Scoring AU context is a more reliable measurement of
target accessibility than any other currently available models with mRNA
secondary structure calculation {% cite Bartel2009 -f {{ bib }} %}.

Multiple target sites enhance miRNA target efficacy {% cite John2004 -f {{ bib }} %}.
Although the general effect of multiple sites is additive, the effect
can be synergistic when two miRNA targets are within optimal distance.
One reported such optimal distance is defined as two seed sites
separated by between 13 and 35 nt {% cite Saetrom2007 -f {{ bib }} %}. For example, a gene
with two 7mers within optimal distance is more down-regulated than a
gene with a single 8mer. However, the effect is not apparent when two
7mers are not within optimal distance. In this case, a gene with 8mer is
more down-regulated than a gene with two 7mers {% cite Bartel2009 -f {{ bib }} %}.

To summarize miRNA target recognition and efficacy, most animal miRNAs
bind on the 3' region of their target mRNAs by base paring. The
seed site, which is located at position 2 to 7 of the miRNA, is usually
used for this base paring, and the seed type tends to be one of the most
important features. There are also other additional features that can
contribute to target recognition and efficacy, such as 3'
additional paring, site conservation, site accessibility, and
cooperability of multiple target sites.

## 3.6 MicroRNA binding also occurs outside of the 3' UTR {#T:3.6}

Although the precise regulatory mechanism of miRISC's binding on the
3' UTR is unclear, it may cause deadenylation, decapping, and
exonucleolytic digestion of the mRNA
{% cite Behm-Ansmant2006a Giraldez2006 Wu2006 -f {{ bib }} %}. Moreover, miRISCs bind
other regions that reside outside of 3' UTRs, such as CDS
{% cite Hafner2010 -f {{ bib }} %}, 5' UTR {% cite Lee2009 Hafner2010 -f {{ bib }} %}, and promoter
regions {% cite Kim2008 Place2008 -f {{ bib }} %}.

Many miRNAs bind CDS regions; however, most of the sites are likely
non-functional because ribosomes seem to detach miRISCs from their
binding site while moving along the CDS region for translation
{% cite Bartel2004 -f {{ bib }} %}. Nonetheless, there are several evidences that some miRNA
target sites in CDS are functional. One example is that rare codons in
CDS regions tend to make ribosomes stalled, and miRNA target sites right
after these codons can be functional {% cite Gu2009 -f {{ bib }} %}. Moreover, some target
sites experimentally validated in CDS tend to have one very strong site
{% cite Duursma2008 Elcheva2009 -f {{ bib }} %}, or multiple sites within optimal distance
{% cite Forman2008 Tay2008 -f {{ bib }} %}.

Some miRNAs also target 5' UTR regions, though it is much less
common than 3' UTR and CDS regions {% cite Bartel2009 -f {{ bib }} %}. One intriguing
class of miRNA targets involved in 5' UTR is miBridge targets
{% cite Lee2009 -f {{ bib }} %}. The miBridge target is a miRNA target site that has a normal
seed site on the 3' UTR and a 5' portion paring on the
5' UTR simultaneously. One possible explanation for the
regulation of miBridge is that miBridge is involved in the translational
initiation by preventing ribosome scanning through the 5' UTR
{% cite Lee2009 -f {{ bib }} %}.

MicroRNA regulation can also occur inside the nucleus despite that
miRNA's major regulatory roles are in the cytoplasm
{% cite Hwang2007 Politz2006 -f {{ bib }} %}. The miRNA regulation in the nucleus is likely
at the transcriptional level rather than the translational level.
Several studies reported that miRNAs cause transcriptional silencing by
targeting promoter regions {% cite Kim2008 Place2008 -f {{ bib }} %}.

## 3.7 Some of coding and non-coding pairs of cis-NATs potentially may have regulatory interactions with miRNAs {#T:3.7}

A complex locus is a locus that contains several genes that interact
among each other {% cite Engstrom2006 -f {{ bib }} %}. Two major classes of complex loci are
cis-natural antisense transcripts (cis-NATs) and bi-directionally
promoters (Fig. [3.4](#F:3.4)) {% cite Engstrom2006 -f {{ bib }} %}. Many complex loci have
important regulatory roles, even though the precise mechanism is unknown
{% cite Duhig1998 Holmes2003 -f {{ bib }} %}.

### &nbsp; {#F:3.4}
{: .no_toc }
![Figure 3.4]({{ fig3_4 }}){:width="{{ page.figs.fig3_4[1] }}"}

#### **Figure 3.4**. Complex loci.
{: .no_toc .text-caption }
Complex loci consist of multiple genes that
interact among each other. Two major classes of complex loci are
cis-NATs and bi-directional promoters. Cis-NATs can be divided into
three categories depending on the directions of the overlaps. "Head to
Head" is that sense and antisense transcripts are partially overlapped
on their 5' ends. "Tail to Tail" is that sense and antisense
transcripts are partially overlapped on their 3' ends. "Full
overlap" is that one transcript is fully overlapped with the other
transcript. Bi-directional promoters reside between two genes arranged
head-to-head on opposite strands with less than 1000 base pairs
separating their transcription start sites
{% cite Trinklein2004a -f {{ bib }} %}.
{: .fs-2 }

---

Cis-NATs is a sense-antisense pair of transcripts that are partially
overlapping in the same locus {% cite Wang2005 -f {{ bib }} %}. Cis-NATs are relatively
common in many species, and they are quite abundant in human
{% cite Chen2004 Engstrom2006 Zhang2006 -f {{ bib }} %}. Three major classes, or
orientations, of cis-NATs are "head to head", "tail to tail", and "full
overlap" (Fig. [3.4](#F:3.4)) {% cite Osato2007 -f {{ bib }} %}. Although the molecular mechanism
of cis-NAT regulation is poorly understood, three models may explain the
potential cis-NAT regulation {% cite Osato2007 -f {{ bib }} %}. The first model is the
transcriptional collision model {% cite Osato2007 -f {{ bib }} %}, which can be the main
mechanism for "head to head" cis-NATs. The second model is the dsRNA
formation model of sense and antisense transcripts {% cite Osato2007 -f {{ bib }} %}. One
study showed that an endogenous ncRNA derived from a cis-NAT pair
regulates its anti-sense transcript of a protein coding gene in plants
{% cite Borsani2005 -f {{ bib }} %}. The third model is that cis-NATs are involved in
epigenetic regulation. This model is based on the evidence that some
ncRNAs are involved in the modification of chromatin structure and DNA
methylation in the promoter region {% cite Tufarelli2003 Beisel2011 -f {{ bib }} %}.

Bi-directional promoters reside between two genes arranged head-to-head
on opposite strands with less than 1000 base pairs separating their
transcription start sites {% cite Trinklein2004a -f {{ bib }} %}. Many pairs from
bi-directional promoters are co-expressed, but some are antiregulated
{% cite Trinklein2004a -f {{ bib }} %}. Bi-directional promoters are abundant; for instance,
they represent approximately 10% of all the genes in human
{% cite Trinklein2004a -f {{ bib }} %}.

The main objective of the third sub-goal: *[miRNA and other ncRNAs]({{ path_ncrna }}/)* is to
investigate potential miRNA interactions with other ncRNAs. Of these
classes of complex loci, some miRNAs potentially interact with
ncRNA:mRNA pairs of cis-NATs. In this case, miRNAs indirectly regulate
the expression of the mRNAs in cis-NATs through directly regulating
their paired ncRNAs (Fig. [3.5](#F:3.5)). Bi-directional promoters may also have
ncRNA:mRNA pairs that potentially involve miRNAs regulation. Annotated
data of bi-directional promoters are available for mRNA:mRNA pairs
{% cite Engstrom2006 -f {{ bib }} %}, but there are few reliable data for ncRNA:mRNA pairs of
bi-directional promoters. Therefore, we excluded bi-directional
promoters and focused on cis-NATs, especially on ncRNA:mRNA pairs of
cis-NATs, in the third sub-goal: *[miRNA and other ncRNAs]({{ path_ncrna }}/)*.

### &nbsp; {#F:3.5}
{: .no_toc }
![Figure 3.5]({{ fig3_5 }}){:width="{{ page.figs.fig3_5[1] }}"}

#### **Figure 3.5**. miRNA regulation on cis-NAT.
{: .no_toc .text-caption }
The figure illustrates two different
potential modes of miRNA regulation on cis-NATs. Direct miRNA regulation
is a normal regulatory mode of miRNAs, in which miRNA binds on the
3' UTR of mRNA. Indirect mode is that miRNA regulates the
protein coding mRNA in cis-NAT indirectly through binding the non-coding
transcript.
{: .fs-2 }

---

## 3.8 Chromatin associated RNAs are potentially associated with the modification of chromatin structure {#T:3.8}

Chromatin associated RNAs (CARs) are experimentally validated non-coding
RNAs that can bind a part of the chromatin directly {% cite Mondal2010 -f {{ bib }} %}. Since
CARs affect their host and neighboring genes {% cite Mondal2010 -f {{ bib }} %}, CARs can be
seen as a class of complex loci. CARs are likely involved in the
regulation of chromatin structure by recruiting chromatin-modifying
complexes (Fig. [3.6](#F:3.6)). This scenario is supported by the evidence that
long ncRNAs regulate chromatin modification by guiding chromatin
remodeling complexes to specific genome loci
{% cite Mercer2009 Whitehead2009 -f {{ bib }} %}. In addition to long ncRNAs, RNAi is also
known to have roles in the regulation of chromatin structure. For
instance, in fission yeast, CARs serve as assembly platform to the
RNA-induced initiation of transcriptional gene-silencing (RITS) complex.
In this case of fission yeast, siRNAs associate with AGO1 and guide the
RITS complex to CARs {% cite Beisel2011 -f {{ bib }} %}.

Similar to ncRNA:mRNA pairs of cis-NATs, CARs potentially have
interactions with miRNAs, though there is currently no strong evidence
to support this. Therefore, we chose cis-NATs and CARs to investigate
their potential interactions with miRNAs in the third sub-goal: *[miRNA and other ncRNAs]({{ path_ncrna }}/)*.

### &nbsp; {#F:3.6}
{: .no_toc }
![Figure 3.6]({{ fig3_6 }}){:width="{{ page.figs.fig3_6[1] }}"}

#### **Figure 3.6**. CARs.
{: .no_toc .text-caption }
Upper panel shows a protein complex, a CAR, and
nucleosomes. The complementary DNA region to the CAR is indicated in
red. Lower panel shows one example of the CAR regulation to the
chromatin. The CAR acts as a guide for the protein complex that can
modify the chromatin structure.
{: .fs-2 }

---

## References {#S:3.9}
{% bibliography --cited_in_order -f {{ bib }} %}
