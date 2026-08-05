---
title: Probability distributions
---

# Probability distributions

← [Back to the statistical method navigator](../index.md)

---

## Quick answer

Every hypothesis test compares an observed statistic with the values that
would typically be expected if the null hypothesis were true.

Those expected values are described by a **probability distribution**.

Without a probability distribution, it is impossible to decide whether
an observed statistic is ordinary or unusually large.

---

## Why do hypothesis tests need probability distributions?

Suppose that two independent groups are compared using Welch's t-test.

After collecting the data, the **observed** test statistic is 

\[
T = 2.31.
\]

Is this value large?

Is it small?

Should the null hypothesis be rejected?

Large compared with what?

The value **2.31** alone does not answer these questions.

To interpret it, we must compare it with the values that would normally
be observed if the null hypothesis were true.

Those expected values are described by the null distribution of the
statistic.

---

## A statistic is also a random variable

A common misunderstanding is to think that the test statistic is just a
number.

It is not.

Before the data are collected, the observations themselves are random.

Consequently,

- the sample mean is random;
- the sample variance is random;
- the difference between two sample means is random;
- the test statistic is also random.

Each time a new sample is collected, the statistic takes a different
value.

Therefore, the statistic itself is a **random variable**.

Like every random variable, it has its own probability distribution.

Different statistics generally have different probability distributions.

---

## A simple example

Suppose the null hypothesis states

\[
H_0:\mu=100.
\]

Imagine repeatedly collecting independent random samples of the same
size from that population.

For each sample, compute the sample mean.

The sample mean will not always be exactly 100.

Instead, it will fluctuate around the population mean because of random
sampling variability.

A typical sequence of sample means might be

```text
Population mean = 100

Random sample #1  →  x̄ = 99.2

Random sample #2  →  x̄ = 101.7

Random sample #3  →  x̄ = 100.5

Random sample #4  →  x̄ = 98.9

Random sample #5  →  x̄ = 100.8

...
```

> None of these sample means is wrong.
>
> They are simply different outcomes of the same random sampling process.
>
> Consequently, a different random sample will generally produce a different value of the statistic.

If we repeat this process thousands of times, those sample means form a distribution.

This distribution is called the **sampling distribution of the sample mean.**

Many hypothesis tests are based on exactly the same idea.

The only difference is that the random variable is no longer the sample mean but another statistic, such as a t statistic, a z statistic, an F statistic or a χ² statistic.

The distinction between a population parameter and a sample statistic is fundamental to statistical inference.

| Population                       | Sample                      |
| -------------------------------- | --------------------------- |
| **Parameter**                    | **Statistic**               |
| Fixed (although usually unknown) | Random                      |
| One value                        | One observed value per random sample |

Statistical inference consists of using a random sample statistic to draw conclusions about a fixed but unknown population parameter.

---

## What is a probability distribution?

A probability distribution describes how likely different values of a
random variable are.

Some values are more likely than others. Some are common. Others are rare.

For hypothesis testing, the most important question is therefore:

> **How unusual is the observed statistic if the null hypothesis is
> true?**

Answering this question requires knowing the distribution of that
statistic under the null hypothesis.

This distribution is called the **null distribution**.

---

## The shape of a distribution

Different random variables produce different probability distributions.

Some are perfectly symmetric.

Others are positively skewed.

Some depend on one or more parameters.

Others have a fixed shape.

The shape of the distribution determines how unusual a given statistic
is.

For this reason, choosing the correct distribution is an essential part
of every hypothesis test.

Different hypothesis tests use different null distributions.

Choosing the appropriate distribution is therefore one of the key steps
when selecting a statistical method.

At this point, an important question naturally arises.

> **What do these probability distributions actually look like, and why
> do different hypothesis tests use different ones?**

The next section introduces the most common probability distributions
used in statistical inference and explains when each one appears.

---

## Common probability distributions

Different statistics produce different probability distributions.

For this reason, different hypothesis tests use different null
distributions.

The most common distributions encountered in statistical inference are:

- Normal distribution
- Student's *t* distribution
- Chi-square distribution
- F distribution

Each one has different properties and is used in different situations.

---

## Normal distribution

The Normal distribution is one of the most important probability
distributions in statistics.

It is:

- symmetric
- bell-shaped
- completely determined by its mean and standard deviation

Many statistics are approximately normally distributed when the sample
size is sufficiently large.

For this reason, the Normal distribution appears throughout statistical
inference.

Typical applications include:

- z-tests
- confidence intervals based on the Normal approximation
- the [Central Limit Theorem](central-limit-theorem.md) *(coming soon)*

