# 📊 CEMA EDA: HIV Trends & Child Mortality Analysis

This project presents an exploratory data analysis (EDA) of global health indicators, focusing on HIV prevalence, neonatal mortality, and under-five mortality trends across countries and regions.

> NOTE: For an in-depth look into the analysis, click [here](https://kelvinziroh.github.io/cema-eda/)

## 🧠 Objectives

- Understand global and regional trends in HIV infections (2000–2023)
- Identify countries contributing most to the global HIV burden
- Explore patterns in neonatal and under-five mortality
- Prepare clean, structured datasets for downstream analysis and visualization

## 📦 Data Sources

- WHO Global Health Observatory (HIV data)
- Child mortality datasets
- Multidimensional poverty indicators

The analysis aligns with the broader mission of [Center for Epidemiological Modelling and Analysis (CEMA)](https://cema-africa.uonbi.ac.ke/), which emphasizes data-driven insights for public health decision-making.

## 🧹 Data Cleaning & Preparation

Key preprocessing steps included:

- Extracting numeric values from string-based ranges (e.g., `"320 000 [280 000 - 380 000]"`)
- Handling missing values:

  - Removed countries with no data across all years
  - Used forward-fill (`ffill`) and backward-fill (`bfill`) for partial gaps

- Reshaping data:

  - Pivoted years into columns for trend analysis

- Validated dataset integrity:

  - No duplicate records
  - Reduced noise from incomplete country entries

## 🔍 Key Insights

### 1. Data Coverage & Structure

- 194 countries initially; reduced after filtering missing-only records
- 8 time points: 2000, 2005, 2010, 2015, 2020–2023
- Significant proportion of missing or non-numeric raw entries required transformation

### 2. Global HIV Burden Concentration

- A relatively small subset of countries accounts for **~75% of global HIV cases**
- These countries dominate trend patterns and are critical for policy targeting

### 3. Regional Disparities

- HIV burden distribution varies significantly by WHO region
- Within each region, a few countries contribute the majority of cases
- Regional aggregation reveals different epidemic dynamics compared to global analysis

### 4. Data Quality Observations

- Some countries had **no data across all years** → excluded
- Others had **partial missing values**, especially at temporal edges
- Assumptions (e.g., interpreting `<500` as upper bounds) were necessary for consistency

### 5. Trend Behavior

- Longitudinal trends show:

  - Stabilization or decline in some high-burden countries
  - Persistent or growing burden in others
- Visualization of top contributors provides clearer insight than aggregate global plots

## 📈 Methodological Highlights

- Proportion-based analysis to identify major contributors
- Cumulative distribution approach to isolate top 75% burden
- Use of reshaping (pivot + melt) for flexible analysis
- Combination of global and regional perspectives

## ⚠️ Assumptions & Limitations

- String-encoded values required heuristic parsing
- Forward/backward filling may smooth real fluctuations
- Countries with sparse data were excluded, potentially biasing representation

