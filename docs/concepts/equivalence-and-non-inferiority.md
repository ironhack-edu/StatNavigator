## Quick question

Suppose that we compare two machine learning models.

The statistical test produces

\[
p=0.42.
\]

We therefore fail to reject the null hypothesis.

Can we conclude that the two models perform equally well?

**No.**

A non-significant result tells us that we do not have sufficient evidence
to conclude that the models are different.

It does **not provide evidence that they are equivalent**. 

This distinction motivates two important families of statistical tests:

- **equivalence tests**
- **non-inferiority tests**

---

## Failure to detect a difference is not evidence of equality

In a traditional hypothesis test,

the null hypothesis usually represents the absence of an effect or
difference.

For example,

\[
H_0:\mu_A=\mu_B.
\]

We then ask whether the available evidence is strong enough to reject
that hypothesis.

If the result is not statistically significant, we **fail to reject** \(H_0\).

But notice what we have *not* demonstrated.

We have not demonstrated that

\[
\mu_A=\mu_B.
\]

There are at least two possible explanations.

1. The two population means may really be very similar.
2. A real difference may exist, but the study may not have enough
   statistical power to detect it.

The second situation corresponds to a [**Type II error**](computing-p-values.md#type-i-and-type-ii-errors): we fail to reject \(H_0\) even though \(H_0\) is false.

As we saw in [**Statistical Power**](statistical-power.md), low statistical power makes this error more likely.

---

!!! warning "Absence of evidence is not evidence of equivalence"

    Failing to reject a difference does **not** demonstrate that two
    treatments, models or processes are equivalent.

    A non-significant result may occur because the true difference is
    small.

    But it may also occur because the study does not contain enough
    information to detect an important difference.

    Demonstrating equivalence therefore requires a statistical procedure
    specifically designed to provide evidence that any remaining
    difference is sufficiently small.

---

## A different statistical question

Traditional hypothesis tests are designed to look for evidence of a
difference.

However, sometimes that is not the question we actually want to answer.

Imagine that a company already uses a machine learning model in
production.

A new model is

- much faster
- cheaper to run
- easier to interpret
- easier to maintain

The company may not need the new model to be **better**.

It may only need to know that its predictive performance is not meaningfully worse.

This is a fundamentally different statistical question.

Instead of asking

> *"Can we detect a difference?"*

we may want to ask

> *"Can we show that any difference is too small to matter?"*

or

> *"Can we show that the new model is not unacceptably worse?"*

These questions lead respectively to **equivalence** and
**non-inferiority** testing.

---

## What does "equivalent" mean?

Equivalence does not mean that two population parameters are exactly equal.

In practice, exact equality

\[
\theta_A=\theta_B
\]

is usually neither realistic nor necessary.

Instead, we need to decide how large a difference could be before it becomes practically important.

Suppose that

\[
\delta=\theta_A-\theta_B
\]

represents the true difference between two population parameters.

We define a positive value

\[
\Delta
\]

called the **equivalence margin**.

Differences between

\[
-\Delta
\]

and

\[
+\Delta
\]

are considered too small to be practically important.

Therefore,

\[
\boxed{
-\Delta < \delta < +\Delta
}
\]

defines the region of **practical equivalence**.

```text
Meaningfully worse       Equivalent        Meaningfully better

<----------------|=====================|---------------->
                -Δ          0          +Δ
```

---

!!! note "Equivalent does not mean identical"

    Equivalence testing does **not** attempt to demonstrate that

    \[
    \theta_A=\theta_B.
    \]

    Instead,

    it asks whether the remaining difference is sufficiently small to be
    considered practically unimportant.

---

## From practical significance to confidence intervals

This idea connects directly with
[**Statistical versus Practical Significance**](statistical-versus-practical-significance.md).

There, we distinguished between detecting an effect and deciding whether that
effect is large enough to matter.

Equivalence testing formalises that idea by defining explicit limits

\[
-\Delta
\qquad\text{and}\qquad
+\Delta.
\]

But the true difference

\[
\delta
\]

is unknown.

We only have an estimate obtained from our sample.

How can we determine whether the unknown population difference is
plausibly contained inside the equivalence region?

This is where [**confidence intervals**](computing-confidence-intervals.md) become particularly useful.

Later in this chapter, we will see that equivalence can be assessed by comparing a confidence
interval for the difference with the predefined equivalence margins.

---

## Reversing the usual hypotheses

Equivalence testing requires a different way of thinking about the null
hypothesis.

In a traditional hypothesis test, the null hypothesis usually represents no difference:

\[
H_0:\delta=0.
\]

We collect evidence in an attempt to reject this hypothesis.

Equivalence testing reverses this logic.

Instead of assuming that the two population parameters are equivalent, we assume that the difference between them is large enough to matter.

Conceptually,

\[
H_0:
\delta \le -\Delta
\quad
\text{or}
\quad
\delta \ge +\Delta.
\]

The alternative hypothesis is

\[
H_1:
-\Delta < \delta < +\Delta.
\]

Therefore, to conclude that two population parameters are equivalent, we need sufficient evidence to reject the possibility of a practically
important difference.

---

!!! tip "The null hypothesis has changed"

    In a traditional difference test,

    \[
    H_0
    \]

    usually represents **no difference**.

    In an equivalence test,

    \[
    H_0
    \]

    represents a difference **large enough to matter**.

    This reversal is the key to understanding equivalence testing.

---

## Two One-Sided Tests (TOST)

How can we test whether

\[
-\Delta < \delta < +\Delta?
\]

One common approach is the **Two One-Sided Tests procedure**, usually abbreviated as **TOST**.

The idea is simpler than its name may suggest.

To establish equivalence, we need to demonstrate two things:

1. the true difference is greater than the lower equivalence limit

\[
\delta > -\Delta;
\]

2. the true difference is smaller than the upper equivalence limit

\[
\delta < +\Delta.
\]

These are two one-sided hypothesis tests.

Both conditions must be satisfied before we can conclude that the
difference lies inside the equivalence region.

```text
                 Equivalence region

              -Δ                   +Δ
               │                     │
───────────────│═════════════════════│───────────────
               →                     ←
          δ must be              δ must be
          above -Δ               below +Δ
```

---

!!! note "Why two tests?"

    Equivalence requires ruling out meaningful differences in **both
    directions**.

    We must obtain evidence that the true difference is

    \[
    \delta>-\Delta
    \]

    and simultaneously that

    \[
    \delta<+\Delta.
    \]

    Passing only one of these tests is not enough to establish
    equivalence.

---

## A more intuitive approach: confidence intervals

There is another way to understand the same idea that is often much more
intuitive.

Earlier we learned that a [**confidence interval**](computing-confidence-intervals.md)
represents a range of plausible values for an unknown population parameter.

Here, the unknown parameter is the true difference

\[
\delta.
\]

Suppose that we construct a confidence interval for that difference.

If the entire interval lies inside the equivalence region, the data provide sufficient evidence to conclude equivalence at the chosen significance level.

\[
(-\Delta,+\Delta),
\]

the data provide sufficient evidence to conclude equivalence at the chosen significance level.

!!! warning "Remember: the confidence interval depends on the sample"

    The confidence interval is calculated from a random sample.

    If we repeated the study with different random samples, we would
    obtain different confidence intervals.

    Therefore, one sample may provide sufficient evidence of equivalence
    while another sample from the same populations may not.

    Equivalence testing does not eliminate sampling uncertainty.

    It provides a statistical decision while controlling the probability
    of making an incorrect conclusion.

    For the standard TOST procedure with

    \[
    \alpha=0.05,
    \]

    equivalence can be assessed using the corresponding two-sided

    \[
    90\%
    \]

    confidence interval.

    This may initially seem surprising.

    The reason is that TOST consists of two one-sided tests, each
    performed at the significance level

    \[
    \alpha=0.05.
    \]

    These correspond to a two-sided \(90\%\) confidence interval.

    Equivalence is established when this entire interval lies inside the
    predefined equivalence margins.

Conceptually:

```text
                    Equivalence region

              -Δ                         +Δ
               │                           │
───────────────│═══════════════════════════│───────────────
                     ├───────────┤
                    Confidence interval

                         ✓ Equivalent
```

However, if part of the confidence interval extends beyond an equivalence boundary, we cannot conclude equivalence.

```text
                    Equivalence region

              -Δ                         +Δ
               │                           │
───────────────│═══════════════════════════│───────────────
          ├────────────────┤

             Confidence interval

                   ✗ Equivalence not established
```

Notice the wording.

We do **not** conclude that the two population parameters are **non-equivalent**.

We conclude only that the available evidence is insufficient to establish equivalence.

---

!!! tip "Confidence intervals make equivalence visible"

    For equivalence to be established,

    the confidence interval for the difference must lie entirely inside
    the predefined equivalence margins.

    \[
    -\Delta
    <
    CI_{\text{lower}}
    <
    CI_{\text{upper}}
    <
    +\Delta
    \]

    This provides an intuitive visual interpretation of equivalence
    testing.

---

## Why a non-significant traditional test is not enough

We can now see why failing to reject

\[
H_0:\delta=0
\]

does not establish equivalence.

Consider a very uncertain estimate:

```text
                    Equivalence region

              -Δ                         +Δ
               │                           │
───────────────│═══════════════════════════│───────────────
       ├─────────────────────────────────────────┤
                  Confidence interval
```

The confidence interval contains

\[
0,
\]

so a traditional hypothesis test may fail to detect a statistically
significant difference.

But the interval also contains differences outside the equivalence
region.

The data are compatible both with

- practically negligible differences
- practically important differences

Therefore,

we do not have enough information to establish equivalence.

This is precisely why

> **failure to detect a difference is not evidence of equivalence.**

---

## What about non-inferiority?

Non-inferiority follows the same basic logic, but only one boundary matters.

Suppose that larger values represent better performance and that we are
willing to accept the new method provided that it is not worse than the
existing method by more than

\[
\Delta.
\]

The unacceptable region is

\[
\delta\le-\Delta.
\]

Therefore, the hypotheses can be written conceptually as

\[
H_0:\delta\le-\Delta
\]

against

\[
H_1:\delta>-\Delta.
\]

To establish non-inferiority,

we need sufficient evidence that the true difference lies above the lower acceptable boundary.

Using a confidence interval, this means that its lower bound must lie above

\[
-\Delta.
\]

```text
           Unacceptably worse        Acceptable

                     -Δ
                      │
──────────────────────│════════════════════════════════
                         ├──────────────┤
                        Confidence interval

                              ✓ Non-inferior
```

Unlike equivalence testing, the confidence interval does not need to remain below

\[
+\Delta.
\]

If the new method turns out to be substantially better, that does not contradict non-inferiority.

---

!!! tip "Two boundaries versus one"

    **Equivalence**

    \[
    -\Delta < \delta < +\Delta
    \]

    requires ruling out important differences in both directions.

    **Non-inferiority**

    \[
    \delta>-\Delta
    \]

    requires ruling out only an unacceptably worse result.

    This is why equivalence uses two boundaries while
    non-inferiority uses only one.

---

## A subtle but important conclusion

Traditional difference tests and equivalence tests answer fundamentally different questions.

A traditional test asks:

> **Is there sufficient evidence that a difference exists?**

An equivalence test asks:

> **Is there sufficient evidence that any difference is small enough not
> to matter?**

A non-inferiority test asks:

> **Is there sufficient evidence that the new option is not unacceptably
> worse?**

These conclusions are not interchangeable.

In particular,

\[
\text{not statistically different}
\]

does **not** imply

\[
\text{statistically equivalent}.
\]

---

## Key takeaways

After completing this chapter, you should understand that

- failing to reject the null hypothesis does not demonstrate
  equivalence
- a non-significant result may simply reflect insufficient statistical
  power
- equivalence requires defining a practically meaningful margin
  \(\Delta\)
- equivalence means that the true difference is sufficiently small, not
  that it is exactly zero
- equivalence testing reverses the usual role of the null hypothesis
- TOST tests both equivalence boundaries separately
- confidence intervals provide an intuitive way to assess equivalence
- non-inferiority considers only the boundary representing an
  unacceptably worse result
- equivalence and non-inferiority margins should be determined from the
  practical context, not chosen after observing the data.
- confidence intervals depend on the random sample, so different samples
  may lead to different equivalence conclusions

---

## Where to go next

We have now seen that statistical inference can answer several different questions.

We can ask whether an effect exists, whether we have enough statistical power to detect it, whether its magnitude is practically important,
and even whether a difference is sufficiently small to be considered equivalent.

But all these methods depend on choosing the **appropriate statistical test for the question and the data at hand**.

That brings us back to the main purpose of StatNavigator:

> **Which statistical test should I use?**

Return to the [**statistical method navigator**](../index.md) to choose a statistical test based on your data and research question.
