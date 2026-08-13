---
title: Statistical Power
---

# Statistical Power

← [Back to the statistical method navigator](../index.md)

---

## Quick question

Suppose that two populations are genuinely different.

If we perform a hypothesis test, will it always detect that difference?

Surprisingly, the answer is **no**.

Even when the alternative hypothesis is true, a statistical test may fail to detect the difference simply because the
sample does not contain enough information.

The probability of correctly detecting a real effect is called the **statistical power** of the test.

---

## What is statistical power?

Earlier we introduced the two possible errors in hypothesis testing.

- A **Type I error** occurs when we reject the null hypothesis even
  though it is true.

- A **Type II error** occurs when we fail to reject the null hypothesis
  even though it is false.

Statistical power is simply the probability of **avoiding a Type II
error**.

Equivalently,

\[
\boxed{
\text{Power}=1-\beta
}
\]

where

- \(\beta\) is the probability of committing a Type II error
- \(1-\beta\) is the probability of correctly rejecting the null
  hypothesis when it is false

The four possible outcomes of a hypothesis test can therefore be summarised as follows.

| **Reality** → <br> **Statistical decision** ↓ | **Positive** <br> (\(H_0\) false) | **Negative** <br> (\(H_0\) true) |
|-----------------------------------------------|:---------------------------------:|:--------------------------------:|
| **Reject \(H_0\)** | 🟩 **True Positive** = **Power** = \(1-\beta\) | 🟥 **False Positive** = **Type I error** = **Significance level** = \(\alpha\) |
| **Fail to reject \(H_0\)** | 🟥 **False Negative** = **Type II error** = \(\beta\) | 🟩 **True Negative** = **Correct decision** = \(1-\alpha\) |

!!! tip "Every outcome has a probability"

    Once the significance level

    \[
    \alpha
    \]

    has been chosen, each possible outcome has an associated probability. 

    - When the null hypothesis is true:

      - Reject \(H_0\): \(\alpha\)
      - Fail to reject \(H_0\): \(1-\alpha\)

    - When the null hypothesis is false:

      - Reject \(H_0\): \(1-\beta\) (Power)
      - Fail to reject \(H_0\): \(\beta\)

!!! note "Connection with binary classification"

    A hypothesis test can also be viewed as a binary classifier. 

    - The **positive** class corresponds to situations where the null
      hypothesis is false.
    - The **negative** class corresponds to situations where the null
      hypothesis is true.

    Under this interpretation:

    - Type I errors are **false positives**.
    - Type II errors are **false negatives**.
    - Statistical power is the **true positive rate**.

---

## An intuitive interpretation

Imagine that a new medical treatment really is more effective than the current one.

If a statistical test has a power of

\[
80\%,
\]

this does **not** mean that the treatment works 80% of the time.

Instead, it means that, if the treatment truly is more effective, the statistical test will correctly detect that improvement in about
80% of repeated studies.

In the remaining 20%, the test will fail to detect the difference even though it actually exists, leading to a Type II error.

---

!!! tip "Power measures the ability to detect real differences"

    A high statistical power means that,

    when a genuine effect exists,

    the statistical test is likely to detect it.

    Conversely,

    a low statistical power increases the probability of missing real
    effects.

---

## What determines statistical power?

Several factors influence the statistical power of a hypothesis test.

The most important are

- the sample size
- the magnitude of the true effect
- the variability of the data
- the chosen significance level \(\alpha\)

Understanding these relationships helps explain why some studies are
more likely than others to detect real effects.

---

### 1. Larger sample sizes

Increasing the sample size is one of the most effective ways to increase statistical power.

Why?

Earlier we learned that the Standard Error of the Mean decreases as the
sample size increases.

Consequently, the sampling distribution becomes narrower, making it easier to distinguish genuine differences from random variation.

This is one of the main reasons why larger studies are generally more likely to detect real effects.

---

### 2. Larger effect sizes

Some effects are easier to detect than others.

For example, a treatment that reduces blood pressure by

\[
20\ \mathrm{mmHg}
\]

is usually much easier to detect than one that reduces it by only

\[
2\ \mathrm{mmHg}.
\]

Larger differences produce larger test statistics, which in turn increase **the probability of rejecting the null hypothesis when it is false**.

---

### 3. Lower variability

Suppose that two studies compare exactly the same population means.

If one study contains highly variable observations, while the other contains observations that are much more consistent,
the second study will usually have greater statistical power.

Less variability produces more precise estimates, making genuine differences easier to detect.

---

### 4. A larger significance level

Increasing the significance level

\[
\alpha
\]

makes it easier to reject the null hypothesis.

Consequently, statistical power also increases.

However, this comes at an important cost.

A larger significance level also increases the probability of committing a Type I error.

Choosing

\[
\alpha
\]

therefore involves a trade-off between detecting real effects and avoiding false positives.

For this reason, the significance level should be chosen **before collecting or analysing the data**, not afterwards.

---

!!! warning "There is no free lunch"

    Increasing statistical power is desirable, but it often requires making compromises.

    For example, increasing the significance level raises statistical power, but also increases the probability of false positives.

    In practice, increasing the sample size is usually the preferred way to improve statistical power because it does not increase the Type I error rate.

    There is rarely a perfect solution.

    Every statistical decision involves a trade-off.

---

## A common misconception

A non-significant result does **not** necessarily mean that there is no effect.

It may simply indicate that the study had insufficient statistical power to detect it.

This is particularly common when the sample size is small.

For this reason, failure to reject the null hypothesis should never be interpreted as proof that the null hypothesis is true.

---

## Key takeaways

After completing this chapter, you should understand that

- statistical power is the probability of correctly rejecting a false
  null hypothesis
- statistical power is equal to \(1-\beta\)
- low statistical power increases the probability of Type II errors
- larger samples generally produce greater statistical power
- increasing \(\alpha\) increases statistical power, but also increases
  the probability of Type I errors

---

## Where to go next

A statistically significant result does not necessarily imply that the
observed effect is important in practice.

A very small effect may become statistically significant simply because
the sample size is very large.

This naturally raises another important question.

> **Is every statistically significant result practically meaningful?**

The next chapter introduces [**Statistical versus Practical Significance**]*(statistical-versus-practical-significance)*.
