---
title: Confidence intervals
---

# Confidence intervals

← [Back to the statistical method navigator](../index.md)

---

## Quick question

Hypothesis tests answer questions such as

> **Should the null hypothesis be rejected?**

However, a yes/no decision is not always enough.

A natural question is therefore:

> **Instead of making a yes/no decision, can we estimate the plausible
> values of the unknown population parameter?**

Confidence intervals answer this question.

---

## Why do we need confidence intervals?

Suppose we wish to estimate the average height of all students at a
university.

After collecting a random sample, we obtain

\[
\bar{x}=172.4\text{ cm}.
\]

where the bar over x, means the **sample mean**.

Should we conclude that the population mean is exactly

\[
\mu=172.4\text{ cm}?
\]

where $\mu$ represents the actual **population mean**. 

Probably not. In general, $\bar{x}\ne\mu$. In fact, the sample mean $\bar{x}$ will be off from the actual population mean $\mu$ by a certain random amount $\delta$. Thus, $\bar{x}=\mu+\delta$. Some samples will have a smaller delta, others bigger.

A different random sample will have different values. Therefore, a different sample would almost certainly produce a different
sample mean.

Therefore, the sample mean should not be interpreted as the exact value of the
population mean.

Instead, it should be viewed as an estimate.

---

## Point estimates are not enough

The sample mean

\[
\bar{x}=172.4
\]

is called a **point estimate** because it consists of a single value.

Point estimates are simple to compute, but they provide no information about their precision.

For example,

does

\[
172.4
\]

represent a very precise estimate?

Or could the true population mean reasonably be

- 172.3?
- 171.8?
- 174.5?

The point estimate alone cannot answer these questions.

---

## A natural question

At this point, an obvious question arises.

The population parameter is unknown.

If we do not know its true value, how can we possibly determine how far our estimate might be from it?

In other words,

> **How can we construct a plausible interval around an unknown
> parameter?**

At first sight, this may seem impossible.

The answer follows exactly the same philosophy used throughout
statistical inference.

We cannot study the unknown population parameter directly.

Instead, we study the behaviour of the **sample statistic**.

If we understand how the statistic varies from one random sample to
another, we can quantify the uncertainty associated with our estimate.

Everything we need has already been introduced.

We know that sample statistics follow probability distributions.

We also know how to obtain critical values from those distributions
using the **Percent Point Function (PPF)**.

Confidence intervals simply combine these ideas.

---

## From a single value to an interval

Rather than estimating the population parameter with a single number,

we estimate it using a range of plausible values.

For example, instead of reporting

\[
\mu=172.4,
\]

we might report

\[
171.8
\le
\mu
\le
173.0.
\]

This interval expresses the uncertainty associated with estimating the
population mean from a random sample.

Such an interval is called a **confidence interval**.

---

## Why is the interval necessary?

Every random sample produces

- a different sample mean
- a different estimate of the population parameter

Consequently, every random sample also produces a different confidence interval.

A confidence interval therefore reflects the uncertainty introduced by
random sampling.

!!! tip "A confidence interval is also random"

    The population parameter is fixed, although usually unknown.

    The confidence interval is **not** fixed.

    If we repeatedly collect new random samples, we obtain different
    **confidence intervals**.

    The randomness lies in the interval, not in the parameter.

---

## Accuracy and precision

When discussing statistical estimates,

it is useful to distinguish between **accuracy** and **precision**.

- **Accuracy** describes how close an estimate is to the true population
  parameter.
- **Precision** describes how much the estimate varies from one random
  sample to another.

The difficulty is that the true population parameter is unknown.

Therefore, we cannot directly measure the accuracy of our estimate.

What we can study is its precision.

Confidence intervals quantify this precision.

A narrow interval indicates a more precise estimate.

A wide interval indicates greater uncertainty.

!!! success "Confidence intervals estimate precision"

    The true population parameter is unknown.

    Therefore,

    we cannot measure how accurate our estimate is.

    What we can measure is how much the statistic varies from one random
    sample to another.

    Confidence intervals do **not** estimate the accuracy of the
    estimate.

    They quantify its **precision**.

---

## Confidence intervals and hypothesis tests

Confidence intervals and hypothesis tests answer different questions.

A hypothesis test asks

> **Is the observed evidence strong enough to reject the null
> hypothesis?**

