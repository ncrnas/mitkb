---
layout: default
title: 5 Statistical methods
parent: Overview
nav_order: 6
usemathjax: true
description: "Statistical tests and methods"
comments: true
group: thesis
folders:
  experiment: mirna-high-throughput-experiments
  ncrna: mirna-and-other-ncrnas
scholar:
  bibliography: thesis_5
---

{% capture path_experiment %}{{ site.baseurl }}/{{ page.folders.experiment }}{% endcapture %}
{% capture path_ncrna %}{{ site.baseurl }}/{{ page.folders.ncrna }}{% endcapture %}

{% assign bib = page.scholar.bibliography %}

# 5 Statistical tests and methods
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

This chapter describes various statistical methods used in our research.
We used basic statistical methods, such as parametric tests and
correlation, to achieve all three sub-goals of our research, but we used
multiple non-parametric tests only for the second and third sub-goals:
*[miRNA high-throughput experiments]({{ path_experiment }}/)*,
and *[miRNA and other ncRNAs]({{ path_ncrna }}/)*.
Moreover, we mainly used the resampling approach to achieve the third
sub-goal: *[miRNA and other ncRNAs]({{ path_ncrna }}/)*.

## 5.1 Parametric statistics: Parameters and Hypothesis testing {#S:5.1}

Statistics tests play important roles in biology to analyze different
kinds of data from biological experiments. Most analyses in biology use
parametric statistics, which can be used only when the data are likely
from a known distribution with parameters. The most commonly used
parametric distribution is the normal distribution, which has two
parameters: $$\mu$$ (mean) and $$\sigma^{2}$$ (variance). Mean is a measure
of central tendency, whereas variance is a measure of spread. Standard
deviation ($$\sigma$$), which is the square root of variance, is also a
measure of spread. The normal distribution is defined by its probability
density function {% cite Rosner2006 -f {{ bib }} %} as:

$$\label{eq_norm} f(x) = \dfrac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}x^{2}}. \tag{5.1}$$

The parametric statistics offers various analysis methods, but the most
common method is hypothesis testing. Hypothesis testing is that the null
hypothesis, denoted by <i>H<sub>0</sub></i>, is tested to infer whether the
alternative hypothesis, denoted by <i>H<sub>1</sub></i>, is true or false. The
alternative hypothesis contradicts the null hypothesis in some sense
{% cite Rosner2006 -f {{ bib }} %}, therefore, if <i>H<sub>0</sub></i> is rejected, <i>H<sub>1</sub></i> is inferred as
"True", whereas if <i>H<sub>0</sub></i> is accepted, <i>H<sub>1</sub></i> is inferred as "False".

