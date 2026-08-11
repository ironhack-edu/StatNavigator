---
title: Central Limit Theorem (CLT)
---

# Central Limit Theorem (CLT)

← [Back to the statistical method navigator](../index.md)

---

## Quick question

In the previous chapter we learned that the **Law of Large Numbers
(LLN)** explains why larger samples tend to produce more reliable
statistical estimates.

However,

another important question naturally arises.

> **What probability distribution does the sample mean follow?**

The answer is provided by one of the most important results in
probability theory:

the **Central Limit Theorem (CLT).**

---

## Why do we need the Central Limit Theorem?

The Law of Large Numbers tells us that the sample mean becomes
increasingly close to the population mean as the sample size increases.

However, it tells us nothing about the **distribution** of the sample mean.

Suppose we repeatedly collect random samples of the same size.

Each sample produces a different sample mean.

Some sample means are slightly larger.

Others are slightly smaller.

A natural question therefore arises.

> **How are those sample means distributed?**

Understanding this sampling distribution is essential because statistical
inference relies on probability distributions.

Without knowing the distribution of the sample mean, we could not compute

- p-values
- confidence intervals
- critical values

---

## From one sample to many samples

Imagine repeatedly collecting independent random samples from the same
population.

```text
Population
      │
      ├────────► Sample 1 ─────► x̄₁
      │
      ├────────► Sample 2 ─────► x̄₂
      │
      ├────────► Sample 3 ─────► x̄₃
      │
      ├────────► Sample 4 ─────► x̄₄
      │
      └────────► ...
```

Instead of looking at the individual observations,

we now look only at the sample means.

Those sample means themselves form a new probability distribution.

This distribution is called the **sampling distribution of the sample
mean**.

---

## A surprising result

At first sight, there is no obvious reason why the sampling distribution should have any particular shape.

After all, the original population could have almost any distribution.

It might be

- symmetric
- skewed
- bimodal
- irregular

One might therefore expect the sampling distribution to be equally irregular.

Surprisingly, this is not what happens.

As the sample size increases, the sampling distribution of the sample mean becomes increasingly close
to a **Normal distribution**.

This remarkable result is known as the **Central Limit Theorem**.

---

## The Central Limit Theorem

The Central Limit Theorem states that, under appropriate conditions, the **sampling distribution of the sample mean** approaches a Normal
distribution as the sample size increases, **regardless of the shape of the original population distribution**.

In other words,

\[
\boxed{
\bar{X}
\approx
N
\left(
\mu,
\frac{\sigma}{\sqrt{n}}
\right)
}
\]

for sufficiently large sample sizes.

Several important ideas appear in this expression.

- The centre of the distribution is the population mean
- Its spread is determined by the standard error
- The approximation improves as the sample size increases

---

!!! tip "The CLT is about the sampling distribution"

    The Central Limit Theorem does **not** state that the population is
    Normally distributed.

    It states that the **sampling distribution of the sample mean**
    becomes approximately Normal as the sample size increases.

This distinction is one of the most important ideas in statistics.

!!! tip "Is a sample size of 30 always enough?"

    A common rule of thumb is that the Central Limit Theorem provides a
    good Normal approximation when

    \[
    n \ge 30.
    \]

    However,

    this is **not** a mathematical requirement.

    If the population is already Normally distributed, the sampling distribution of the sample mean is Normal for **any**
    sample size.

    On the other hand, highly skewed or heavy-tailed populations may require considerably
    larger samples before the Normal approximation becomes accurate.

    The required sample size therefore depends on the underlying
    population distribution.

---

## The relationship with the Law of Large Numbers

The Law of Large Numbers and the Central Limit Theorem are closely
related, but they answer different questions.

| Law of Large Numbers | Central Limit Theorem |
|----------------------|-----------------------|
| Where does the sample mean go? | What distribution does the sample mean follow? |
| The sample mean converges towards the population mean. | The sampling distribution becomes approximately Normal. |

