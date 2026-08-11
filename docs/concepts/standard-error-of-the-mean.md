---
title: Standard Error of the Mean (SEM) 
---

# Standard Error of the Mean (SEM) 

← [Back to the statistical method navigator](../index.md)

---

## Quick question

In the previous chapter we learned that repeated random samples produce different sample means.

The Central Limit Theorem tells us that those sample means follow an approximately Normal distribution.

However, another important question naturally arises.

> **How much should we expect the sample mean to vary from one sample to another?**

The answer is given by the **Standard Error of the Mean (SEM).**

---

## Why do we need the Standard Error?

Suppose that two independent researchers collect random samples from the same population.

Even if both samples are perfectly random, they will almost certainly obtain different **sample means**.

Why?

Because every random sample is different.

Some samples happen to contain slightly larger observations.

Others contain slightly smaller ones.

The Standard Error measures exactly this variability.

It tells us how much the **sample mean** is expected to fluctuate **from one random sample to another**.

---

## Three different measures of variability

Statistics uses three closely related quantities that are often confused.

| Quantity | Symbol | What does it measure? |
|----------|--------|-----------------------|
| **Population standard deviation** | \(\sigma\) | The variability of the entire population. |
| **Sample standard deviation** | \(s\) | An estimate of the unknown population standard deviation computed from a sample. |
| **Standard Error** | \(SE=\sigma/\sqrt{n}\) (or approximately \(s/\sqrt{n}\)) | The variability of the **sample mean** from one sample to another. |

The first two describe the variability of **individual observations**.

The Standard Error describes the variability of the **sample means**.

These quantities answer different questions and should never be used interchangeably.

---
```text
Population

           Population Standard Deviation (σ)

                    │<──────────────>│

┌──────────────────────────────────────────────────────────────┐
│ x₁  x₂  x₃  x₄  x₅  x₆  x₇  x₈  x₉  x₁₀  x₁₁  ...            │
└──────────────────────────────────────────────────────────────┘

                 Individual observations


One random sample

              Sample Standard Deviation (s)

               │<──────────────>│ 

               {x₁,  x₅,  x₈,...}

          Individual observations in one sample


Repeated random samples

           Standard Error of the Mean (SEM)

        ⎧ {x₁,  x₅,  x₈,  x₉, ...} ───► x̄₁
        ⎪
        ⎪ {x₈,  x₂,  x₇,  x₃, ...} ───► x̄₂
        ⎪
        ⎨ {x₁₈, x₁₃, x₂₃, ...} ─────► x̄₃
        ⎪
        ⎪ {x₂,  x₇,  x₃, ...} ──────► x̄₄
        ⎪
        ⎩ {x₆,  x₃,  x₈, ...} ──────► x̄₅
                   ⋮
            Variability of the sample means (SEM) 
```

---

## Computing the Standard Error

If the population standard deviation is known,

the Standard Error of the sample mean is

\[
\boxed{
SE
=
\frac{\sigma}{\sqrt{n}}
}
\]

where

- \(\sigma\) is the population standard deviation;
- \(n\) is the sample size.

In practice, the population standard deviation is almost never known.

It is therefore replaced by the sample standard deviation, giving

\[
\boxed{
SEM
\approx
\frac{s}{\sqrt{n}}
}
\]

!!! note "Why do we replace σ by s?"

    In practice,

    the population standard deviation

    \[
    \sigma
    \]

    is almost never known.

    It must therefore be estimated from the sample using

    \[
    s.
    \]

    Estimating the population variability introduces additional uncertainty.

    This is why many statistical methods use **Student's t distribution** instead of the Normal distribution.

    We will return to this idea in later chapters.

This approximation is used in most practical applications.

---

## Why does the Standard Error decrease?

Notice what happens when the sample size increases.

The denominator

\[
\sqrt{n}
\]

becomes larger. Consequently, the Standard Error becomes smaller.

This means that repeated sample means become increasingly concentrated around the population mean.

Larger samples therefore produce more precise estimates.

---

!!! tip "Doubling the sample size does not halve the Standard Error"

    The Standard Error decreases proportionally to

    \[
    \frac{1}{\sqrt{n}}.
    \]

    Consequently, doubling the sample size does **not** halve the Standard Error.

    To reduce the Standard Error by half, the sample size must be multiplied by four.

This is one of the most important practical consequences of the Standard Error.

---

## Key takeaways

After completing this chapter, you should understand that:

- The Standard Error measures the variability of the **sample mean**.
- It is different from both the population and sample standard deviations.
- Larger samples produce smaller Standard Errors.
- The Standard Error decreases proportionally to \(1/\sqrt n\).
- In practice, the population standard deviation is usually unknown and must be estimated from the sample.

---

## Where to go next

Throughout this chapter we **assumed** that the Standard Error can be computed using

\[
SE \approx \frac{s}{\sqrt n}.
\]

But this raises a natural question.

> **Where does the sample standard deviation \(s\) come from?**

Unlike the population standard deviation, it must be **estimated** from the sample itself.

Understanding how this estimate is computed, and why it requires a small
correction, is the next step towards understanding many statistical methods.

Continue with

- [Bessel's correction]*(coming soon)*
