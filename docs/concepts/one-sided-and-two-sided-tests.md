---
title: One-sided and two-sided tests
---

# One-sided and two-sided tests

← [Back to the statistical method navigator](../index.md)

---

## Quick answer

The direction of a hypothesis test is determined by the **alternative
hypothesis**.

Once the alternative hypothesis has been defined, everything else
follows naturally:

- the expected sign of the test statistic
- the rejection region
- whether the test is one-sided or two-sided
- the definition of *"more extreme"*
- the calculation of the p-value.

The rejection region should **not** be memorised.

Instead, it can usually be derived directly from the test statistic.

---

## Why does the direction of the test matter?

One of the most common sources of confusion in hypothesis testing is
deciding whether the rejection region is located in:

- the left tail
- the right tail
- both tails

Many students try to memorise these cases separately.

Fortunately, for a large family of statistical tests there is a much
simpler approach.

Instead of memorising the rejection region, derive it from the test
statistic.

---

## The common structure of many test statistics

Many classical hypothesis tests use a statistic having the following
general form:

\[
\text{Statistic}
=
\frac{
\text{Estimate}
-
\text{Null value}
}
{\text{Standard error}}
\]

Examples include:

- One-sample t-test
- Paired t-test
- Welch's t-test
- Two-proportions z-test
- Tests for regression coefficients

Although the exact formulas differ, they all share the same structure.

The numerator measures how far the estimate lies from the value assumed
under the null hypothesis.

The denominator expresses that difference in units of standard error.

Therefore:

> **The numerator determines the direction. The denominator determines
> the scale.**

The denominator is always positive whenever the statistic is defined.

Consequently, the sign of the statistic depends entirely on the
numerator.

This observation allows us to determine the rejection region without
memorising it.

---

## A systematic reasoning procedure

Whenever you encounter a new statistical test, follow these steps.

1. Write the alternative hypothesis.
2. Determine the expected sign of the numerator if the alternative
   hypothesis were true.
3. Deduce the sign of the statistic.
4. Identify the corresponding rejection region.

This reasoning works for many classical statistical tests and is often
much easier than memorising separate rules.

---

## Example 1 — Right-sided test

Suppose we wish to demonstrate that the mean of Population 1 is larger
than the mean of Population 2.

The hypotheses are

\[
H_0:\mu_1\le\mu_2
\]

\[
H_1:\mu_1>\mu_2
\]

A typical test statistic is

\[
T
=
\frac
{\bar x_1-\bar x_2}
{SE}
\]

If the alternative hypothesis is true, we expect

\[
\bar x_1-\bar x_2>0
\]

Since the denominator is positive,

\[
T>0
\]

Therefore, evidence against the null hypothesis accumulates in the
right-hand tail of the null distribution.

```text
                 H₀ : θ ≤ θ₀

Accept H₀                    Reject H₀
─────────────────────────────██████████
                      critical value
```

---

## Example 2 — Left-sided test

Suppose instead that the scientific claim is

\[
H_1:\mu_1<\mu_2
\]

The null hypothesis becomes

\[
H_0:\mu_1\ge\mu_2
\]

The same statistic is used:

\[
T
=
\frac
{\bar x_1-\bar x_2}
{SE}
\]

If the alternative hypothesis is true,

\[
\bar x_1-\bar x_2<0
\]

The denominator remains positive.

Therefore,

\[
T<0
\]

Evidence against the null hypothesis accumulates in the left-hand tail.

```text
                 H₀ : θ ≥ θ₀

Reject H₀                    Accept H₀
██████████─────────────────────────────
critical value
```

---

## Example 3 — Two-sided test

Suppose now that the research question is simply whether the two
population means differ.

The hypotheses are

\[
H_0:\mu_1=\mu_2
\]

\[
H_1:\mu_1\neq\mu_2
\]

If the alternative hypothesis is true,

the numerator may become

positive

or

negative.

Therefore,

the statistic may become

strongly positive

or

strongly negative.

Evidence against the null hypothesis can therefore accumulate in either
tail.

```text
                 H₀ : θ = θ₀

Reject      Accept H₀      Reject
██████──────────────────██████
```

Notice that the equality in the null hypothesis does not point towards
either direction.

Consequently, both tails become rejection regions.

---

## A quick way to reason about the rejection region

Whenever you encounter a new hypothesis test, start from the scientific
question.

Ask yourself:

> **If the alternative hypothesis were true, what values of the test
> statistic would I expect to observe?**

This question naturally leads to the rejection region.

The reasoning is always the same.

1. Start from the alternative hypothesis.
2. Determine the expected sign of the numerator.
3. Determine the expected sign of the statistic.
4. Locate those values on the null distribution.
5. Those values define the rejection region.

Notice that the reasoning always starts from the scientific claim
represented by the alternative hypothesis.

There is no need to think in terms of "the opposite of the null
hypothesis".

---

## When does this reasoning apply?

The reasoning presented in this document applies to a large family of
statistical tests whose statistic has the general form

\[
\frac{\text{Estimate}-\text{Null value}}
{\text{Standard error}}
\]

where the denominator is strictly positive whenever the statistic is
defined.