!!! note "Why doesn't the CLT always use the Normal distribution?"

    The Central Limit Theorem describes the sampling distribution of the
    sample mean.

    In practice, however, the population standard deviation is almost never known.

    It must therefore be **estimated** from the sample.

    Estimating this quantity **introduces additional uncertainty**.

    This is why many confidence intervals and hypothesis tests use
    Student's *t* distribution instead of the Normal distribution.

    The relationship between the Normal and Student's *t*
    distributions will be explored in more detail later.

The two results complement one another.

The Law of Large Numbers explains **why** larger samples produce more
stable estimates.

The Central Limit Theorem explains **how those estimates are
distributed**.

---

## Why is the Central Limit Theorem so important?

The Central Limit Theorem is one of the cornerstones of modern
statistics.

Without it, many of the statistical methods presented throughout this guide would
not be possible.

Why?

Because almost every inferential procedure requires knowing the
probability distribution of the statistic being analysed.

The CLT provides exactly that information for the sample mean.

---

## The sampling distribution

The sampling distribution is often confused with the original population
distribution.

However, they are completely different concepts.

The **population distribution** describes the values of individual
observations.

The **sampling distribution** describes the values of a statistic
computed from many independent samples.

For the sample mean, the process looks like this:

```text
Population
      │
      ├────────► Sample 1 ─────► x̄₁
      │
      ├────────► Sample 2 ─────► x̄₂
      │
      ├────────► Sample 3 ─────► x̄₃
      │
      └────────► ...
                      │
                      ▼
        Sampling distribution of x̄
```

The Central Limit Theorem tells us that,

for sufficiently large samples,

this final distribution becomes approximately Normal.

---

## The role of the standard error

The **sampling distribution** is centred on the population mean,

\[
\mu.
\]

However, its spread is **not** determined by the population standard deviation,

\[
\sigma.
\]

Instead, it is determined by the **standard error**,

\[
SE=\frac{\sigma}{\sqrt{n}}.
\]

This simple expression has an important consequence.

As the sample size increases, the standard error decreases.

Therefore, the sampling distribution becomes progressively narrower.

```text
Small sample (large SE)

              ███████████████

Large sample (small SE)

                 ███████
```

This explains why larger samples generally produce more precise estimates.

Notice how the Law of Large Numbers and the Central Limit Theorem now
work together.

- The Law of Large Numbers explains why the sample mean tends to be
  close to the population mean.

- The Central Limit Theorem explains why the sampling distribution
  becomes increasingly concentrated around that mean.

---

!!! tip "Three different measures of variability"

    Statistics uses three closely related quantities that are often
    confused.

    | Quantity | Symbol | What does it measure? |
    |----------|--------|-----------------------|
    | **Population standard deviation** | \(\sigma\) | The variability of the **entire population**. |
    | **Sample standard deviation** | \(s\) | An estimate of the unknown population standard deviation **computed from a sample**. |
    | **Standard error (SE)** | \(SE=\sigma/\sqrt{n}\) (or approximately \(s/\sqrt{n}\)) | The variability of the **sample mean** from one **sample to another**. |

    The first two describe the variability of **individual observations**.

    The standard error describes the variability of the **sample mean**.

    These quantities answer different questions and **should not be used interchangeably**.

---

## Why does this matter?

Suppose that we compute a **sample mean**.

By itself, that value tells us very little. Is it unusually large? Is it unusually small? How much different is it from the **population mean?**

Or is it exactly what we would expect by random chance?

To answer those questions, we need to compare the observed **sample mean with its expected sampling distribution**.

The Central Limit Theorem tells us that this distribution is approximately Normal.

Consequently, we can compute

- probabilities using the
  [Cumulative Distribution Function (CDF)](computing-probabilities-with-cdf.md);
- critical values using the
  [Percent Point Function (PPF)](computing-critical-values-with-ppf.md);
- p-values using
  [Computing P-values](computing-p-values.md);
- confidence intervals using
  [Computing confidence intervals](computing-confidence-intervals.md).

Without the Central Limit Theorem, these calculations would not generally be possible.

---

## A practical example

Suppose that the true **population mean** is

\[
\mu = 100,
\]

and the **population standard deviation** is

\[
\sigma = 20.
\]

Random samples of size

\[
n=100
\]

are repeatedly collected.

According to the Central Limit Theorem, the sampling distribution of the sample mean is approximately

