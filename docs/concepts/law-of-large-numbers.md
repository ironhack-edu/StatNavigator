---
title: Law of Large Numbers (LLN)
---

# Law of Large Numbers (LLN)

← [Back to the statistical method navigator](../index.md)

---

## Quick question

In the previous chapter we saw that increasing the sample size produces
more precise confidence intervals.

But why?

Why do larger samples produce more reliable statistical estimates?

The answer lies in one of the most important results of probability
theory:

the **Law of Large Numbers (LLN).**

---

## Why do we need the Law of Large Numbers?

Many modern cars display the average fuel consumption since the last
reset.

Immediately after resetting the trip computer, the displayed average changes noticeably after almost every journey.

However, after several thousand kilometres, the average fuel consumption hardly changes at all.

Why?

The car is computing exactly the same statistic every time: the **sample mean**.

The only thing that changes is the number of observations used to compute it.

This behaviour is one of the main ideas behind the Law of Large Numbers.

---

## A natural question

At first sight, this behaviour may seem surprising.

If every new journey changes the average, why do those changes become smaller and smaller?

Do we simply become lucky as more observations are collected?

Or is there a mathematical reason?

The answer becomes much clearer if we look at how the sample mean is updated.

---

## Updating the sample mean

Suppose that we already know the sample mean computed from the first

\[
n-1
\]

observations.

A new observation,

\[
x_n,
\]

is then added to the sample.

The updated sample mean can be written as

\[
\boxed{
\bar{x}_n
=
\frac{n-1}{n}\bar{x}_{n-1}
+
\frac{x_n}{n}
}
\]

This formula shows that the new mean is a weighted average of

- the previous sample mean
- the new observation

However, it becomes even more informative if we rearrange it.

\[
\boxed{
\bar{x}_n
=
\bar{x}_{n-1}
+
\frac{x_n-\bar{x}_{n-1}}{n}
}
\]

---

## A useful interpretation

The second formula reveals something important.

The new sample mean is simply

- the previous sample mean

plus

- a small correction

That correction is

\[
\frac{x_n-\bar{x}_{n-1}}{n},
\]

which depends on how far the new observation is from the previous mean.

Notice what happens as the sample size increases.

The denominator,

\[
n,
\]

becomes larger and larger.

Consequently, each new observation has less influence on the updated mean. Only observations that differ substantially from the previous mean can produce noticeable changes.

!!! tip "Why does the sample mean become more stable?"

    Every new observation modifies the previous sample mean by

    \[
    \frac{x_n-\bar{x}_{n-1}}{n}.
    \]

    As the sample size increases, the factor \(1/n\) becomes progressively smaller.

    Consequently, individual observations generally have less influence on the sample
    mean, making large changes progressively less likely.

---

## A numerical example

Suppose that the current mean, based on the first four observations, is

\[
100.
\]

A fifth observation with value

\[
130
\]

is added.

The updated mean becomes

\[
100+\frac{(130-100)}{5}=106.
\]

The new observation noticeably changes the mean.

Now imagine that the current mean is still

\[
100,
\]

but it is based on the first 499 observations.

The 500th observation is again

\[
130.
\]

The updated mean becomes

\[
100+\frac{(130-100)}{500}=100.06.
\]

The same observation now has almost no effect.

Nothing about the new observation has changed.

Only the sample size has increased.

---

## An intuition, not a proof

The recursive formula explains why the sample mean becomes increasingly
stable as more observations are collected.

However, this is **not** the Law of Large Numbers itself.

The recursive formula is an algebraic identity.

It does not, by itself, guarantee convergence to the population mean.

That convergence is the probabilistic result established by the Law of
Large Numbers under appropriate conditions.

---

## From stability to convergence

A stable sample mean is useful.

But the Law of Large Numbers makes a much stronger statement.

It tells us that, under appropriate conditions, the sample mean not only becomes more stable, it also becomes increasingly likely to be close to the true population mean.

Intuitively, we may therefore think of large changes in the sample mean
as becoming progressively less likely as the sample size increases.

This idea is one of the foundations of statistical inference.

---

## The Law of Large Numbers

One intuitive way to represent the relationship between the sample mean
and the unknown population mean is

\[
\boxed{
\mu
=
\bar{x}
+
\delta
}
\]

where

- \(\mu\) is the population mean
- \(\bar{x}\) is the sample mean
- \(\delta=\mu-\bar{x}\) is the estimation error

