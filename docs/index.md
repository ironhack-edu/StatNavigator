# Choosing the Right Statistical Method

Use the diagram below to identify an appropriate statistical method.

```mermaid
flowchart TD

    START{"What do you want to compare?"}

    START -->|"One sample against a reference value"| ONE["One-sample t-test"]
    START -->|"Two paired measurements"| PAIRED["Paired t-test"]
    START -->|"Two independent groups"| WELCH["Welch's t-test"]
    START -->|"Three or more independent groups"| ANOVA["One-way ANOVA"]

    click ONE "tests/one-sample-t-test/" "Open the One-sample t-test card"
    click PAIRED "tests/paired-t-test/" "Open the Paired t-test card"
    click WELCH "tests/welch-t-test/" "Open the Welch's t-test card"
    click ANOVA "tests/one-way-anova/" "Open the One-way ANOVA card"

    classDef question fill:#e8f1fb,stroke:#2463a6,stroke-width:2px,color:#111;
    classDef continuous fill:#e7f4ea,stroke:#2e7d32,stroke-width:2px,color:#111;

    class START question;
    class ONE,PAIRED,WELCH,ANOVA continuous;
```

## Available methods

### Comparison of means

- [One-sample t-test](tests/one-sample-t-test.md)  
  Compare a sample mean against a reference value.

- [Paired t-test](tests/paired-t-test.md)  
  Compare the mean difference between two related measurements.

- [Welch's t-test](tests/welch-t-test.md)  
  Compare the means of two independent groups without assuming equal variances.

- [One-way ANOVA](tests/one-way-anova.md)  
  Compare the means of three or more independent groups.

---

*More statistical methods will be added over time, including Two-way ANOVA, non-parametric tests, regression models and assumption checks.*