The p-value is the probability of incorrectly rejecting the null
hypothesis when it is true. For example, the p-value 0.05 means that
there is 5% chance of rejecting the null hypothesis when it is true. Two
significance levels, 0.05 and 0.01, are commonly used as statistically
"significant" or "highly significant". Moreover, two types of errors may
occur when the null hypothesis is either accepted or rejected (Table
[5.1](#T:5.1)). Type I error is the error of rejecting the
null hypothesis when it is true, whereas Type II error is the error of
accepting the null hypothesis when it is false. Type I error is more
important for hypothesis testing because the p-value is equivalent to
the probability of Type I error.

<br />
### **Table 5.1**. Four possible outcomes of hypothesis testing. {#T:5.1}
{: .no_toc .text-caption }
The table shows the four possible outcomes of hypothesis testing with two error types.
{: .fs-2 }

|                             | <i>H<sub>0</sub></i> is true           | <i>H<sub>1</sub></i> is true           |
|+---------------------------+|+--------------------------------------+|+--------------------------------------+|
| Accept <i>H<sub>0</sub></i> | True Negative                          | False Negative <br /> (Type II error)  |
| Reject <i>H<sub>0</sub></i> | False Positive <br />  (Type I error)  | True Positive                          |

---

For analysis of biological data, one of the most common methods for
hypothesis testing is two sample inference. For example, when two
samples, $$x_{1}$$ and $$x_{2}$$, are normally distributed with equal
variance, the test statistic $$t$$ {% cite Rosner2006 -f {{ bib }} %} is:

$$\label{eq_stu_t} t = \dfrac{\overline{x}_{1}-\overline{x}_{2}}{S\sqrt{\dfrac{1}{n_{1}}+\dfrac{1}{n_{2}}}}, \tag{5.2}$$

where $$S = \sqrt{((n_{1}-1)s_{1}^{2}+(n_{2}-1)s_{2}^{2})/(n_{1}+n_{2}-2)}$$,
$$n_{1}$$ and $$n_{2}$$ are sample size of $$x_{1}$$ and $$x_{2}$$, and $$s_{1}$$
and $$s_{2}$$ are standard deviation of $$x_{1}$$ and $$x_{2}$$. The test
statistics enables to determine the sampling distribution under the null
hypothesis, hence the p-value can be calculated from the test
statistics. The calculation method of the test statistics varies
depending on the type of distributions and the properties of the
samples. In the example above, the test statistic $$t$$ follows Student's
t distribution. This test is called two sample Student's t-test, and it
is used when the variances need to be calculated directly from the
samples.

## 5.2 Non-parametric statistical methods: Wilcoxon rank-sum and Kolmogorov-Smirnov tests {#S:5.2}

The parametric statistical methods are valid only when the samples of
interest follow known distributions with parameters. However, the
original distributions of samples are quite often unknown, therefore,
non-parametric statistical methods should be used in these cases.
Non-parametric methods tend to be more robust, and their applicability
is much wider than corresponding parametric methods because they need
fewer assumptions. However, they require a larger sample size to draw
the same conclusion of their corresponding parametric methods because
they usually have less statistical power.

One of the most commonly used non-parametric statistical methods is the
Wilcoxon rank-sum test {% cite Mann1947 Wilcoxon1945 -f {{ bib }} %}, which is a two sample
non-parametric test when the samples are independent. It uses a ranking
procedure, in which individual values are ordered and ranked. There are
two approaches, the Mann-Whitney U-test and the normal approximation, to
calculate the test statistics for the Wilcoxon rank-sum test. (i) The
Mann-Whitney U-test {% cite Mann1947 -f {{ bib }} %} is used to test whether two samples are
drawn from the same distribution. The U value for the U-test is
calculated from the sum of the ranks and the sample size. For example,
the $$U$$ value for sample $$x$$, denoted as $$U_{x}$$, is calculated as
$$U_{x}=R_{x}-n_{x}(n_{x}+1)/2$$ where $$R_{x}$$ is the sum of the ranks of
$$x$$, and $$n_{x}$$ is the sample size of $$x$$. (ii) The normal
approximation can be used instead of the U-test when the sample size is
large enough (>10) for both samples {% cite Rosner2006 -f {{ bib }} %}.
The test statistics T for two independent samples, $$x$$ and $$y$$, is:

$$\label{eq_wc} T = \dfrac{\left[ \left| R_{1} - \dfrac{n_{1}(n_{1}+n_{2}+1)}{2} \right| - \dfrac{1}{2} \right]}{\sqrt{\left( \dfrac{n_{1}n_{2}}{12} \right) (n_{1}+n_{2}+1))}}, \tag{5.3}$$

where $$R_{x}$$ is the sum of the ranks of $$x$$, and $$n_{x}$$ and $$n_{y}$$
are the sample size of $$x$$ and $$y$$.

The Kolmogorov-Smirnov test (K-S test) is a non-parametric statistical
method that does not use ranking procedures. For instance, the two
sample K-S test is used to infer whether two continuous distributions
differ. The K-S test requires two continuous distribution functions,
$$F(x)$$ and $$G(y)$$ where the two distributions are defined as
$$X_{1} \ldots X_{m}$$ with the size $$m$$, and $$Y_{1} \ldots Y_{n}$$ with
the size $$n$$. In this case, however, both distributions are unknown.
Therefore, empirical distribution functions, $$\hat{F}(x)$$ and
$$\hat{G}(y)$$, are used instead. An empirical distribution function is a
step function defined as {% cite Kvam2007 -f {{ bib }} %}:

$$\label{eq_empr} \hat{F}_{n}(x) = \dfrac{1}{n} \sum_{i=1}^{n} I(X_{i} \leq x), \tag{5.4}$$

where $$I(X_{i} \leq x)$$ is the indicator function, and is equal to 1 if
$$X_{i} \leq x$$ and 0 otherwise. The test statistics $$D$$ for the K-S test
{% cite Arnold2005 -f {{ bib }} %} is:

$$\label{eq_ks} D = \max_x | \hat{F}(x) - \hat{G}(x) |, \tag{5.5}$$

for the hypothesis of this test:

$$\begin{array}{l l l}
      H_{0}: & F(x) = G(x)    & \textrm{for all $x$},  \\
      H_{1}: & F(x) \neq G(x) & \textrm{for some $x$}.  \\
    \end{array}$$

<i>H<sub>0</sub></i> is rejected at level $$\alpha$$ when D is too
large as in:

$$\label{eq_ks_d} \dfrac{mn}{m+n}D > K_{\alpha}, \tag{5.6}$$

where the critical value of the Kolmogorov distribution, $$K_{\alpha}$$, is
found from $$P(K \leq K_{\alpha}) = 1 - \alpha$$ {% cite Marsaglia2003 -f {{ bib }} %}.

## 5.3 Resampling: Bootstrap and Permutation test {#S:5.3}

In statistics, resampling methods treat an observed sample as a finite
population {% cite Rizzo2008 -f {{ bib }} %} and reuse the data of the observed sample.
Resampling approaches have gained popularity in recent years because
sufficient computational power has become available to make enough
random samples to achieve robust statistical analysis {% cite Moore2009 -f {{ bib }} %}.
Three major applications of resampling are (i) the bootstrapping method
as estimating the characteristics of the sample, (ii) the permutation
test as exchanging labels to perform significant tests, and (iii) the
cross validation approach as validating models by using random subsets.
This section briefly explains two such applications, bootstrapping and
permutation tests. Cross-validation is explained in the next chapter as
an evaluation method for machine learning.

Bootstrapping {% cite Efron1994 -f {{ bib }} %} is a resampling method that generates random
samples from an observed sample with replacement. Sampling with
replacement means that a randomly drawn observation should put back in
the original sample before drawing the next one {% cite Moore2009 -f {{ bib }} %}. Bootstrap
is mainly used for estimating population characteristics by collecting
the statistics from many resamples.

Permutation tests are non-parametric procedures based on resampling. The
tests randomly rearrange the data without replacement to create the
sampling distribution of the test statistics under the null hypothesis
{% cite Moore2009 -f {{ bib }} %}. To illustrate the basic idea of a permutation test,
suppose we have two samples $$x$$ with size m and $$y$$ with size n. We
first pool all the data points from $$x$$ and $$y$$, and randomly draw a
point from this pooled set without replacement to make resample controls
with size $$m$$ and $$n$$. We then iterate this resampling to make a
permutation distribution. The number of resamples depends on a required
statistical power, but 1000 is widely used. The p-value is calculated by
comparing the parameter of the original observation with the permutation
distribution of the parameter {% cite Moore2009 -f {{ bib }} %}. For instance, if 14 cases of
999 resamples are larger than the parameter of the original sample, the
p-value of one-sided test can be calculated as:

$$\label{eq_pval_perm}
\dfrac{14+1}{999+1} = \dfrac{15}{1000} = 0.015. \tag{5.7}$$

Adding one to both numerator and denominator of Eq. \eqref{eq_pval_perm}
improves the estimate of the p-value.
Moreover, Fisher's exact test {% cite Fisher1922 -f {{ bib }} %} is a special case of
permutation test that is used in the analysis of categorical data,
especially for contingency tables with small sample size. For instance,
when the Fisher's exact test is used for a 2 × 2 table, it
calculates the exact probability by considering all possible values
under the assumption that the margins of the table are fixed
{% cite Moore2009 -f {{ bib }} %}.

## 5.4 Multiple comparison tests: Analysis of variance, Bonferroni correction, and False discovery rate {#S:5.4}

In addition to one and two sample inferences, multisample inference is
also important in many biological analyses. Two major approaches for
multisample inference are the analysis of variance (ANOVA) and multiple
comparison tests.

The ANOVA test concerns the means of several groups, and its hypothesis
is:

$$\begin{array}{l l}
      H_{0}: \textrm{all means are equal},   \\
      H_{1}: \textrm{not all means are equal}.  \\
    \end{array}$$

The F test can be used when each group follows a
normal distribution, and the test statistics $$F$$ is:

$$\label{eq_ftest}
F = \dfrac{\textrm{Between Mean Square}}{\textrm{Within Mean Square}}. \tag{5.8}$$

"Between Mean Square" measures the mean among the groups, whereas
"Within Mean Square" measures the mean among individuals within the same
group {% cite Moore2009 -f {{ bib }} %}.

As for the non-parametric approach, the Kruskal-Wallis test
{% cite Kruskal1952 -f {{ bib }} %} can be used if some group has no specific distribution.
It is a non-parametric ANOVA test, and it uses ranking procedures as
calculating the sums of the ranks for the groups {% cite Moore2009 -f {{ bib }} %}.

Multiple comparisons procedures enable to detect the groups that differ
from the others. The most common approach of multiple comparisons is to
simply compare all possible pairs by two sample inference, followed by
p-value adjustment. The p-value adjustment is critical for multiple
comparisons because some differences likely occur just by chance if
there is a large number of groups, and every pair of groups should be
compared {% cite Moore2009 -f {{ bib }} %}. Many p-value correction methods have been
developed for various cases, and most of them either change the
significance level of the test, $$\alpha$$, or consider the false
discovery rate (FDR), which is (False Positive) / (False Positive + True
Negative).

The Bonferroni correction computes an alternative significance level,
$$\alpha^{*}$$, defined as {% cite Rosner2006 -f {{ bib }} %}:

$$\label{eq_bonf} \alpha^{*} = \dfrac{\alpha}{\binom{k}{2}}, \tag{5.9}$$

where $$k$$ is the number of groups. For example, there are 45 possible pairs
when $$k = 10$$, therefore $$\alpha^{*} = \alpha / 45$$. One critical
problem of the Bonferroni correction is to control the overall
experimental-wise type I error rate, hence, no significant pairs may be
found when $$k$$ is very large.

The FDR control, or the Benjamini and Hochberg correction
{% cite Benjamini1995 -f {{ bib }} %}, is to modify p-values without controlling the overall
experimental-wise type I error rate. The FDR aims to control the
proportion of false-positive results {% cite Rosner2006 -f {{ bib }} %}, therefore, several
significant pairs will be expected to be found.

## 5.5 Correlation: Pearson's and Spearman's correlation coefficients {#S:5.5}

In statistics, the correlation indicates the statistical relationships
between two or more samples. The correlation coefficient, which ranges
from -1 to 1, represents the degree of correlation. Samples are
positively correlated, negatively correlated, and uncorrelated when the
coefficient is greater than 0, less than 0, and exactly 0, respectively
{% cite Rosner2006 -f {{ bib }} %}. It is also important to test the significance of
correlation by determining whether an observed correlation coefficient
is significantly different from zero or not.

Pearson's correlation coefficient, usually denoted as $$r$$, indicates the
linear relationships between two samples that follow normal
distribution. For example, two samples, X and Y, have individual
observations represented as $$x_{i}$$ and $$y_{i}$$ where i = 1, 2, \..., n.
The Pearson's correlation coefficient, $$r_{xy}$$, is {% cite Rosner2006 -f {{ bib }} %}:

$$\label{eq_pearson} r_{xy} = \dfrac{\sum_{i=1}^{n}(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sqrt{\sum_{i=1}^{n}(x_{i}-\bar{x})^{2}\sum_{i=1}^{n}(y_{i}-\bar{y})^{2}}}. \tag{5.10}$$

This is equivalent to:

$$r_{xy} = \dfrac{s_{xy}}{s_{x}s_{y}} = \dfrac{\textrm{sample covariance between $x$ and $y$}}{(\textrm{sample standard deviation of $x$})(\textrm{sample standard deviation of $y$})}.$$

Spearman's correlation coefficient, denoted as $$\rho$$, is a
non-parametric method. Hence, it can be used when the distributions are
unknown. The calculation of $$\rho$$ is similar to that of $$r$$, but the
ranks are used instead of the actual observation values {% cite Rosner2006 -f {{ bib }} %}.

## 5.6 Regression analysis: Multivariate linear regression {#S:5.6}

Regression analysis is an important statistical method with biological
data because it identifies the characteristics and relationships among
multiple factors {% cite Schneider2010 -f {{ bib }} %}. Many types of regression analysis
exist depending on different criteria such as univariate versus
multivariate, or linear versus non-linear, for instance.

Multivariate linear regression can be performed to study the effect of
multiple variables and their linear relationships in the data. The
linear regression model relating $$y$$ to $$x_{1}$$, \..., $$x_{k}$$, is
{% cite Rosner2006 -f {{ bib }} %}:

$$\label{eq_lreg} y = \alpha + \displaystyle\sum_{j=1}^{k}\beta_{j}x_{j} + e, \tag{5.11}$$

where $$e$$ is an error term that is normally distributed with mean 0 and
variance $$\sigma^{2}$$. The main goal of the regression analysis is to
minimize $$e$$ and estimate the best $$\alpha$$ and $$\beta$$ to fit this
model.

The goodness of fit for a regression model indicates how well the
observed data fit the predicted model. One of the approaches to measure
the goodness of fit for multiple regression models is to perform
residual analysis {% cite Rosner2006 -f {{ bib }} %}. Moreover, many procedures of regression
analysis overlap with those of machine learning. Therefore, several
machine learning evaluation methods are also useful to evaluate
regression models. Some of these evaluation methods for machine learning
are explained in the next chapter.

## References {#S:5.7}
{% bibliography --cited_in_order -f {{ bib }} %}