Typical examples include:

- One-sample t-test
- Paired t-test
- Welch's t-test
- Two-proportions z-test
- Tests for regression coefficients

For this family of tests:

- the numerator determines the direction;
- the denominator determines the scale.

Consequently, the expected sign of the statistic immediately identifies
the rejection region.

---

## Important exceptions

The reasoning described above is extremely useful, but it does **not**
apply to every statistical test.

It relies on the statistic having a sign.

Some statistical procedures instead use statistics that are always
non-negative.

Examples include:

- One-way ANOVA
- Two-way ANOVA
- Chi-square tests
- Likelihood-ratio tests

Typical statistics are

\[
F\ge0
\]

and

\[
\chi^2\ge0.
\]

Since these statistics cannot become negative, only **large positive
values** provide evidence against the null hypothesis.

Consequently, their rejection region is always located in the
right-hand tail.

This is why ANOVA and Chi-square tests do not have left-sided and
right-sided versions.

---

## Two equivalent ways to perform a hypothesis test

Once the rejection region has been identified, there are two completely
equivalent ways to perform the hypothesis test.

### Approach 1 — Critical values

Compute the test statistic and compare it with one or more critical
values (one critical value for each rejection region).

Reject the null hypothesis if the statistic falls inside the rejection
region.

This approach makes the rejection region explicit and is often the
easiest way to understand the logic of a hypothesis test.

---

### Approach 2 — p-values

Compute the probability of obtaining a value of the statistic at least as
extreme as the observed one, assuming that the null hypothesis is true.

Reject the null hypothesis whenever

\[
p<\alpha.
\]

Both approaches always produce exactly the same statistical decision.

They differ only in the way the decision is obtained.

Detailed explanations of these two approaches are provided in the
following concept pages:

- Critical values *(coming soon)*;
- P-values *(coming soon)*;
- Probability distributions *(coming soon)*;
- Cumulative distribution functions (CDF) *(coming soon)*;
- Percent point functions (PPF) *(coming soon)*.

---

## A useful memory trick

Once you have understood the reasoning above, there is an easy shortcut.

!!! tip "Memory trick"

    Start by looking at the **alternative hypothesis**. 

    Ask yourself:

    **If the alternative hypothesis were true, what sign should the test
    statistic have?**

    - A positive statistic corresponds to the **right-hand tail**.
    - A negative statistic corresponds to the **left-hand tail**.
    - If both positive and negative values support the alternative
      hypothesis, both tails become rejection regions.

    If you ever forget the result, you can verify it by checking the
    direction of the inequality in the alternative hypothesis and asking
    yourself which values of the statistic would provide evidence in its
    favour.

The rejection region is determined by the values of the statistic that
support the alternative hypothesis.

The "arrow trick" is simply a convenient shortcut once this reasoning has
been understood.

---

## Common misunderstandings

### "The rejection region has to be memorised."

Incorrect.

For many statistical tests it can be derived directly from the expected
sign of the statistic.

---

### "The direction of the test is chosen after looking at the data."

Incorrect.

The direction of the test is determined by the research question before
the data are analysed.

Changing the direction afterwards invalidates the interpretation of the
statistical test.

---

### "The null hypothesis determines the rejection region."

Not directly.

The scientific question determines the alternative hypothesis.

The alternative hypothesis determines the expected sign of the
statistic.

The expected sign determines the rejection region.

The null hypothesis simply describes the complementary parameter region.

---

### "Every statistical test has left-sided and right-sided versions."

Incorrect.

Some statistical tests use statistics that are always non-negative.

Those tests always reject in the right-hand tail.

---

## Practical workflow

Whenever you encounter a new hypothesis test:

1. Define the scientific question.
2. Formulate the alternative hypothesis.
3. Ask yourself:

   > **If the alternative hypothesis were true, what sign should the
   > statistic have?**

4. Identify where those values are located in the null distribution.
5. Compute the test statistic.
6. Make the statistical decision using either:
   - the critical-value approach;
   - the p-value approach.

---

## Take-home message

!!! success "Main idea"

    Start from the scientific question.

    The scientific question determines the alternative hypothesis.

    The alternative hypothesis tells you what values of the statistic
    support your claim.

    Those values define the rejection region.

    The "arrow trick" is simply a convenient shortcut once the reasoning
    has been understood.

---

## Related concepts

- [Statistical hypotheses](hypotheses.md)
- Probability distributions *(coming soon)*
- Critical values *(coming soon)*
- P-values *(coming soon)*
- Cumulative distribution functions (CDF) *(coming soon)*
- Percent point functions (PPF) *(coming soon)*

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)
- [One-way ANOVA](../tests/one-way-anova.md)
- [Two-way ANOVA](../tests/two-way-anova.md)

---

## References

- Casella, G., & Berger, R. L. (2002).
  *Statistical Inference* (2nd ed.). Duxbury.

- Lehmann, E. L., & Romano, J. P. (2005).
  *Testing Statistical Hypotheses* (3rd ed.). Springer.

- Rice, J. A. (2007).
  *Mathematical Statistics and Data Analysis* (3rd ed.). Cengage.
