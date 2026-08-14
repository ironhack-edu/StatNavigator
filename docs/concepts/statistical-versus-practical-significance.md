---
title: Statistical versus Practical Significance
---

# Statistical versus Practical Significance

← [Back to the statistical method navigator](../index.md)

---

## Quick question

Suppose that two machine learning models are evaluated on a test set containing several million observations.

Model A achieves an accuracy of

\[
94.10\%.
\]

Model B achieves

\[
94.15\%.
\]

A statistical test comparing both models produces

\[
p<0.0001.
\]

The improvement is therefore **highly statistically significant**.

But should the company replace its current model for an improvement of only **0.05 percentage points**?

The answer depends on the application.

If the new model is much more expensive to train, slower to deploy or
harder to maintain, such a small improvement may not justify the additional cost.

This illustrates an important distinction in statistical inference.

!!! note "The examples are illustrative"

    The numerical values used throughout this chapter are intended only
    to illustrate the difference between **statistical significance**
    and **practical significance**.

    Whether an observed effect is considered practically important
    always depends on the application and should be assessed by domain
    experts.

    In medicine, engineering, finance or manufacturing, even very small
    differences may sometimes have important real-world consequences.

---

## Statistical significance

A result is said to be **statistically significant** when the observed
data provide sufficient evidence to reject the null hypothesis at the
chosen significance level.

In other words, statistical significance tells us that the observed effect is unlikely to
be explained by random sampling variation alone.

It does **not** tell us whether the effect is large, important, or **useful in practice**.

---

!!! tip "Statistical significance answers only one question"

    Statistical significance tells us whether there is sufficient
    evidence against the null hypothesis.

    It does **not** tell us whether the observed effect is meaningful.

---

## Practical significance

Practical significance asks a completely different question.

Instead of asking

> *"Is the effect real?"*

it asks

> *"Is the effect large enough to matter?"*

The answer depends entirely on the context.

For example, an improvement in prediction accuracy of

\[
0.05\%
\]

may be too small to justify replacing an existing machine learning model, especially if the new model is more expensive to train, slower to deploy or harder to maintain.

On the other hand, the same numerical improvement might be valuable in applications where even small gains translate into substantial economic or societal benefits.

Practical significance therefore requires interpreting the size of the observed effect within its real-world context.

---

## Why are these concepts different?

Statistical significance depends strongly on the sample size.

As we learned in the previous chapters, larger samples produce smaller Standard Errors.

Smaller Standard Errors make it easier to detect even very small differences.

Consequently, a tiny effect may become statistically significant if the sample size is large enough.

Conversely, a practically important effect may fail to reach statistical significance if the sample size is too small.

---

## Statistical significance is not enough

Statistical significance answers an important question.

> *"Is there sufficient evidence that an effect exists?"*

However, many real-world decisions require answering an additional question.

> *"Is the observed effect large enough to justify taking action?"*

A statistically significant result therefore represents **the beginning of the analysis**, not its end.

In practice, statistical significance should always be interpreted together with the estimated magnitude of the observed effect and the context in which it occurs.

---

!!! tip "Statistical significance is only one part of the story"

    A small p-value tells us that the observed effect is unlikely to be
    explained by random variation alone.

    It does **not** tell us whether the effect is important enough to
    justify changing a treatment, deploying a new machine learning model
    or modifying an industrial process.

---

## Confidence intervals provide additional information

Earlier we learned that confidence intervals estimate a plausible range
of values for an unknown population parameter.

This information is also useful when assessing practical significance.

A confidence interval allows us to evaluate not only whether an effect is likely to exist,
but also whether its magnitude is large enough to matter in practice.

For example, a confidence interval that contains only very small improvements may
suggest that, although the effect is statistically significant, its
practical impact is limited.

Conversely, a wide confidence interval may indicate that additional data are needed
before making an informed decision.

---

!!! tip "Never interpret a p-value in isolation"

    Whenever possible, interpret hypothesis tests together with confidence intervals.

    Together, they provide considerably more information than a p-value alone.

---

## A common mistake

One of the most common mistakes in statistical inference is assuming
that a statistically significant result is automatically important.

This is not necessarily true.

As we learned in the previous chapter, **large samples reduce the Standard Error of the Mean**.

Consequently, even **extremely small effects may become statistically significant if the sample size is sufficiently large**.

Conversely, **a practically important effect may fail to reach statistical significance if the study has low statistical power**.

This is why statistical significance should never be interpreted without considering the size of the observed effect and the quality of the
available evidence.

---

!!! warning "Significant does not mean important"

    Statistical significance answers the question

    > *"Is there evidence that an effect exists?"*

    Practical significance answers a different question

    > *"Does the observed effect matter in the real world?"*

    Confusing these two concepts is one of the most common mistakes in
    applied statistics.

---

## Key takeaways

After completing this chapter, you should understand that

- statistical significance and practical significance answer different
  questions
- statistically significant results are not necessarily important in
  practice
- practical significance always depends on the application and the
  surrounding context
- confidence intervals help assess whether an observed effect is large
  enough to matter
- statistical significance should never be interpreted in isolation.

---

## Where to go next

If practical significance depends on the magnitude of the observed effect, how can we measure that magnitude objectively?

The next chapter introduces
[**Effect Size**]*(effect-size)*,

a family of measures designed to quantify the practical importance of an observed effect independently of the sample size.
