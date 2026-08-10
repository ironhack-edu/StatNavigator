---
title: Percent Point Function (PPF)
---

# Percent Point Function (PPF)

← [Back to the statistical method navigator](../index.md)

---

## Quick question

Once we know how to compute probabilities from a probability
distribution, another question naturally arises.

> **Which value corresponds to a given probability?**

The mathematical tool that answers this question is called the
**Percent Point Function (PPF)**.

---

## Why do we need the PPF?

In the previous chapter we learned how to compute probabilities from a
probability distribution using the cumulative distribution function
(CDF).

Suppose that

\[
P(Z\le x)=0.975.
\]

The probability is known.

However, the corresponding value of \(x\) is not.

A natural question is therefore

> **Which value leaves 97.5% of the distribution to its left?**

Or, equivalently,

> **Which value leaves only 2.5% of the distribution to its right?**

The mathematical tool that answers these questions is the
**Percent Point Function (PPF)**.

---

## From probabilities to values

The CDF starts with a value and computes its cumulative probability.

The PPF does exactly the opposite.

It starts with a cumulative probability and returns the corresponding
value of the random variable.

For this reason, the PPF is often called the **inverse of the CDF**.

---

## The Percent Point Function

Mathematically,

\[
\boxed{x=F^{-1}(p)}
\]

where

- \(p\) is a cumulative probability;
- \(x\) is the corresponding value of the random variable.

---

## CDF vs PPF

Notice that

- the input of the PPF is a probability
- the output is a numerical value.

| CDF                              | PPF                                      |
| -------------------------------- | ---------------------------------------- |
| Starts with a value              | Starts with a probability                |
| Returns a **probability**        | Returns a **value**                      |
| Computes accumulated probability | Computes the corresponding cut-off value |
| Used to compute probabilities    | Used to compute critical values          |
| Input → value                    | Input → probability                      |
| Output → probability             | Output → value                           |

---

## A visual interpretation

Suppose that we wish to find the value that leaves 95% of the
distribution to its left.

```text
                 │
             ____│____
           /█████│
         /███████│
_______/█████████│____________
                x

Left area = 0.95
```

The PPF determines the location of the vertical line.

It answers the question

> **Where must the cut-off value be placed so that the accumulated
> probability equals 95%?**

---

## Why is the PPF important?

Many statistical methods require determining **critical values**.

For example,

- the critical value of a z-test
- the critical value of a t-test
- confidence interval limits

In every case, the problem is the same.

The probability is known.

The corresponding value must be found.

This is exactly what the PPF computes.

---

## Computing critical values in Python

Like the cumulative distribution function, the Percent Point Function is
implemented in most scientific libraries.

In SciPy, the inverse cumulative distribution function is provided by
the method `ppf()`.

### Normal distribution

Suppose that we wish to determine the value that leaves

\[
97.5\%
\]

of the distribution to its left.

Equivalently,

\[
P(Z\le z)=0.975.
\]

This value can be computed as

```python
from scipy.stats import norm

norm.ppf(0.975)
```

which returns approximately

```text
1.96
```

Therefore,

\[
P(Z\le1.96)=0.975.
\]

Notice that the input of the function is now a **probability**, not a
numerical value.

The output is the corresponding critical value.

---

### Student's *t* distribution

The same idea applies to every probability distribution.

Suppose that we need the value leaving

\[
97.5\%
\]

of a Student's *t* distribution with 18 degrees of freedom to its left.

The computation is

```python
from scipy.stats import t

t.ppf(0.975, df=18)
```

Here,

- `0.975` is the cumulative probability;
- `df=18` specifies the degrees of freedom of the distribution.

As with the CDF, the degrees of freedom depend on the statistical method
being used.

The PPF simply uses the value provided.

Notice that the only difference is the probability distribution being
used.

The interpretation is exactly the same.

---

## Computing critical values for hypothesis tests

In hypothesis testing, the significance level

\[
\alpha
\]

determines the size of the rejection region.

The role of the PPF is to locate the **critical value(s)** that separate
the rejection region from the non-rejection region.

### Right-tailed tests

Suppose that

\[
\alpha=0.05.
\]

The rejection region occupies the rightmost 5% of the distribution.

```text
                       Critical value
                             │
               ______________│██████████
             /               │███████████
___________/                 │████████████
                            zα

Accepted region      Rejection region (α = 0.05)
```

Since 5% of the distribution lies to the right, 95% must lie to the
left.

Therefore, the critical value is computed as

```python
from scipy.stats import norm

norm.ppf(0.95)
```

which returns approximately

```text
1.64
```

Therefore, the critical value is: 1.64

---

### Left-tailed tests

Again suppose that

\[
\alpha=0.05.
\]

Now the rejection region occupies the leftmost 5% of the distribution.

```text
          Critical value
                │
██████████______│_________________________
█████████      /│
███████      /  │
___________/____│_________________________

Rejection region (α = 0.05)     Accepted region
```

