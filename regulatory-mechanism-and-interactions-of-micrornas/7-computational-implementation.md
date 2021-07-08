---
layout: default
title: 7 Implementation
parent: Overview
nav_order: 8
description: "Computational implementation"
scholar:
  bibliography: thesis_7
---

{% assign bib = page.scholar.bibliography %}

# 7 Computational implementation
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

This chapter gives an overview of the computational implementation
approaches used in our research. We mainly used Python for general
programming, and R for statistical programming and analysis. This
chapter also briefly gives additional information about software
development methodologies and data storage.

## 7.1 Software development methodologies: Rapid application development and Test-driven development {#S:7.1}

Many conventional software development methodologies, such as variants
of the waterfall method {% cite Royce1970 -f {{ bib }} %}, require strict documentation at
the design phase, and full implementation rather than prototyping in the
implementation phase. A waterfall method is a sequential design process
flowing steadily downwards through the phases of the software
development life cycle. These strict and non-flexible software
development phases of conventional methodologies led to many failed
system development projects in the 1980s and early 1990s, especially in
large-scale projects. Rapid application development (RAD) {% cite Martin1991 -f {{ bib }} %}
is a relatively new software development methodology, which aims to
decrease the complexity of implementation and increase the speed of
application development. There are many types of RADs, such as Scrum
{% cite Rising2000 -f {{ bib }} %}, Agile software development (Agile) {% cite Cockburn2001 -f {{ bib }} %}, and
Extreme Programming (XP) {% cite Auer2001 -f {{ bib }} %}. Most of them focus on simplifying
each phase and reducing the duration of the software development cycle.
One of the most suitable RADs for small or mid-size bioinformatics
projects is Test-driven development (TDD) {% cite Beck2002 -f {{ bib }} %}, which is
equivalent to the test-first programming concepts of XP. TDD enforces
the creation of unit tests before actual coding. Although full
compliance to TDD is not necessary, making as many unit tests as
possible with mock data can ensure high reliability of the application.

## 7.2 Programming languages: Object-oriented programming and Python {#S:7.2}

