# BDD Automation Flowchart

```mermaid
graph TD
    Start([Start]) --> A[Read Excel Test Cases - Gherkin Format]
    A --> B[Parse Test Case Keywords<br/>(Given, When, Then)]
    B --> C{Identify Test Case Type}

    C --> D[Column Existence Check]
    C --> E[Column Nullity Check]
    C --> F[Table-to-Table Comparison]
    C --> G[Table-to-Excel Comparison]
    C --> H[Predefined SQL Execution]

    D --> I[Generate Corresponding SQL]
    E --> I
    F --> I
    G --> I
    H --> I

    I --> J[Execute SQL on BigQuery]
    J --> K[Capture Results from BigQuery]
    K --> L[Compile Results & Evidence into Excel Workbook<br/>(Separate Tabs per Test Case)]
    L --> End([End])
