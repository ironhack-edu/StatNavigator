# Choosing the Right Statistical Method

Use the diagram below to identify an appropriate statistical method.

```mermaid
flowchart TD
    START{"What do you want to compare?"}
    START -->|"Means of two independent groups"| WELCH["Welch's t-test"]

    click WELCH "tests/welch-t-test/" "Open the Welch's t-test card"

    classDef question fill:#e8f1fb,stroke:#2463a6,stroke-width:2px,color:#111;
    classDef continuous fill:#e7f4ea,stroke:#2e7d32,stroke-width:2px,color:#111;

    class START question;
    class WELCH continuous;
```