!!! note "The sign of the estimation error"

    Here we define

    \[
    \delta=\mu-\bar{x},
    \]

    so that

    \[
    \mu=\bar{x}+\delta.
    \]

    We could define the discrepancy in the opposite direction instead.

    Its sign would change, but the underlying idea would not: \(\delta\)
    represents the difference between the sample estimate and the
    population parameter.

    When discussing the size of the estimation error, what matters is
    \(|\delta|\).

The Law of Large Numbers tells us that, under appropriate conditions,
this estimation error becomes **increasingly likely to be small as the
sample size increases**.

In other words, larger samples tend to produce estimates that are closer to the true
population parameter.

---

## Why does the estimation error become smaller?

Earlier we rewrote the recursive formula for the sample mean as

\[
\boxed{
\bar{x}_n
=
\bar{x}_{n-1}
+
\frac{x_n-\bar{x}_{n-1}}{n}
}
\]

The second term represents the correction introduced by the new
observation.

Notice two important facts.

First, the correction depends on how different the new observation is from the
previous sample mean.

Second, the correction is divided by

\[
n.
\]

As the sample size increases, this denominator becomes larger.

Consequently, each new observation has less influence on the updated mean.

Only observations that differ substantially from the previous mean can
produce noticeable changes.

Intuitively, we may therefore think of **large estimation errors**
becoming progressively less likely as the sample size increases.

---

!!! tip "The connection with confidence intervals"

    In the previous chapter we wrote a confidence interval as

    \[
    \text{Estimate}
    \pm
    \text{Margin of error}.
    \]

    Here,

    we write

    \[
    \mu
    =
    \bar{x}
    +
    \delta.
    \]

    Both expressions describe exactly the same idea.

    The sample mean is only an estimate of the unknown population mean.

    The difference between them is an estimation error.

    The Law of Large Numbers explains why large estimation errors become
    progressively less likely as more observations are collected.

---

## What does "converges" mean?

The Law of Large Numbers is often summarised by writing

\[
\bar{x}
\longrightarrow
\mu
\qquad
\text{as }
n
\longrightarrow
\infty.
\]

This does **not** mean that the sample mean eventually becomes exactly
equal to the population mean.

Random samples always contain random variation.

Therefore, the sample mean continues to fluctuate, **even for very large samples**.

However, large fluctuations become progressively less likely as the
sample size increases.

As a consequence, the sample mean becomes increasingly likely to remain close to the true
population mean.

!!! tip "A useful way to think about the Law of Large Numbers"

    The relationship

    \[
    \mu=\bar{x}+\delta
    \]

    provides a simple mental model.

    - The sample mean is an estimate of the unknown population mean.
    - \(\delta\) represents the estimation error.
    - As the sample size increases, large values of \(|\delta|\) become
      progressively less likely.

    The sample mean does not become exactly equal to the population mean.

    Instead, it becomes increasingly likely to differ from it by only a small
    amount.

!!! tip "The Law of Large Numbers is probabilistic"

    The Law of Large Numbers does **not** guarantee that every large
    sample produces an accurate estimate.

    Unusual samples are always possible.

    Instead,

    it tells us that larger samples are increasingly likely to produce
    estimates close to the true population parameter.

---

## Why is this important?

The Law of Large Numbers explains why statistical estimation is
possible.

If the sample mean did **not** converge towards the population mean, collecting more observations would not systematically improve our estimate of that parameter.

Statistical estimation based on sample means would therefore lose one of its fundamental guarantees.

Fortunately, the opposite is true.

Larger samples make large estimation errors progressively less likely, producing more stable and reliable estimates.

---

## Consistent estimators

The sample mean is an example of a **consistent estimator**.

An estimator is said to be consistent if it converges towards the true
population parameter as the sample size increases.

Many of the estimators used throughout statistics share this property.

This is one of the main reasons why increasing the sample size improves
statistical inference.

---

## Returning to the car example

Conceptually, the average fuel consumption displayed by the trip
computer behaves like a sample mean: as more data are accumulated, each
additional journey has less influence on the overall estimate.

Immediately after resetting the trip computer, every new journey noticeably changes the displayed average.

After thousands of kilometres, the same journey has almost no visible effect.

The average fuel consumption has not stopped changing.

Instead, large changes in the estimated mean have become progressively
less likely as more observations have been accumulated.

The Law of Large Numbers explains **why** larger samples tend to produce
more reliable estimates.

A different question still remains.

>**How are those estimates distributed from sample to sample?**

Answering that question leads to the next fundamental result of
probability theory:

the [Central Limit Theorem (CLT)](central-limit-theorem.md).
