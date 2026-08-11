---
title: Bessel's Correction
---

# Bessel's Correction

← [Back to the statistical method navigator](../index.md)

---

## Quick question

In the previous chapter we learned that the Standard Error of the Mean (SEM) is usually computed as

\[
SE
\approx
\frac{s}{\sqrt{n}}.
\]

However, this raises a natural question.

> **Where does the sample standard deviation \(s\) come from?**

Unlike the population standard deviation, it cannot be computed directly because the population is unknown.

Instead, it must be estimated from the sample itself.

---

## Why can't we compute the population standard deviation?

If the entire population were available, the population standard deviation would be

\[
\boxed{
\sigma
=
\sqrt{
\frac1N
\sum_{i=1}^{N}
(x_i-\mu)^2
}
}
\]

where

- \(N\) is the population size;
- \(\mu\) is the population mean.

Unfortunately, neither quantity is usually known.

In practice, we only observe a sample containing

\[
n \ll N
\]

observations, and we must estimate both the population mean and the population
standard deviation from that sample.

---

## A natural first attempt

The most obvious idea is simply to replace the unknown population
quantities by their sample counterparts.

This leads to

\[
\sqrt{
\frac1n
\sum_{i=1}^{n}
(x_i-\bar{x})^2
}.
\]

At first sight, this seems perfectly reasonable.

After all, the sample mean is our best estimate of the unknown population mean.

So why shouldn't this formula work?

---

## A surprising problem

Surprisingly, this **estimator** is **systematically too small**.

On average, it underestimates the true population variability.

Why?

Because the sample mean,

\[
\bar{x},
\]

is computed from the very same observations used to estimate the variability.

Consequently, the observations are, on average, **slightly closer to the sample mean** than they would be to the true
population mean.

As a result, the estimated variability becomes slightly too small.

---

!!! tip "The sample mean makes the sample look slightly less variable"

    The sample mean is chosen to be the centre of the observed sample.

    Consequently, the deviations

    \[
    x_i-\bar{x}
    \]

    are, on average, slightly smaller than the deviations

    \[
    x_i-\mu.
    \]

    This causes the naive estimator to underestimate the true population variability.

---

## Correcting the bias

To compensate for this small systematic underestimation, the denominator

\[
n
\]

is replaced by

\[
n-1.
\]

The resulting estimator is called the **sample standard deviation**, and is computed as

\[
\boxed{
s
=
\sqrt{
\frac1{n-1}
\sum_{i=1}^{n}
(x_i-\bar{x})^2
}
}
\]

This adjustment is known as **Bessel's correction**.

!!! tip "A practical recommendation for data analysis"

    In most real-world data analysis projects, you should treat the
    available dataset as a **sample**, not as the entire population.

    This means that:

    - the sample mean should be interpreted as $\bar{x}$ not as the population mean $\mu$
    
    - the sample standard deviation $s$  should be used instead of the unknown population standard deviation $\sigma$

    Consequently, when using statistical software, remember to compute
    the sample standard deviation using **Bessel's correction**
    (typically `ddof=1`).

    Unless you know that your dataset contains the **entire population**,
    treating it as a sample is usually the safest choice for statistical
    inference.

---

## Why does dividing by \(n-1\) work?

The detailed mathematical proof requires concepts from mathematical
statistics such as expectation and unbiased estimators.

However, the underlying intuition is surprisingly simple.

When computing the sample standard deviation, we first estimate the sample mean

\[
\bar{x}.
\]

Because this mean is computed from the same observations, not all observations can vary independently.

One degree of freedom has already been used to estimate the sample mean.

---

## A simple example

Suppose that a sample contains four observations, and that their sample mean is known to be

\[
10.
\]

If we already know the first three observations, the fourth one is no longer free to take any value.

It must satisfy

\[
\frac{x_1+x_2+x_3+x_4}{4}=10.
\]

Equivalently,

\[
x_4
=
40-x_1-x_2-x_3.
\]

The last observation is therefore completely determined by the other three.

Although the sample contains four observations, only three of them are free to vary.

This is why we say that the sample has

\[
n-1
\]

degrees of freedom.

---

!!! tip "One degree of freedom is used to estimate the sample mean"

    Estimating the sample mean consumes one degree of freedom.

    Consequently, only

    \[
    n-1
    \]

    independent pieces of information remain available for estimating
    the population variability.

---

## Why is this important?

Without Bessel's correction, the sample variance would systematically underestimate the population variance.

Using

\[
n-1
\]

instead of

\[
n
\]

removes this systematic bias,

making the sample variance an unbiased estimator of the population variance.

---

!!! note "A subtle point"

    Strictly speaking, Bessel's correction makes the **sample variance**

    \[
    s^2
    \]

    an unbiased estimator of the population variance

    \[
    \sigma^2.
    \]

    The sample standard deviation

    \[
    s
    \]

    itself remains a slightly biased estimator of

    \[
    \sigma,
    \]

    although this bias rapidly decreases as the sample size increases.

---

!!! tip "Python reminder"

    Unless you know that your dataset represents the entire population, treat it as a **sample**.

    Consequently, use the sample standard deviation, which includes Bessel's correction.

    For example,

    ```python
    import numpy as np

    s = np.std(data, ddof=1)
    ```

    In contrast, Pandas computes the sample standard deviation (using ddof=1) by default:

    ```python
    s = df["column"].std()
    ```

    This default behaviour makes Pandas particularly convenient for statistical inference.

---

!!! info "Interested in the mathematical proof?"

    This chapter focuses on the intuition behind Bessel's correction.

    A rigorous proof requires concepts such as expectation,
    bias of estimators and properties of random variables,
    which are beyond the scope of this introductory guide.

    Readers interested in the mathematical derivation may consult
    standard textbooks on mathematical statistics such as

    - Casella & Berger — *Statistical Inference*.
    - Rice — *Mathematical Statistics and Data Analysis*.
    - Hogg, McKean & Craig — *Introduction to Mathematical Statistics*.

---

## Key takeaways

After completing this chapter, you should understand that

- the population standard deviation cannot usually be computed directly
- replacing the unknown population mean by the sample mean introduces a
  small systematic bias
- Bessel's correction compensates for this bias by dividing by

  \[
  n-1;
  \]

- one degree of freedom is used to estimate the sample mean
- the corrected sample standard deviation is therefore preferred for
  statistical inference

---

## Where to go next

The sample standard deviation provides an estimate of the unknown
population standard deviation.

But this raises another important question.

> **How does estimating the population variability affect the sampling distribution of the sample mean?**

Answering this question leads to the **Student's *t* distribution**,

which explains why many confidence intervals and hypothesis tests use a
*t* distribution instead of a Normal distribution when the population
standard deviation is unknown.
