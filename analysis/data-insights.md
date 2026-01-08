# Data Insights Extraction

## Description

Analyze data to extract actionable insights. Identifies patterns, anomalies, and recommendations from datasets, logs, or metrics.

## Prompt

```
Analyze this data and extract insights:

## Data

{{data}}

## Context

{{context}}

## Questions to Answer

{{questions}}

---

## Analysis Framework

### 1. Data Overview

**What am I looking at?**
- Data type (time series, categorical, numerical)
- Size and completeness
- Time range covered
- Key fields/columns

**Data Quality Issues:**
- Missing values
- Outliers
- Inconsistencies

### 2. Descriptive Statistics

For numerical data:
- Count, mean, median, mode
- Min, max, range
- Standard deviation
- Distribution shape

For categorical data:
- Unique values
- Frequency distribution
- Most/least common

### 3. Pattern Recognition

**Trends:**
- Is there an upward/downward trend?
- Seasonal patterns?
- Cyclical behavior?

**Correlations:**
- What variables move together?
- What variables move opposite?
- Potential causation to investigate?

**Segments:**
- Are there distinct groups in the data?
- How do segments differ?

### 4. Anomaly Detection

**Outliers:**
- What points are unusual?
- Are they errors or meaningful?

**Sudden Changes:**
- Any abrupt shifts?
- What happened at those times?

### 5. Key Insights

Present 3-5 actionable insights:

**Insight 1: [Title]**
- Finding: [What the data shows]
- Evidence: [Specific numbers/comparisons]
- Implication: [What this means]
- Recommendation: [What to do about it]

### 6. Limitations

- What can't we conclude from this data?
- What additional data would help?
- What assumptions are we making?

### 7. Next Steps

- Immediate actions
- Further analysis needed
- Data to collect going forward
```

## Variables

- `{{data}}`: The dataset (CSV, JSON, table, or description of metrics)
- `{{context}}`: Business context (what this data represents, why you're analyzing it)
- `{{questions}}`: Specific questions you want answered

## Example Usage

```
Analyze this data and extract insights:

## Data

| Month | Signups | Churn | Revenue |
|-------|---------|-------|---------|
| Jan   | 1200    | 45    | $24,000 |
| Feb   | 1350    | 52    | $26,100 |
| Mar   | 980     | 78    | $23,400 |
...

## Context

SaaS product, $20/month subscription. Marketing spend was cut in March.

## Questions to Answer

1. Why did March performance drop?
2. Is churn rate concerning?
3. What should we prioritize?
```

## Notes

- Always state confidence level in conclusions
- Distinguish correlation from causation
- Round numbers appropriately for readability
- Visualizations help (describe charts if generating them)
- Business context changes interpretation