A confidence interval asks

> **Which values of the population parameter are compatible with the
> observed data?**

Both approaches are based on exactly the same statistical ideas.

They simply present the information in different ways.

---

## A visual interpretation

Imagine that the horizontal line below represents all possible values of
the population mean.

```text
──────────────────────────────────────────────────────────────

        171.8                172.4                 173.0

───────────[====================●====================]───────────
                                ↑
                           Sample mean
```

The dot represents the point estimate.

The interval represents the range of plausible values for the unknown
population parameter.

Notice that the interval does **not** tell us how close the estimate is
to the true population parameter.

Instead, it tells us how precise the estimate is expected to be.

The wider the interval, the greater the uncertainty.

The narrower the interval, the more precise the estimate.

---

## What determines the width of a confidence interval?

Some confidence intervals are very narrow.

Others are much wider.

Why?

The answer depends on several factors,

including

- the variability of the data
- the sample size
- the chosen confidence level

Understanding how these factors determine the interval requires knowing

- how the sampling distribution behaves
- how the standard error measures its variability
- how critical values are obtained from a probability distribution

The next section brings together these ideas to show how confidence
intervals are actually constructed.

---

## How are confidence intervals constructed?

Everything we need has already been introduced.

We know that sample statistics follow probability distributions.

We also know how to obtain critical values from those distributions
using the **Percent Point Function (PPF)**.

Confidence intervals simply combine these ideas.

A confidence interval is built from three main elements:

- a **point estimate**
- the **sampling variability** of that estimate
- a **critical value** determined by the chosen confidence level

Its general form is

\[
\boxed{
\text{Estimate}
\pm
\text{Critical value}
\times
\text{Standard error}
}
\]

The quantity

\[
\text{Critical value}
\times
\text{Standard error}
\]

is called the **margin of error**.

Therefore,

\[
\boxed{
\text{Confidence interval}
=
\text{Estimate}
\pm
\text{Margin of error}
}
\]

---

## The sampling distribution

The population parameter is unknown.

However, the behaviour of the sample statistic can be described using its
**sampling distribution**.

Imagine repeatedly collecting independent random samples of the same
size from the population.

Each sample produces a different value of the statistic.

Those values form a sampling distribution.

For example,

```text
Sample #1  →  x̄ = 171.9

Sample #2  →  x̄ = 172.6

Sample #3  →  x̄ = 172.1

Sample #4  →  x̄ = 172.8

Sample #5  →  x̄ = 172.3

...
```

The sampling distribution tells us how much the statistic typically
varies from one random sample to another.

This variability is precisely what allows us to quantify the precision
of our estimate.

---

## The standard error

The spread of the sampling distribution is measured by the
**standard error**.

The standard error tells us how much a statistic typically varies from
one random sample to another.

A smaller standard error means that the statistic is more stable across
samples.

A larger standard error means that the statistic varies more.

For a sample mean, when the population standard deviation is unknown, the standard error is estimated as

\[
\boxed{
SE(\bar{x})
=
\frac{s}{\sqrt{n}}
}
\]

where

- \(s\) is the sample standard deviation
- \(n\) is the sample size

Notice an important consequence.

As the sample size increases, the standard error decreases.

This is one reason why larger samples generally produce more precise
estimates.

---

## Choosing a confidence level

Before constructing a confidence interval, we must choose a **confidence level**.

Common choices are

- 90%
- 95%
- 99%

The confidence level is directly related to the
[significance level](computing-p-values.md) used in hypothesis testing.

They are complementary quantities.

\[
\boxed{
\text{Confidence level}
=
1-\alpha
}
\]

For example,

| Confidence level | Significance level |
|------------------|-------------------:|
| 90% | 0.10 |
| 95% | 0.05 |
| 99% | 0.01 |

Thus,

a 95% confidence interval corresponds to

\[
\alpha=0.05.
\]

---

## Where does \(\alpha\) go?

For a two-sided confidence interval,

the total probability excluded from the interval is

\[
\alpha.
\]

Because the probability distribution is symmetric, this probability is divided equally between both tails.

Each tail therefore contains

\[
\frac{\alpha}{2}.
\]

For a 95% confidence interval,

\[
\alpha=0.05,
\]

so

\[
\frac{\alpha}{2}=0.025.
\]

