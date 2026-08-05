---
- Two-way ANOVA
title: Statistical hypotheses
---

# Statistical hypotheses

← [Back to the statistical method navigator](../index.md)

---

## Quick answer

A statistical hypothesis test compares two competing statements about a
population parameter:

- the **null hypothesis**, \(H_0\);
- the **alternative hypothesis**, \(H_1\).

The alternative hypothesis **should normally contain the scientific claim
that we want the data to support**.

A classical hypothesis test can provide evidence in favour of \(H_1\) by
rejecting \(H_0\).

It cannot prove that \(H_0\) is true.

---

## What is a statistical hypothesis?

A statistical hypothesis is a statement about an unknown population
quantity.

Examples include:

\[
\mu = 100
\]

\[
p_1 = p_2
\]

\[
\mu_1-\mu_2 > 5
\]

\[
p_{Test}-p_{Control} > 0.03
\]

These statements concern population parameters such as:

- a population mean
- a population proportion
- a difference between means
- a difference between proportions
- a regression coefficient
- an association between variables

Because population parameters are usually unknown, we use sample data to
evaluate whether the observed evidence is compatible with a proposed
hypothesis.

---

## Null and alternative hypotheses

A hypothesis test starts with two competing statements.

### Null hypothesis

The null hypothesis is written as:

\[
H_0
\]

It represents the set of parameter values that the test attempts to
challenge.

Typical examples are:

\[
H_0:\mu=\mu_0
\]

\[
H_0:\mu_1-\mu_2=0
\]

\[
H_0:p_1-p_2\leq0.03
\]

### Alternative hypothesis

The alternative hypothesis is written as:

\[
H_1
\]

or sometimes:

\[
H_A
\]

It represents the claim for which we want to obtain evidence.

Examples are:

\[
H_1:\mu\neq\mu_0
\]

\[
H_1:\mu_1-\mu_2>0
\]

\[
H_1:p_1-p_2>0.03
\]

---

## Put the claim you want to support in \(H_1\)

A useful general rule is:

> Put in \(H_1\) the scientific or practical claim that you want the data
> to support.

Suppose a company wants to demonstrate that a new website increases the
completion rate by more than three percentage points.

The claim of interest is:

\[
p_{Test}-p_{Control}>0.03
\]

Therefore:

\[
H_1:p_{Test}-p_{Control}>0.03
\]

and the null hypothesis is:

\[
H_0:p_{Test}-p_{Control}\leq0.03
\]

If the data provide sufficiently strong evidence against \(H_0\), we may
reject it and conclude that the improvement is greater than three
percentage points.

---

## Why not place the desired claim in \(H_0\)?

Suppose instead that we write:

\[
H_0:p_{Test}-p_{Control}>0.03
\]

and obtain:

\[
p=0.80
\]

Can we conclude that the new website improves the completion rate by more
than three percentage points?

No.

A large p-value means only that we have not found enough evidence against
\(H_0\).

It does not mean that \(H_0\) has been demonstrated.

The correct conclusion is:

> The data do not provide sufficient evidence to reject the hypothesis
> that the difference exceeds three percentage points.

This is not equivalent to saying:

> The difference has been proven to exceed three percentage points.

---

## Rejecting and failing to reject

A classical hypothesis test produces one of two decisions.

### Reject \(H_0\)

If the result is sufficiently incompatible with \(H_0\), we reject the
null hypothesis.

For example:

\[
p_{value}<\alpha
\]

may lead us to reject \(H_0\).

The p-value measures how unusual the observed test statistic, or a more
extreme one, would be if \(H_0\) and the assumptions of the statistical
model were true.

See P-values *(coming soon)* for a detailed explanation.

The conclusion is:

> The data provide evidence in favour of \(H_1\).

This does not imply absolute certainty.

A hypothesis test controls the probability of certain errors; it does not
produce a mathematical proof.

### Fail to reject \(H_0\)

If the evidence is not sufficiently strong, we fail to reject \(H_0\).

For example:

\[
p_{value}\geq\alpha
\]

The conclusion is:

> The data do not provide sufficient evidence against \(H_0\).

Do not write:

> We accept \(H_0\).

Do not write:

> We have proved that \(H_0\) is true.

A non-significant result may occur because:

- \(H_0\) is approximately true
- the sample is too small
- the data are highly variable
- the measurement is imprecise
- the test has low statistical power
- several parameter values remain compatible with the data

---

## The criminal-trial analogy

A criminal trial provides a useful analogy for the asymmetry between
\(H_0\) and \(H_1\).

Suppose:

\[
H_0:\text{The defendant is not guilty}
\]

\[
H_1:\text{The defendant is guilty}
\]

The prosecution must provide enough evidence to reject the presumption
represented by \(H_0\).

### Strong evidence

If the evidence is sufficiently strong, the court may reject \(H_0\) and
return a guilty verdict.