\[
N
\left(
100,
\frac{20}{\sqrt{100}}
\right)
=
N(100,2).
\]

Notice what happened.

The **individual observations** still vary with a standard deviation of

\[
\sigma=20,
\]

but the **sample means** vary much less.

Their **standard error** is only

\[
\frac{\sigma}{\sqrt{n}}=\frac{20}{\sqrt{100}}=2.
\]

This reduction in variability is precisely what makes statistical
inference possible.

---

## Verifying the theorem with Python

The Central Limit Theorem can easily be explored through simulation.

The basic idea is simple.

1. Generate a population with any distribution.
2. Draw many independent random samples.
3. Compute the sample mean for each sample.
4. Plot the resulting sampling distribution.

Even if the original population is strongly skewed,

the sampling distribution of the sample mean becomes increasingly
Normal as the sample size grows.

The following example illustrates this behaviour.

---

## Simulating the Central Limit Theorem with Python

The Central Limit Theorem is particularly well suited to computer
simulation.

The idea is simple.

1. Generate a population with any probability distribution.
2. Draw many independent random samples of the same size.
3. Compute the sample mean for each sample.
4. Plot the distribution of those sample means.

Even if the original population is far from Normal, the sampling distribution of the sample mean becomes increasingly Normal
as the sample size grows.

The following example uses an exponential distribution, which is highly right-skewed.

```python
import numpy as np
import matplotlib.pyplot as plt

# Reproducibility
rng = np.random.default_rng(seed=42)

# Population parameters
sample_size = 30
num_samples = 10000

# Draw many samples from a skewed distribution
samples = rng.exponential(scale=1.0,
                          size=(num_samples, sample_size))

# Compute the sample mean of each sample
sample_means = samples.mean(axis=1)

# Plot the sampling distribution
plt.hist(sample_means,
         bins=40,
         density=True,
         edgecolor="black")

plt.xlabel("Sample mean")
plt.ylabel("Density")
plt.title("Sampling distribution of the sample mean")
plt.show()
```

The resulting histogram is approximately bell-shaped, despite the original exponential population being strongly skewed.

Increasing the sample size makes the Normal approximation even better.

---

## Common misconceptions

The Central Limit Theorem is often misunderstood.

It does **not** state that

- every dataset is Normally distributed
- every population is Normally distributed
- a sample size of exactly 30 is always sufficient
- individual observations become Normally distributed

Instead, it states that the **sampling distribution of the sample mean** approaches a Normal distribution under appropriate conditions.

---

!!! warning "The CLT applies to sample means"

    The Central Limit Theorem describes the behaviour of the **sample
    mean**, not the original observations.

    Individual observations remain distributed according to the original population.

    Only the **sampling distribution** of the statistic becomes approximately Normal.

---

## Summary

The Central Limit Theorem explains why the sample mean has such a central role in statistics.

It tells us that

- repeated samples produce different sample means
- those sample means form a sampling distribution
- for sufficiently large sample sizes, that sampling distribution is approximately Normal
- the spread of that distribution is determined by the standard error

Together with the Law of Large Numbers, the Central Limit Theorem provides the mathematical foundation for much
of statistical inference.

---

## LLN and CLT at a glance

| Law of Large Numbers (LLN) | Central Limit Theorem (CLT) |
|----------------------------|-----------------------------|
| Explains where the sample mean goes. | Explains how the sample mean is distributed. |
| The sample mean approaches the population mean. | The sampling distribution approaches a Normal distribution. |
| Concerned with convergence. | Concerned with the shape of the sampling distribution. |
| Explains why estimates become more reliable. | Explains why Normal-based inference is possible. |

These two results complement each other.

The Law of Large Numbers explains why larger samples produce increasingly reliable estimates.

The Central Limit Theorem explains why those estimates can be analysed using the Normal distribution.

---

## Where to go next

The Central Limit Theorem explains why the sampling distribution of the sample mean becomes approximately Normal.

However, many statistical methods require knowing **how much variability** to
expect **from one sample mean to another**.

This variability is quantified by the **standard error**, which plays a
central role in confidence intervals and hypothesis tests.

To understand how this quantity is computed and interpreted, see

[Standard error]*(standard-error.md)*.