```text
                 α/2                             α/2
            <---------|                     |---------->

────────────██████████|=====================|██████████────────────
                      │                     │
                   Lower                Upper
                  critical             critical
                    value                value

                       ←────── 1 − α ──────→
                        Confidence interval
```

---

!!! tip "The same critical values appear again"

    The critical values used to construct a confidence interval are
    exactly the same values used in a two-sided hypothesis test.

    The mathematics is identical.

    Only the interpretation changes.

---

## Which probability distribution should we use?

The critical values must always be obtained from the probability
distribution of the statistic being analysed.

In this example, we are estimating a population mean.

If the population standard deviation were known, the Normal distribution could be used.

However, in practice, the population standard deviation is almost always unknown.

Instead, it is estimated from the sample.

This introduces additional uncertainty.

For this reason, confidence intervals for a population mean are usually based on
**Student's *t* distribution**.

The exact shape of the distribution depends on the number of **degrees of freedom**.

For a one-sample mean,

\[
df=n-1.
\]

As the sample size increases, the additional uncertainty becomes smaller.

Consequently, the Student's *t* distribution gradually approaches the Normal distribution.

---

## Obtaining the critical value with the PPF

Suppose our sample contains

\[
n=25
\]

observations.

The number of degrees of freedom is therefore

\[
df=24.
\]

For a 95% confidence interval,

the upper cumulative probability is

\[
1-\frac{\alpha}{2}
=
1-\frac{0.05}{2}
=
0.975
\]

The corresponding critical value is obtained using the PPF.

```python
from scipy.stats import t

alpha = 0.05
df = 24

critical_value = t.ppf(1 - alpha / 2, df=df)
```

which returns approximately

```text
2.064
```

---

## Returning to our example

Suppose that our sample produced

\[
\bar{x}=172.4\text{ cm}
\]

with

\[
s=1.5\text{ cm}
\]

and

\[
n=25
\]

The estimated standard error is

\[
SE
=
\frac{1.5}{\sqrt{25}}
=
0.30
\]

The critical value is

\[
t_{c}=2.064
\]

The margin of error is therefore

\[
2.064\times0.30
=
0.619
\]

The confidence interval becomes

\[
172.4\pm0.619.
\]

or

\[
\boxed{
171.78
\le
\mu
\le
173.02
}
\]

---

## Computing the interval manually in Python

Exactly the same calculation can be reproduced step by step.

```python
from math import sqrt
from scipy.stats import t

mean = 172.4
sample_std = 1.5
n = 25
alpha = 0.05

df = n - 1

standard_error = sample_std / sqrt(n)

critical_value = t.ppf(
    1 - alpha / 2,
    df=df
)

margin_of_error = critical_value * standard_error

lower = mean - margin_of_error
upper = mean + margin_of_error

print(lower, upper)
```

Every step corresponds to a statistical concept.

```text
Random sample
      │
      ├── Sample mean (x̄)
      ├── Sample standard deviation (s)
      └── Sample size (n)
               │
               ▼
       Standard error
               │
Confidence level (1 − α)
               │
               ▼
             PPF
               │
               ▼
        Critical value
               │
               ▼
        Margin of error
               │
               ▼
      Confidence interval
```

Nothing in this calculation is a black box.

Every numerical value corresponds to a statistical concept introduced
previously.

---

!!! tip "Reporting statistical results"

    During the calculations,

    it is good practice to keep sufficient precision to avoid rounding
    errors.

    Final reported results, however, should be rounded to a sensible
    level of precision.

    A common convention is to round the **uncertainty** to **one
    significant figure**, or to **two significant figures if the first
    non-zero digit is 1**.

    The estimated value should then be rounded to the **same decimal
    position** as the uncertainty.

    | Before rounding | Reported result |
    |-----------------|-----------------|
    | \(172.4 \pm 0.619\) | \(172.4 \pm 0.6\) |
    | \(172.37 \pm 0.124\) | \(172.37 \pm 0.12\) |
    | \(173.2 \pm 12.8\) | \(173 \pm 13\) |

    Reporting unnecessary decimal places suggests a level of precision
    that the data do not support.

    The same principle applies when reporting p-values, confidence
    intervals and other statistical quantities.

---

## Verifying the calculation with SciPy

Once the calculation is understood,

a scientific library can perform exactly the same steps.

For example,