This does not mean that guilt has been established with absolute
mathematical certainty.

It means that the evidence exceeded the required standard.

### Insufficient evidence

If the evidence is insufficient, the verdict is:

> Not guilty.

The verdict is not:

> Proven innocent.

The court has failed to find enough evidence to reject the initial
presumption.

Similarly, failing to reject a statistical null hypothesis does not prove
that it is true.

!!! note "Important limitation of the analogy"

    Statistical hypothesis testing and legal trials are not identical.

    The analogy is useful only for understanding the asymmetric burden of
    evidence: evidence is required to reject the initial hypothesis, while
    failure to reject it is not proof that it is true.

---

## Why do we begin by assuming \(H_0\)?

A hypothesis test temporarily assumes that \(H_0\) is true.

It then asks:

> If \(H_0\) were true, how unusual would the observed result be?

The reasoning is:

1. assume \(H_0\)
2. determine the sampling distribution expected under \(H_0\)
3. calculate a test statistic from the observed data
4. measure how extreme the statistic is under \(H_0\)
5. reject \(H_0\) if the result is sufficiently incompatible with it

This resembles reasoning by contradiction:

- assume a statement
- derive its implications
- reject the assumption if the observed consequences are highly
  inconsistent with it

However, a hypothesis test is probabilistic rather than a formal
mathematical proof.

---

## Equality and directional hypotheses

### Two-sided test

Use a two-sided alternative when differences in either direction matter.

\[
H_0:\theta=\theta_0
\]

\[
H_1:\theta\neq\theta_0
\]

Examples:

\[
H_0:\mu_1-\mu_2=0
\]

\[
H_1:\mu_1-\mu_2\neq0
\]

The rejection region is distributed across both tails of the null
distribution.

---

### Right-sided test

Use a right-sided alternative when the scientific claim is that the
parameter is greater than a boundary.

\[
H_0:\theta\leq\theta_0
\]

\[
H_1:\theta>\theta_0
\]

Example:

\[
H_0:p_{Test}-p_{Control}\leq0.03
\]

\[
H_1:p_{Test}-p_{Control}>0.03
\]

The rejection region is in the right tail.

---

### Left-sided test

Use a left-sided alternative when the scientific claim is that the
parameter is smaller than a boundary.

\[
H_0:\theta\geq\theta_0
\]

\[
H_1:\theta<\theta_0
\]

Example:

\[
H_0:\mu_{New}-\mu_{Current}\geq0
\]

\[
H_1:\mu_{New}-\mu_{Current}<0
\]

The rejection region is in the left tail.

The alternative hypothesis determines which part of the null distribution
is considered evidence against \(H_0\).

See
One-sided and two-sided tests *(coming soon)*
for diagrams of the rejection regions and an explanation of how
directionality affects the p-value.

---

## The equality belongs to the null hypothesis

The boundary value is normally included in \(H_0\).

For example:

\[
H_0:\theta\leq\theta_0
\]

rather than:

\[
H_0:\theta<\theta_0
\]

The test statistic and p-value are usually calculated at the boundary:

\[
\theta=\theta_0
\]

This boundary represents the case that is most difficult to distinguish
from the alternative while still belonging to \(H_0\).

---

## Superiority

A superiority test asks whether an effect exceeds a specified boundary.

For a difference in proportions:

\[
\Delta=p_1-p_2
\]

If superiority requires:

\[
\Delta>\delta
\]

then:

\[
H_0:\Delta\leq\delta
\]

\[
H_1:\Delta>\delta
\]

The margin \(\delta\) should be defined before analysing the data and
should have a scientific or practical justification.

---

## Non-inferiority

A non-inferiority test asks whether a new option is not unacceptably worse
than a reference option.

Suppose negative values favour the reference group and a decrease larger
than \(\delta\) is considered unacceptable.

Then:

\[
H_0:\Delta\leq-\delta
\]

\[
H_1:\Delta>-\delta
\]

Rejecting \(H_0\) supports the conclusion that the new option is not worse
than the reference by more than the allowed margin.

Non-inferiority does not automatically imply superiority.

---

## Equivalence

An equivalence test asks whether the effect lies inside a pre-defined
interval of practically negligible differences.

The equivalence region is:

\[
-\delta<\Delta<\delta
\]

The hypotheses are:

\[
H_0:
\Delta\leq-\delta
\quad
\text{or}
\quad
\Delta\geq\delta
\]

\[
H_1:
-\delta<\Delta<\delta
\]

The null hypothesis represents non-equivalence.

The alternative represents equivalence.

This formulation is necessary because failing to reject an equality null
hypothesis does not demonstrate that two effects are sufficiently close.

Equivalence is commonly evaluated using two one-sided tests.

---

## Type I and Type II errors

Because statistical decisions are made under uncertainty, errors are
possible.