---

## Student's *t* distribution

The Student's *t* distribution resembles the Normal distribution but has
heavier tails.

This reflects the additional uncertainty introduced when the population
variance is unknown and must be estimated from the sample.

The exact shape of the distribution depends on the **degrees of
freedom**.

As the degrees of freedom increase, the *t* distribution gradually
approaches the Normal distribution.

Typical applications include:

- One-sample t-test
- Paired t-test
- Welch's t-test
- Linear regression coefficients

---

## Chi-square distribution

Unlike the Normal and *t* distributions, the Chi-square distribution is
not symmetric.

It is defined only for non-negative values.

Its exact shape depends on the degrees of freedom.

With few degrees of freedom it is strongly positively skewed.

As the degrees of freedom increase, it becomes progressively more
symmetric.

Typical applications include:

- goodness-of-fit tests
- tests of independence
- tests involving variances

---

## F distribution

The F distribution is also defined only for non-negative values.

Like the Chi-square distribution, it is positively skewed.

Its shape depends on two independent sets of degrees of freedom.

Typical applications include:

- One-way ANOVA
- Two-way ANOVA
- comparison of nested regression models

---

## Degrees of freedom

Several probability distributions depend on one or more parameters known
as **degrees of freedom**.

Although their precise definition depends on the statistical procedure,
degrees of freedom generally represent the amount of independent
information available after estimating model parameters.

Changing the degrees of freedom changes the shape of the distribution. 

Different values of the degrees of freedom produce different versions of the same probability distribution.

For example:

- the Student's *t* distribution becomes closer to the Normal
  distribution
- the Chi-square distribution becomes less skewed
- the F distribution also changes shape

For this reason, the correct number of degrees of freedom must always be
used when performing a hypothesis test.

## Summary of the main probability distributions

The following table summarises the most important properties of the
probability distributions commonly encountered in statistical inference.

| Distribution | Symmetric | Possible values | Degrees of freedom | Typical applications | More details |
|--------------|:---------:|-----------------|:------------------:|----------------------|--------------|
| Normal | ✓ | \((-\infty,+\infty)\) | No | z-tests, Normal approximation | *(coming soon)* |
| Student's *t* | ✓ | \((-\infty,+\infty)\) | One | t-tests, regression coefficients | *(coming soon)* |
| Chi-square | ✗ | \([0,+\infty)\) | One | Goodness-of-fit, independence, variances | *(coming soon)* |
| F | ✗ | \([0,+\infty)\) | Two | ANOVA, nested models | *(coming soon)* |

---

## Which distribution does each statistical test use?

| Statistical method     | Null distribution |
| ---------------------- | ----------------- |
| One-sample t-test      | Student's *t*     |
| Paired t-test          | Student's *t*     |
| Welch's t-test         | Student's *t*     |
| Two-proportions z-test | Normal            |
| One-way ANOVA          | F                 |
| Two-way ANOVA          | F                 |
| Chi-square test        | Chi-square        |

Knowing which null distribution is associated with each statistical test
is an essential step in understanding how hypothesis testing works.

---

## Common misunderstandings

### "Every hypothesis test uses the Normal distribution."

Incorrect.

Different statistical tests use different null distributions.

---

### "The Normal distribution is always appropriate."

No.

The appropriate distribution depends on the statistic being analysed and
the assumptions of the statistical method.

---

### "Degrees of freedom are just another formula to memorise."

Not at all.

Degrees of freedom determine the shape of several probability
distributions.

They therefore influence the probabilities, critical values and
p-values obtained from those distributions.

---

## Take-home message

!!! success "Main idea"

    A hypothesis test does not only require a test statistic.

    It also requires the probability distribution of that statistic
    under the null hypothesis.

    Different statistical tests use different null distributions because
    they are based on different statistics.

---

We now know that every hypothesis test compares an observed statistic
with the distribution of values expected under the null hypothesis.

But how can we compute probabilities from that distribution?

The answer lies in the **cumulative distribution function (CDF)** and
its inverse, the **percent point function (PPF)**. These functions allow us to compute p-values, critical values and
confidence intervals from a probability distribution.

---

## Related concepts

- [Statistical hypotheses](hypotheses.md)
- [One-sided and two-sided tests](one-sided-and-two-sided-tests.md)
- Central Limit Theorem *(coming soon)*
- Cumulative distribution functions (CDF) *(coming soon)*
- Percent point functions (PPF) *(coming soon)*
- P-values *(coming soon)*

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)
- [One-way ANOVA](../tests/one-way-anova.md)
- [Two-way ANOVA](../tests/two-way-anova.md)