```python
from scipy.stats import t

interval = t.interval(
    confidence=0.95,
    df=df,
    loc=mean,
    scale=standard_error
)

print(interval)
```

The result is the same confidence interval obtained manually.

!!! tip "Understand first, automate second"

    Scientific libraries are extremely useful.

    However,

    they should automate calculations rather than replace
    understanding.

    Knowing how a confidence interval is constructed makes it easier to

    - verify the chosen probability distribution
    - check the degrees of freedom
    - confirm the critical value
    - detect incorrect assumptions
    - recognise implausible results

---

## What controls the width of the interval?

The confidence interval has the form

\[
\text{Estimate}
\pm
\text{Critical value}
\times
\text{Standard error}.
\]

Its width therefore depends mainly on two quantities:

- the critical value
- the standard error

Increasing the confidence level increases the critical value, producing a wider confidence interval.

Increasing the standard error also widens the interval.

Conversely, a smaller standard error produces a narrower and therefore more precise confidence interval.

Since

\[
SE(\bar{x})
=
\frac{s}{\sqrt{n}}
\]

increasing the sample size reduces the standard error.

This naturally raises another question.

> **Why does increasing the sample size make statistical estimates more stable?**

Answering this question leads to one of the fundamental results of
probability theory:

the **Law of Large Numbers (LLN)**.

---

## Summary: building a confidence interval

The construction of a confidence interval always follows the same logic.

| Step | Statistical concept |
|------|----------------------|
| 1 | Compute a **point estimate** from the sample |
| 2 | Estimate its **standard error** |
| 3 | Choose a **confidence level** |
| 4 | Obtain the corresponding **critical value** using the PPF |
| 5 | Compute the **margin of error** |
| 6 | Construct the confidence interval |

The complete process can be summarised as

```text
Random sample
      │
      ▼
Point estimate
      │
      ▼
Standard error
      │
      ▼
Confidence level (1 − α)
      │
      ▼
Critical value (PPF)
      │
      ▼
Margin of error
      │
      ▼
Confidence interval
```

Every confidence interval follows exactly the same reasoning.

The only differences are

- the statistic being estimated
- the probability distribution used
- the formula for the standard error

---

## Common misunderstandings

### "A 95% confidence interval contains the true parameter with probability 95%."

Not exactly.

After the sample has been collected, the confidence interval is fixed.

The population parameter is also fixed.

The parameter is either inside the interval or it is not.

The confidence level refers to the **procedure** used to construct the
interval.

If we repeatedly collected new random samples and computed a confidence
interval from each one, approximately **95%** of those intervals would contain the true
population parameter.

---

### "A confidence interval tells us how accurate our estimate is."

No.

The true population parameter is unknown.

Therefore, we cannot directly measure the accuracy of the estimate.

Confidence intervals quantify the **precision** of the estimation
procedure.

---

### "Confidence intervals and hypothesis tests are unrelated."

Incorrect.

Both are based on exactly the same statistical ideas.

They use

- the same sampling distribution
- the same critical values
- the same significance level

They simply answer different questions.

---

### "Confidence intervals always use the Normal distribution."

No.

The appropriate probability distribution depends on the statistic being analysed.

For example,

- one-sample means usually use Student's *t* distribution
- proportions often use the Normal approximation
- other statistical methods may use different probability distributions

---

## Take-home message

!!! success "Main idea"

    Confidence intervals estimate **plausible values** of an unknown
    population parameter.

    They are constructed by combining

    - a point estimate
    - its standard error
    - a critical value obtained from the appropriate probability
      distribution

    Confidence intervals do **not** measure the accuracy of an estimate.

    They quantify its **precision**.

---

We now know how confidence intervals are constructed.

One important question still remains.

>**Why do larger samples produce more reliable statistical estimates?**

The answer lies in one of the fundamental results of probability theory.

As the sample size increases, sample statistics become progressively more stable and converge towards
their corresponding population parameters.

This result is known as the **Law of Large Numbers (LLN).**

---

## Related concepts

- [Probability distributions](probability-distributions.md)
- [Computing probabilities with the CDF](computing-probabilities-with-cdf.md)
- [Computing critical values with the PPF](computing-critical-values-with-ppf.md)
- [Computing p-values](computing-p-values.md)
- Law of Large Numbers (LLN) *(coming soon)*

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)
