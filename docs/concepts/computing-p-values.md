---
title: P-values
---

# P-values

← [Back to the statistical method navigator](../index.md)

---

## Quick question

After computing a test statistic, one important question remains.

> **Is the observed discrepancy between the sample and the null
> hypothesis unusually large, or could it simply be due to random
> sampling?**

The p-value provides a quantitative answer to this question.

---

## Why do we need a p-value?

Every hypothesis test follows the same general procedure.

First,

- a null hypothesis is formulated
- a significance level is chosen
- a test statistic is computed

However, calculating the test statistic does not, by itself, answer the
research question.

For example,

suppose that a statistical test produces

\[
T=2.31.
\]

Is this discrepancy large?

Is it small?

Should the null hypothesis be rejected?

The value **2.31** alone does not answer any of these questions.

To interpret it, we must compare it with what would normally be expected
if the null hypothesis were true.

The p-value provides exactly this comparison.

---

## Every test statistic measures a discrepancy

Although hypothesis tests use different formulas, they all measure the
same fundamental idea.

They quantify the discrepancy between

- what was observed in the sample
- what would be expected if the null hypothesis were true

For example,

- a one-sample *t* statistic measures how far the sample mean is from
  the hypothesised population mean
- Welch's *t* statistic measures the discrepancy between two sample
  means
- a two-proportions *z* statistic measures the discrepancy between two
  sample proportions;
- a Chi-square statistic measures the discrepancy between observed and
  expected frequencies.

The formulas are different.

The underlying idea is always the same.

---

## Measuring the size of the discrepancy

Most statistical tests compute a statistic of the form

\[
\boxed{
\frac{\text{Observed value}-\text{Expected value under }H_0}
{\text{Standard error}}
}
\]

The exact formula depends on the statistical method.

However, the interpretation is remarkably similar.

- the numerator measures **how large the discrepancy is**
- the denominator simply expresses that discrepancy on an appropriate
  scale

Once this quantity has been computed, the next question is no longer

> **How large is the discrepancy?**

Instead, it becomes

> **How likely is it to observe a discrepancy at least this large if the
> null hypothesis is true?**

---

## The definition of the p-value

The p-value answers exactly this question.

!!! success "The central idea"

    Every hypothesis test begins by measuring the discrepancy between
    the observed sample and what would be expected if the null hypothesis
    were true.

    The test statistic is the numerical quantity that measures this
    discrepancy.

    The p-value is therefore defined as

    \[
    p_{\text{value}}
    =
    P(\text{discrepancy or larger}\mid H_0=\text{ true})
    \]

    Since the test statistic is precisely the quantity used to measure
    the discrepancy, this is equivalent to

    \[
    p_{\text{value}}
    =
    P(\text{statistic or more extreme}\mid H_0=\text{ true})
    \]

    The expression **"more extreme"** depends on the alternative
    hypothesis and therefore on the rejection region.

---

## What does "more extreme" mean?

The meaning of **more extreme** depends on the statistical test being
performed.

For a right-tailed test,

larger statistics are more extreme.

```text
                       Observed statistic
                               │
               ________________│██████████
             /                 │███████████
___________/                   │████████████

             p-value
```

The p-value is therefore

\[
P(T\ge t_{\text{obs}}\mid H_0).
\]

---

For a left-tailed test,

smaller statistics are more extreme.

```text
             Observed statistic
                     │
██████████___________│____________________
█████████           /│
███████           /  │
_________________/___│____________________

       p-value
```

The p-value is

\[
P(T\le t_{\text{obs}}\mid H_0).
\]

---

For a two-sided test,

both tails correspond to increasingly large discrepancies.

```text
           Observed          Observed
           statistic         statistic
               │                 │
██████_________│_________________│________██████
█████          │                 │        █████
______________/                  \________________

        p-value / 2       p-value / 2
```

The p-value is therefore obtained by combining the probabilities in both
tails.

---

Some statistical tests, such as the [Chi-square test]*(coming soon)*, have only one
rejection region.

In those cases, **more extreme** simply means values further into that
single rejection region.

Therefore, the exact interpretation of **more extreme** always depends
on the rejection region defined by the statistical method.

---

## A useful observation

Notice that the p-value is always computed

- **assuming that the null hypothesis is true**
- using the probability distribution of the test statistic under the
  null hypothesis

This is why every hypothesis test requires a probability distribution.

Without it, the p-value cannot be computed.

---

At this point, an important question naturally arises.

Even if the p-value has been computed,

**how small must it be before we reject the null hypothesis?**

The answer requires introducing the **significance level**,
\(\alpha\).

---

## The significance level

The p-value tells us how unusual the observed discrepancy is under the
null hypothesis.

However, it does **not** tell us whether that probability is small
enough to reject the null hypothesis.

To make this decision, we need a reference value.

This reference value is called the **significance level**,

\[
\alpha.
\]

The significance level is chosen **before** analysing the data.

The statistical decision is then made by comparing the p-value with
\(\alpha\).

