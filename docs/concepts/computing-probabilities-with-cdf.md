---
title: Cumulative distribution function (CDF)
---

# Cumulative distribution function (CDF)

← [Back to the statistical method navigator](../index.md)

---

## Quick question

Once we know the probability distribution of a random variable, one
question naturally arises.

> **What is the probability that the variable takes a value less than or
> equal to a given threshold?**

The mathematical tool that answers this question is called the
**cumulative distribution function (CDF).**

---

## Why do we need the CDF?

In the previous chapter we learned that every hypothesis test compares
an observed statistic with its probability distribution under the null
hypothesis.

Suppose that the observed test statistic is

\[
T = 2.31.
\]

Knowing that the statistic follows a probability distribution is useful.

However, another question immediately arises.

> **What is the probability of observing a value less than or equal to
> 2.31?**

Or, more generally,

> **What is the probability that a random variable is less than or equal
> to a given value?**

The mathematical tool that answers this question is the **cumulative
distribution function (CDF).**

---

## From a probability distribution to probabilities

A probability distribution tells us how the values of a random variable
are distributed.

However, in statistical inference we are usually interested in
probabilities rather than in the shape of the distribution itself.

For example, we might ask:

- What is the probability that a statistic is less than 2?
- What is the probability that it is greater than 2?
- What is the probability that it lies between 1 and 2?

The CDF provides a simple way to answer all these questions.

If you would like to learn why hypothesis tests require probability distributions, see [Probability distributions](probability-distributions.md).

---

## The cumulative distribution function

Before introducing the mathematical definition, it is important to
distinguish between two different symbols.

- **\(X\)** denotes the random variable.
- **\(x\)** denotes one particular value of that variable.

For example,

- \(X\) could represent the test statistic.
- \(x = 2.31\) is one observed value of that statistic.

Using this notation, the cumulative distribution function is defined as

\[
\boxed{\mathrm{CDF}(x)=F(x)=P(X\le x)}
\]

In words,

> **The CDF evaluated at \(x\) gives the probability that the random
> variable \(X\) takes a value less than or equal to \(x\).**

Notice that

- the input of the CDF is a **numerical value**
- the output is always a **probability**

---

## A visual interpretation

Imagine the probability distribution shown below.

```text
                 │
             ____│____
           /█████│
         /███████│
_______/█████████│____________
                x
```

The shaded area represents

\[
P(X\le x).
\]

The CDF simply computes the probability contained in the shaded region.

As the value of \(x\) moves to the right, the shaded area becomes larger.

Consequently, the CDF is always a non-decreasing function.

---

## Computing probabilities to the right

The CDF computes probabilities to the **left** of a given value.

However, hypothesis testing often requires probabilities to the
**right**.

Fortunately, this is very easy.

The total probability under any probability distribution is always equal
to **1**.

Therefore, if the probability to the left is already known, the
remaining probability must lie to the right.

```text
                 │
             ____│████████
           /     │██████████
         /       │████████████
_______/         │██████████████______
                x

Left area  = F(x)

Right area = 1 − F(x)
```

Consequently,

\[
P(X>x)=1-P(X\le x).
\]

Using the definition of the CDF,

\[
\boxed{P(X>x)=1-F(x)}
\]

This relationship is known as the **complement rule**.

---

## Computing probabilities between two values

Sometimes we are interested in the probability that a random variable
lies **between two values**.

For example,

> **What is the probability that a statistic lies between 1 and 2?**

The CDF also answers this question.

The probability accumulated up to the larger value is

\[
F(b).
\]

The probability accumulated up to the smaller value is

\[
F(a).
\]

Therefore, the probability contained between the two values is simply
the difference between both cumulative probabilities.

```text
                a           b
                │           │
            ____│███████████│____
          /     │███████████│
_________/      │███████████│____________

Left of a : F(a)

Left of b : F(b)

Between a and b : F(b) − F(a)
```

Consequently,

\[
\boxed{P(a<X\le b)=F(b)-F(a)}
\]

The CDF therefore allows us to compute probabilities in three common
situations:

- to the left of a value
- to the right of a value
- between two values

---

## Properties of the CDF

The CDF always returns a probability.

Since probabilities can never be negative and the total probability
under a probability distribution is always equal to **1**, the CDF can
only take values between 0 and 1.

Therefore,

\[
0 \le F(x) \le 1.
\]

Furthermore,

- the CDF is monotonically non-decreasing
- it approaches 0 in the left tail of the distribution
- it approaches 1 in the right tail

These properties hold for every cumulative distribution function,
regardless of the underlying probability distribution.