The critical value leaves exactly 5% of the probability distribution to
its left.

It is therefore computed as

```python
from scipy.stats import norm

norm.ppf(0.05)
```

which returns approximately

```text
-1.64
```

Therefore, the critical value is: -1.64

---

### Two-sided tests

Finally, suppose that

\[
\alpha=0.05.
\]

The significance level is **divided equally between both tails**.

Each rejection region therefore contains

\[
\alpha/2=0.025.
\]

```text
      Critical            Critical
       value               value
         │                   │
██████___│___________________│___██████
█████    │                   │    █████
_______/ │                   │ \________

 α/2 = 0.025           α/2 = 0.025
```

The two critical values are obtained as

```python
from scipy.stats import norm

norm.ppf(0.025) # -1.960
norm.ppf(0.975) #  1.960
```

Lower critical value = -1.96

Upper critical value =  1.96

!!! tip "Why are the two critical values symmetric?"

    In a two-sided test based on a **symmetric probability distribution**
    (such as the Normal or Student's *t* distribution), the two critical
    values have the same magnitude but opposite signs.

    For example,

    \[
    z_{0.025}=-1.96
    \]

    and

    \[
    z_{0.975}=1.96.
    \]

    This is **not a coincidence**.

    It is a direct consequence of the symmetry of the probability
    distribution.

    Since both tails contain the same probability, the corresponding
    critical values are equally far from the centre of the distribution.

    This is why two-sided hypothesis tests based on symmetric distributions produce pairs of critical values with the same magnitude but opposite signs.

    Asymmetric distributions do not have this property.    

    This property is a direct consequence of the symmetry of the Normal and Student's *t* distributions (see 
[Probability distributions](probability-distributions.md).

---

## The same interface for every distribution

SciPy uses a consistent interface for all probability distributions.

| Distribution | Python |
|--------------|--------|
| Normal | `norm.ppf(p)` |
| Student's *t* | `t.ppf(p, df)` |
| Chi-square | `chi2.ppf(p, df)` |
| F | `f.ppf(p, dfn, dfd)` |

Regardless of the distribution, the interpretation is always the same.

The function returns the value corresponding to the cumulative
probability provided.

Some probability distributions are completely determined by their shape.

Others depend on one or more parameters.

Whenever this happens, those parameters must also be supplied when
computing critical values.

---

## CDF and PPF: two complementary tools

The cumulative distribution function and the Percent Point Function
solve opposite problems.

| CDF | PPF |
|-----|-----|
| Starts with a value | Starts with a probability |
| Returns a probability | Returns a value |
| Used to compute probabilities | Used to compute critical values |
| Input: value | Input: probability |
| Output: probability | Output: value |

The two functions are mathematical inverses of one another.

---

## CDF and PPF in hypothesis testing

Both functions play complementary roles in hypothesis testing.

| Known | Need to compute | Tool |
|--------|-----------------|------|
| Observed statistic | p-value | CDF |
| Significance level (\(\alpha\)) | Critical value | PPF |

Different statistical software may emphasise one approach or the other.

However, both approaches lead to exactly the same statistical decision.

---

## Common misunderstandings

### "The PPF is only used with the Normal distribution."

Incorrect.

Every probability distribution has its own Percent Point Function.

Only the underlying distribution changes.

---

### "The PPF computes probabilities."

No.

The PPF performs the opposite operation.

It starts with a probability and returns the corresponding value.

---

### "The PPF depends on the programming library."

No.

The Percent Point Function is a mathematical concept.

Functions such as `norm.ppf()` and `t.ppf()` are software
implementations of that concept.

Other libraries may use different function names for the same
mathematical idea.

---

## Take-home message

!!! success "Main idea"

    The Percent Point Function is the inverse of the cumulative
    distribution function.

    It transforms probabilities into values.

    In hypothesis testing, it is primarily used to determine critical
    values from the chosen significance level.

---

We now know how to compute both probabilities and critical values from a
probability distribution.

Hypothesis tests often use the PPF to determine critical values from a
chosen significance level.

Modern statistical software, however, often reports **p-values**
instead.

How are these two approaches related?

Why do they always lead to exactly the same statistical decision?

The next chapter answers these questions.

---

## Related concepts

- [Probability distributions](probability-distributions.md)
- [Computing probabilities with the CDF](computing-probabilities-with-cdf.md)
- [Computing p-values](computing-p-values.md)

---

## Related methods

- [One-sample t-test](../tests/one-sample-t-test.md)
- [Paired t-test](../tests/paired-t-test.md)
- [Welch's t-test](../tests/welch-t-test.md)
- [Two-proportions z-test](../tests/two-proportions-z-test.md)
- [One-way ANOVA](../tests/one-way-anova.md)
- [Two-way ANOVA](../tests/two-way-anova.md)
