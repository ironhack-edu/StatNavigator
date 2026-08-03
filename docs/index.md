# Choosing the Right Statistical Method

Use the diagram below to identify an appropriate statistical method.

```mermaid
flowchart TD
    START{"What do you want to compare?"};

    START -->|"One sample against a reference value"| ONE["One-sample t-test"];
    START -->|"Two paired numerical measurements"| PAIRED["Paired t-test"];
    START -->|"Means of two independent groups"| WELCH["Welch's t-test"];
    START -->|"Means across one categorical factor"| ANOVA1["One-way ANOVA"];
    START -->|"Effects of two categorical factors"| ANOVA2["Two-way ANOVA"];
    START -->|"Proportions of two independent groups"| PROP2["Two-proportions z-test"];

    click ONE "tests/one-sample-t-test/" "Open the One-sample t-test card";
    click PAIRED "tests/paired-t-test/" "Open the Paired t-test card";
    click WELCH "tests/welch-t-test/" "Open the Welch's t-test card";
    click ANOVA1 "tests/one-way-anova/" "Open the One-way ANOVA card";
    click ANOVA2 "tests/two-way-anova/" "Open the Two-way ANOVA card";
    click PROP2 "tests/two-proportions-z-test/" "Open the Two-proportions z-test card";

    classDef question fill:#e8f1fb,stroke:#2463a6,stroke-width:2px,color:#111;
    classDef continuous fill:#e7f4ea,stroke:#2e7d32,stroke-width:2px,color:#111;
    classDef proportion fill:#fff1df,stroke:#d97706,stroke-width:2px,color:#111;

    class START question;
    class ONE,PAIRED,WELCH,ANOVA1,ANOVA2 continuous;
    class PROP2 proportion;
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
  Compare the means of three or more independent groups defined by a single categorical factor.

- [Two-way ANOVA](tests/two-way-anova.md)  
  Evaluate the effects of two categorical factors simultaneously and determine whether they interact.

### Comparison of proportions

- [Two-proportions z-test](tests/two-proportions-z-test.md)  
  Compare the success probabilities of two independent groups.

---

*More statistical methods will be added over time, including assumption checks, non-parametric tests, regression models, categorical data analysis and statistical concepts.*