!!! tip "Symmetric probability distributions"

    The complement rule,

    \[
    P(X>x)=1-F(x),
    \]

    applies to **every** probability distribution.

    However, if the distribution is **symmetric** (such as the Normal or
    Student's *t* distribution), an additional relationship holds.

    Values that are equally far from the centre of the distribution have
    complementary cumulative probabilities.

    For example,

    \[
    F(-1.96)=0.025,
    \]

    whereas

    \[
    F(1.96)=0.975.
    \]

    Notice that

    \[
    0.025+0.975=1.
    \]

    This is a direct consequence of the symmetry of the distribution.

    It explains why symmetric distributions produce pairs of critical
    values such as

    \[
    -1.96
    \qquad\text{and}\qquad
    1.96.
    \]

    This property does **not** hold for asymmetric distributions such as
    the Chi-square or F distributions.

---

## Computing probabilities in Python

Most scientific libraries provide a cumulative distribution function for
every probability distribution.

The SciPy library, for example, uses the method `cdf()`.

### Normal distribution

Suppose that

\[
Z\sim N(0,1).
\]

To compute

\[
P(Z\le1.96),
\]

use

```python
from scipy.stats import norm

norm.cdf(1.96)
```

which returns approximately

```text
0.975
```

This means that approximately **97.5%** of the distribution lies to the
left of **1.96**.

---

### Student's *t* distribution

Exactly the same idea applies to other probability distributions.

For example, suppose that

\[
T\sim t(18),
\]

where the distribution has 18 degrees of freedom.

The probability

\[
P(T\le2.10)
\]

is computed as

```python
from scipy.stats import t

t.cdf(2.10, df=18)
```

Here,

- `2.10` is the value at which the cumulative probability is evaluated;
- `df=18` indicates that the *t* distribution has **18 degrees of freedom**.

!!! tip "Where do the degrees of freedom come from?"

    The degrees of freedom are **not chosen arbitrarily**.

    They are determined by the statistical method being used.

    For example,

    - one-sample t-test: \(df=n-1\)
    - paired t-test: \(df=n-1\)
    - Welch's t-test: computed using the Welch–Satterthwaite equation

    The CDF does not calculate the degrees of freedom.

    It simply uses the value provided.

Notice that the only difference is the probability distribution being
used.

The interpretation is exactly the same.

Only the distribution and its parameters change.

The interpretation of the CDF never changes.

For example, a one-sample t-test based on a sample of size \(n\) uses

\[
df=n-1.
\]

In this example,

\[
n=19,
\]

so

\[
df=18.
\]

The exact formula for the degrees of freedom depends on the statistical
method being used.

For example, Welch's t-test uses a different formula from the
one-sample t-test.

Regardless of how the degrees of freedom are obtained, the CDF is always
used in exactly the same way.

Notice that the only difference is the probability distribution being
used.

The interpretation is exactly the same.

---

## A consistent interface

One of the advantages of SciPy is that every probability distribution
uses the same interface.

For example,

| Distribution | Python |
|--------------|--------|
| Normal | `norm.cdf(x)` |
| Student's *t* | `t.cdf(x, df)` |
| Chi-square | `chi2.cdf(x, df)` |
| F | `f.cdf(x, dfn, dfd)` |

Regardless of the distribution, the meaning is always the same.

The function returns

\[
P(X\le x).
\]

Some probability distributions are completely determined by their shape.

Others depend on one or more parameters.

Whenever this happens, those parameters must also be supplied when
computing cumulative probabilities.

---

## Common misunderstandings

### "The CDF gives the probability of observing exactly one value."

Not usually.

For continuous probability distributions,

\[
P(X=x)=0.
\]

The CDF returns the probability accumulated **up to** a given value.

---

### "The CDF always computes the probability that the variable is greater than a value."

Incorrect.

The CDF computes probabilities to the **left**.

Probabilities to the right are obtained using

\[
1-F(x).
\]

---

### "Different probability distributions require different functions."

Not conceptually.

Every probability distribution has its own CDF.

Only the underlying distribution changes.

The interpretation remains exactly the same.

### "The CDF depends on the programming library."

No.

The cumulative distribution function is a mathematical concept.

Functions such as `norm.cdf()` or `t.cdf()` are simply software
implementations of that mathematical definition.

Other libraries may use different function names for the same
mathematical concept.

---

## Take-home message

!!! success "Main idea"

    The cumulative distribution function transforms a probability
    distribution into a tool for computing probabilities.

    Once the CDF is known, probabilities can be computed

    - to the left of a value
    - to the right of a value
    - between two values

---

We now know how to compute probabilities from a probability
distribution.

But sometimes the problem is exactly the opposite.

Instead of knowing the value and asking for its probability,

we now know the probability and want to determine the
corresponding value.

For example,

> **Which value leaves exactly 5% of the distribution to its right?**

Answering this question requires the inverse of the CDF.

This inverse function is called the **Percent Point Function (PPF)**.

---

## Related concepts

- [Probability distributions](probability-distributions.md)
- Percent Point Function (PPF) *(coming soon)*
- P-values *(coming soon)*

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)
- [One-way ANOVA](../tests/one-way-anova.md)
- [Two-way ANOVA](../tests/two-way-anova.md)