### Type I error

A Type I error occurs when we reject \(H_0\) even though \(H_0\) is true.

\[
P(\text{Type I error})=\alpha
\]

The significance level \(\alpha\) defines the tolerated probability of a
Type I error under the assumptions of the test.

### Type II error

A Type II error occurs when we fail to reject \(H_0\) even though the
alternative is true.

\[
P(\text{Type II error})=\beta
\]

### Statistical power

Power is the probability of rejecting \(H_0\) when a specified alternative
is true.

\[
\text{Power}=1-\beta
\]

Low power is one reason why a non-significant result should not be treated
as evidence that \(H_0\) is true.

---

## A decision is not the same as certainty

The possible situations can be summarised as:

| Reality | Reject \(H_0\) | Fail to reject \(H_0\) |
|---|---|---|
| \(H_0\) is true | Type I error | Correct decision |
| \(H_1\) is true | Correct decision | Type II error |

The true state is unknown.

The analyst observes only the statistical decision.

This is why the language used to report results should remain cautious.

---

## Common misunderstandings

### “A large p-value proves \(H_0\)”

Incorrect.

A large p-value means that the data are not sufficiently incompatible
with \(H_0\) to reject it using the selected procedure.

---

### “A small p-value proves \(H_1\)”

Incorrect.

A small p-value indicates evidence against \(H_0\), conditional on the
model and assumptions.

It does not provide absolute proof.

---

### “Non-significant means no effect”

Incorrect.

A non-significant result may be caused by low power, high variability or
an imprecise estimate.

Inspect the confidence interval.

---

### “The hypothesis direction can be chosen after seeing the data”

Incorrect.

Choosing a one-sided hypothesis after inspecting the observed effect
inflates the probability of a false-positive conclusion.

The direction should be specified before examining the result.

---

### “The null hypothesis must always mean no effect”

Not necessarily.

The null may represent:

- no difference
- a minimum superiority boundary
- an unacceptable inferiority boundary
- non-equivalence
- any other parameter region the test is designed to challenge

For example:

\[
H_0:p_1-p_2\leq0.03
\]

does not represent exact equality.

It represents the absence of an improvement greater than three percentage
points.

---

## Practical workflow

Before running a hypothesis test:

1. Define the observational unit.
2. Identify the population parameter of interest.
3. State the scientific or practical claim.
4. Place that claim in \(H_1\).
5. Define the complementary parameter region as \(H_0\).
6. Decide whether the test is two-sided or one-sided.
7. Choose the significance level.
8. Specify any superiority, non-inferiority or equivalence margin.
9. Select a statistical procedure whose assumptions match the data.
10. Report the estimate, confidence interval, test statistic and p-value.

---

## Worked example

Suppose an A/B test compares completion rates.

The organisation requires an improvement of more than three percentage
points before deploying the new version.

Define:

\[
\Delta
=
p_{Test}-p_{Control}
\]

The scientific claim is:

\[
\Delta>0.03
\]

Therefore:

\[
H_0:\Delta\leq0.03
\]

\[
H_1:\Delta>0.03
\]

Suppose the observed difference is:

\[
\widehat{\Delta}=0.064
\]

The point estimate exceeds the required margin, but that alone is not
enough.

The statistical test must evaluate whether sampling uncertainty still
allows values at or below:

\[
0.03
\]

If the one-sided p-value is below the selected significance level, we may
reject \(H_0\) and conclude that the data support an improvement greater
than three percentage points.

If the p-value is not sufficiently small, the correct conclusion is:

> The evidence is insufficient to demonstrate that the improvement
> exceeds three percentage points.

It is not:

> The improvement is definitely three percentage points or less.

---

## Take-home message

!!! success "Main idea"

    Place in \(H_1\) the claim that you want the evidence to support.

    A classical hypothesis test may support \(H_1\) by rejecting \(H_0\).

    Failing to reject \(H_0\) does not prove that \(H_0\) is true.

    Absence of evidence is not necessarily evidence of absence.

---

## Related concepts

- P-values *(coming soon)*
- Confidence intervals *(coming soon)*
- Type I and Type II errors *(coming soon)*
- Statistical power *(coming soon)*
- Statistical versus practical significance *(coming soon)*
- Equivalence and non-inferiority *(coming soon)*

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [One-way ANOVA](../tests/one-way-anova.md)
- [Two-way ANOVA](../tests/two-way-anova.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)

---

## References

- Casella, G., & Berger, R. L. (2002).
  *Statistical Inference* (2nd ed.). Duxbury.
- Lehmann, E. L., & Romano, J. P. (2005).
  *Testing Statistical Hypotheses* (3rd ed.). Springer.
- Wasserstein, R. L., & Lazar, N. A. (2016).
  The ASA statement on p-values: Context, process, and purpose.
  *The American Statistician*, 70(2), 129–133.