The most popular programming paradigm today is object-oriented
programming (OOP). OOP uses "objects" defined by corresponding
"classes". Objects are actual data with data structure and procedures,
whereas classes are definitions or templates to make objects. Many
programming languages currently support full or partial OOP, and some of
the popular ones are C++, Java, Perl, and Python. All of these
programming languages are freely available (Table [7.1](#T:7.1)),
and they are widely used in bioinformatics analysis.
Table [7.1](#T:7.1) also shows two additional languages Haskell
and Go, as examples of functional programming and concurrent programming
paradigms, though these paradigms are less common than OOP in general.

<br />
### **Table 7.1**. Programming languages. {#T:7.1}
{: .no_toc .text-caption }
The table shows a list of freely
available programming languages. "program", "type", and "URL for
software environment" represent the name of programming language, the
name of programming paradigm, and the URL for downloading software
environment, respectively. OOP, Func, Conc in the "type" column
represents three different programming paradigms: object-oriented,
functional, and concurrent programming, respectively.
{: .fs-2 }

| Program       | Type | URL for software environment              |
|---------------|------|-------------------------------------------|
| C++ (GNU)     | OOP  | <https://gcc.gnu.org>                     |
| Java (Oracle) | OOP  | <https://www.oracle.com/technetwork/java> |
| Perl          | OOP  | <https://www.perl.org>                    |
| Python        | OOP  | <https://www.python.org>                  |
| Haskell       | Func | <https://www.haskell.org>                 |
| Go            | Conc | <https://golang.org>                      |

---

Among them, Python has emerged as one of the most popular languages in
bioinformatics. Python requires no static type checking, which enhances
the productivity with the RAD approach. It also offers multiple
programming paradigms, therefore, it can use both object-oriented and
functional programming in the same module, for instance. Moreover,
Python offers two very powerful libraries for scientific computing:
NumPy (<https://numpy.org/>) and SciPy (<https://www.scipy.org/>).
BioPython (<https://biopython.org>) provides a set of libraries for
biological computation to Python. A machine learning package for Python
called PyML provides useful functions to build and test a SVM model
{% cite Ben-Hur2008 -f {{ bib }} %}. We mainly used PyML to build our two-step SVM model for
miRNA target prediction.

## 7.3 Statistical programming languages: R and other statistical computing languages {#S:7.3}

Some programming languages are specialized for statistical computing and
graphics. For instance, SAS, SPSS, STATA, and R support software
environments for statistical computing, whereas MATLAB and Mathematica
are languages that provide statistical features. Among them, only R is
open source software and freely available (Table [7.2](#T:7.2)).
Moreover, R provides many additional
libraries and also a comprehensive framework for high-throughput genome
data analysis, called Bioconductor (<https://www.bioconductor.org>),
hence, it is the most popular statistical computing language for
bioinformatics today.

<br />
### **Table 7.2**. Programming languages for statistical analysis. {#T:7.2}
{: .no_toc .text-caption }
The table shows
a list of programming languages that can be used for statistical
analysis. "program", license", and "URL" represent the name of
programming language, the type of license, and the URL for
organizations or institutes that provide the software, respectively.
{: .fs-2 }

| Program     | License     | URL                                         |
|-------------|-------------|---------------------------------------------|
| SAS         | proprietary | <https://www.sas.com>                       |
| SPSS        | proprietary | <https://www.ibm.com/analytics/spss-statistics-software> |
| STATA       | proprietary | <https://www.stata.com>                     |
| R           | open source | <https://www.r-project.org>                 |
| MATLAB      | proprietary | <https://www.mathworks.com/products/matlab> |
| Mathematica | proprietary | <https://www.wolfram.com/mathematica>       |

---

## 7.4 Data storage: Text files and MySQL {#S:7.4}

Handling the large size data from experiments with high-throughput
technologies usually requires a method for effective data retrieval and
manipulation. The easiest approach is using a text file with
user-defined or pre-defined format. Some examples of popular pre-defined
formats in bioinformatics are FASTA for nucleotide and peptide
sequences, GFF (general feature format) for positional information with
additional features in genome, and MAF (multiple alignment format) for
multiple alignments.

A relational database (RDB) {% cite Codd1970 -f {{ bib }} %} management system offers more
elaborate data storage mechanisms than simple text files. In RDB, data
are usually accessed through the structured query language (SQL), and
all data are stored in multiple tables. MySQL is the most popular freely
available RDB used by bioinformatics projects, but other free RDBs, such
as PostgreSQL or Postgres, and SQLite, are also widely used (Table [7.3](#T:7.3)).

<br />
### **Table 7.3**. Relational databases. {#T:7.3}
{: .no_toc .text-caption }
The table shows a list of relational and NoSQL databases.
<sup>1</sup>PostgreSQL Global Development Group.
<sup>2</sup>SQLite Consortium.
<sup>3</sup>Google App Engine provides BigTable accessibility.
{: .fs-2 }

| Name       | Type  | Provider                | URL                                            |
|------------|-------|-------------------------|------------------------------------------------|
| MySQL      | RDB   | Oracle                  | <https://www.mysql.com>                         |
| PostgreSQL | RDB   | PGDG<sup>1</sup>        | <https://www.postgresql.org>                    |
| SQLite     | RDB   | SQLite Cons<sup>2</sup> | <https://www.sqlite.org>                        |
| MongoDB    | NoSQL | 10gen                   | <https://www.mongodb.org>                       |
| BigTable   | NoSQL | Google                  | <https://cloud.google.com/appengine><sup>3</sup> |
| SimpleDB   | NoSQL | Amazon                  | <https://aws.amazon.com/simpledb>               |

---

In RDB, the data in multiple tables are "joined" when retrieving them
together. All RDB management systems have very poor performance with
joining tables at tera- or peta- byte level. Therefore, NoSQL database
management systems have emerged to control data even at peta byte level.
NoSQL usually avoids SQL usage and relational tables. Many NoSQL systems
are available today, and some popular NoSQLs are MongoDB, Google
BigTable {% cite Chang2006 -f {{ bib }} %}, and Amazon SimpleDB (Table [7.3](#T:7.3)).

Even though handling data at tera byte level is important as more
sequence data from the next generation sequencing become available, many
programming languages currently lack easy-to-use libraries to access
NoSQL management systems. Therefore, using both text files and RDBs
rather than NoSQL is still a major practice in bioinformatics.

## References {#S:7.5}
{% bibliography --cited_in_order -f {{ bib }} %}