---

## Why must α be chosen in advance?

The significance level defines the criterion used to decide whether the
observed evidence against the null hypothesis is sufficiently strong.

If \(\alpha\) were chosen **after** computing the p-value, it would be
possible to adjust the decision rule until the desired conclusion was
obtained.

For this reason, the significance level must always be fixed **before**
looking at the data.

!!! warning "Choose α before analysing the data"

    The significance level must be specified before collecting or
    analysing the data.

    Changing \(\alpha\) after seeing the results introduces bias and
    invalidates the interpretation of the hypothesis test.

---

## Common choices for α

Several significance levels are commonly used in practice.

| Significance level | Typical use |
|-------------------:|-------------|
| 0.10 | Weak evidence required to reject \(H_0\) |
| 0.05 | Standard choice in many scientific disciplines |
| 0.01 | Stronger evidence required before rejecting \(H_0\) |

The value

\[
\alpha=0.05
\]

is by far the most common choice.

Sometimes stronger evidence is required before rejecting the null
hypothesis.

In such situations, a smaller significance level such as

\[
\alpha=0.01
\]

may be chosen.

The consequences of this choice will be discussed later in the section
on [Type I and Type II errors](#type-i-and-type-ii-errors).

---

## Making the statistical decision

Once both quantities have been obtained,

- the p-value
- the significance level

the decision is straightforward.

If

\[
p_{\text{value}}\le\alpha,
\]

the observed discrepancy is considered sufficiently unlikely under the
null hypothesis.

Therefore, we reject the null hypothesis.

Otherwise,

\[
p_{\text{value}}>\alpha,
\]

and we **fail to reject** the null hypothesis.

Notice that failing to reject the null hypothesis does **not mean that
it has been proved true.**

It simply means that the observed discrepancy is not sufficiently large
to reject it.

---

## Critical values and p-values are equivalent

Hypothesis tests can be solved in two equivalent ways.

- Compare the statistic with one or more critical values.
- Compare the p-value with the significance level.

Although these approaches appear different, they always produce exactly
the same statistical decision.

This is because the **CDF** and the **PPF** are inverse functions.

---

### Right-tailed test

```text
                              Critical value
                                     │
                 ____________________│██████████████
               /                     │███████████████
______________/______________________│████████████████
                      ▲
             Observed statistic

                      |------------------------------>
                               p-value

                                     |-------------->
                                           α
```

Since

\[
p_{\text{value}}=1-F(t_{\text{obs}}),
\]

and

\[
p_{\text{value}}>\alpha,
\]

the observed statistic does **not** belong to the rejection region.

Therefore,

we fail to reject the null hypothesis.

---

### Left-tailed test

```text
            Critical value

                 │
█████████████████│_____________________________
██████████████   │
█████████        │
_________________│________▲____________________
                         Observed statistic

<------------------------|

        p-value

<----------------|

      α
```

Since

\[
p_{\text{value}}=F(t_{\text{obs}}),
\]

and

\[
p_{\text{value}}>\alpha,
\]

the observed statistic again lies outside the rejection region.

Therefore,

we fail to reject the null hypothesis.

---

### Two-sided test

```text
 Lower critical                 Upper critical
      value                          value
        │                               │
████████│_______________________________│████████
███████ │                               │ ███████
________│________▲______________▲_______│________
          Symmetric             Observed
           statistic            statistic

<----------------|              |---------------->

 F(sym.)                     1 − F(obs.)

<-------|                               |------->

      α/2                                α/2

```

The p-value is obtained by adding both tail probabilities.

\[
p_{\text{value}}
=
F(t_{\text{sym}})
+
\left(1-F(t_{\text{obs}})\right)
\]

If the combined probability is larger than \(\alpha\),

the null hypothesis is not rejected.

---

Some statistical tests, such as the
[Chi-square test]*(coming soon)*,
have only one rejection region.

In those cases, **"more extreme"** simply means values further inside
that single rejection region.

---

## Equivalent acceptance conditions

The following table summarises the conditions under which the null
hypothesis is **not rejected**.

| Test | Acceptance condition using critical values | Acceptance condition using p-values |
|------|---------------------------------------------|-------------------------------------|
| Right-tailed | Statistic < critical value | \(p_{\text{value}}>\alpha\) |
| Left-tailed | Statistic > critical value | \(p_{\text{value}}>\alpha\) |
| Two-sided | Lower critical value ≤ statistic ≤ Upper critical value | \(p_{\text{value}}>\alpha\) |

Although the comparisons differ,

all three decision rules are completely equivalent.

---

## Computing p-values in Python

The CDF introduced in the previous chapter allows p-values to be
computed directly.

### Right-tailed test

```python
from scipy.stats import norm

p_value = 1 - norm.cdf(statistic)
```

---

### Left-tailed test

```python
from scipy.stats import norm

p_value = norm.cdf(statistic)
```

---

### Two-sided test

```python
from scipy.stats import norm

symmetric_statistic = -statistic

p_value = (
    norm.cdf(symmetric_statistic)
    + (1 - norm.cdf(statistic))
)
```

Exactly the same reasoning applies to other probability distributions.

Only the distribution changes.

For example,

```python
from scipy.stats import t

p_value = 1 - t.cdf(statistic, df)
```

uses the Student's *t* distribution instead of the Normal distribution.

Other scientific libraries may use different function names, but the
underlying mathematical idea is exactly the same.

---

!!! success "Key idea"

    The CDF computes p-values.

    The PPF computes critical values.

    Since the CDF and the PPF are inverse functions, both approaches
    always lead to exactly the same statistical decision.

---

## Why can the decision still be wrong?

The statistical decision is based on a random sample.

Different random samples generally produce different test statistics.

Consequently,

different random samples may lead to different statistical decisions,
even when they come from the same population.

For this reason,

a hypothesis test can never guarantee that the decision is correct.

There is always some probability of making an incorrect decision.

This leads to two possible types of error.

---

## Type I and Type II errors

Two situations are possible in reality.

- The null hypothesis is true.
- The null hypothesis is false.

Likewise,

there are two possible statistical decisions.

- Reject the null hypothesis.
- Fail to reject the null hypothesis.

Combining both possibilities produces four possible outcomes.

| **Reality** → <br>  **Statistical decision** ↓| **\(H_0\) is false** | **\(H_0\) is true** |
|-----------------------------------------------|:--------------------:|:-------------------:|
| **Reject \(H_0\)**                            | 🟩 Correct decision  | 🟥 **Type I error** |
| **Fail to reject \(H_0\)**                    | 🟨 **Type II error** | 🟩 Correct decision |

>Notice that the statistical decision is observable, whereas the true
>state of nature is not.

Consequently, after performing a hypothesis test we know **which
decision was made**, but we do not know whether that decision
corresponds to one of the green cells or to one of the error cells.

!!! tip "What makes hypothesis testing difficult?"

    The statistical decision is observable.

    The true state of nature is not.

    Consequently, after performing a hypothesis test we know **which
    decision was made**, but we do not know whether it corresponds to a
    correct decision or to one of the two possible errors.

    This uncertainty is an unavoidable consequence of statistical
    inference based on random samples.

---

### Type I error

A **Type I error** occurs when

- the null hypothesis is actually true
- but we reject it.

This is sometimes called a **false positive**.

The probability of making a Type I error is denoted by

\[
\alpha.
\]

This is exactly why the significance level must be chosen before
analysing the data.

---

### Type II error

A **Type II error** occurs when

- the null hypothesis is actually false
- but we fail to reject it.

This is sometimes called a **false negative**.

The probability of making a Type II error is usually denoted by

\[
\beta.
\]

Unlike \(\alpha\),

the value of \(\beta\) depends on many factors,

including

- the true effect size
- the sample size
- the variability of the data
- the chosen significance level.

---

## Can both errors be reduced simultaneously?

A natural question now arises.

> **Why not choose an extremely small significance level to avoid
> Type I errors?**

Unfortunately,

reducing one type of error generally increases the other.

Choosing a smaller significance level makes it harder to reject the null
hypothesis.

As a result,

- Type I errors become less frequent;
- Type II errors become more frequent.

Conversely, choosing a larger significance level makes rejecting the null hypothesis easier.

This decreases the probability of a Type II error, but increases the probability of a Type I error.

For this reason, selecting an appropriate significance level always involves balancing both risks.

---

!!! tip "There is no perfect significance level"

    No choice of \(\alpha\) completely eliminates statistical errors.

    Every hypothesis test involves a compromise between the probability
    of making a Type I error and the probability of making a Type II
    error.

    The most appropriate value depends on the practical consequences of
    each type of error.

---

## Take-home message

!!! success "Main idea"

    Every hypothesis test measures the discrepancy between the observed
    sample and what would be expected if the null hypothesis were true.

    The p-value quantifies how unusual that discrepancy is.

    The significance level determines how much evidence is required
    before rejecting the null hypothesis.

    Critical values and p-values are simply two equivalent ways of
    making exactly the same statistical decision.

    Because statistical decisions are based on random samples,

    there is always some probability of making an incorrect decision.

---

We now understand

- how a discrepancy is measured
- how a p-value is computed
- how a statistical decision is made
- why statistical decisions can sometimes be wrong

The next question is naturally

> **Instead of making a yes/no decision, can we estimate the range of
> plausible values for the unknown population parameter?**

Confidence intervals answer this question.

---

## Related concepts

- [Statistical hypotheses](hypotheses.md)
- [One-sided and two-sided tests](one-sided-and-two-sided-tests.md)
- [Probability distributions](probability-distributions.md)
- [Computing probabilities with the CDF](computing-probabilities-with-cdf.md)
- [Computing critical values with the PPF](computing-critical-values-with-ppf.md)

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)
- [Chi-square test]*(coming soon)*
