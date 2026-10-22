# Dairy Calf Feed Intake, Growth and Feed Efficiency Analysis

## Project Overview

This project explores changes in feed intake and body weight among dairy calves during the preweaning period. Using published research data, the analysis examines daily grain, hay, and total mixed ration (TMR) intake, calf growth, and exploratory relationships between feed intake and body weight.

The project demonstrates an agricultural data science workflow using Python, including data quality checks, descriptive statistics, data visualization, and correlation analysis.

## Research Question

How do feed intake and body weight change during the preweaning period in dairy calves, and what relationships can be observed between feed intake and body weight after accounting for age?

## Data Source

The data are from a published dairy calf study by Downey et al. (2022).

- **Research dataset:** [Dryad repository](https://datadryad.org/dataset/doi:10.25338/B8V054)
- **Research article:** [Journal of Dairy Science](https://doi.org/10.3168/jds.2021-21439)

The study included 22 calves: 11 in the Control group and 11 in the Hay group.

## Datasets Analyzed

Four datasets were used in the main analysis:

- **Grain intake:** Daily grain intake measurements from approximately birth through weaning.
- **Hay intake:** Daily hay intake measurements for calves in the Hay treatment group.
- **TMR intake:** Daily total mixed ration intake measurements during the weaning period.
- **Weekly calf weights and ADG:** Body weight measurements and the study-provided average daily gain data.

Feed intake measurements are reported on a dry matter basis in the source data.

## Methods

The analysis used Python and pandas to:

1. Load and inspect the research datasets.
2. Check dataset dimensions, column types, missing values, duplicate records, treatment coverage, and age ranges.
3. Summarize body weight and observed weight change by treatment.
4. Examine daily grain, hay, and TMR intake patterns across age.
5. Compare daily mean TMR intake between treatment groups.
6. Explore correlations between feed intake and body weight.
7. Examine how the intake–weight correlations change after adjusting for age using a residual-based exploratory approach.

Matplotlib was used to create visualizations. SciPy was used for exploratory statistical tests.

## Key Findings

- Mean body weight increased across the study period in both treatment groups.
- Mean observed weight change was approximately 41.4 kg for Control calves and 41.8 kg for Hay calves.
- Grain intake generally increased with age, although daily means fluctuated.
- Hay intake generally increased during its measurement period.
- Mean TMR intake generally increased during weaning. The Hay group had a higher observed daily mean than the Control group on 12 of the 13 days examined.
- Grain and hay intake had positive original correlations with body weight. These correlations were weaker after adjusting for age using the exploratory residual-based method.
- The age-adjusted TMR intake–weight correlation was close to zero.
- Missing intake values were present in all three feed datasets: 8.33% of grain records, 23.01% of hay records, and 20.33% of TMR records.

These findings describe the available observations and should not be interpreted as proof that hay provision caused differences in feed intake or growth.

## Limitations

- The study included only 22 calves.
- Measurements were repeated for individual calves over time and are not statistically independent.
- Feed datasets cover different age ranges and have different amounts of missing data.
- The exploratory correlation calculations do not fully account for repeated measurements within calves.
- Daily treatment comparisons are descriptive and do not establish causal effects.
- The endpoint-based average daily gain calculated in this project differs from the study-provided ADG measure.
- Missing intake values were retained as missing rather than automatically imputed.

## Tools and Skills Demonstrated

- Python
- pandas
- Matplotlib
- SciPy
- Data cleaning and quality assessment
- Descriptive statistics
- Exploratory correlation analysis
- Agricultural research data interpretation
- Reproducible analysis with Google Colab and GitHub

## Conclusion

This project demonstrates how published animal science data can be organized and explored using Python. It identifies descriptive patterns in calf growth and feed intake while acknowledging data limitations and the importance of accounting for age and repeated measurements when interpreting relationships.

The notebook documents the analysis workflow and provides a foundation for more advanced longitudinal modeling of animal growth and feed intake.
## Exported Results

### `feed_intake_weight_correlations.csv`

This file contains the summary comparing feed intake and calf body weight correlations before and after adjusting for age.

**Purpose:**
- Summarizes the relationship between feed intake and body weight for grain, hay, and total mixed ration (TMR).
- Compares the original correlations with age-adjusted correlations.
- Records the sample sizes and statistical results produced by the analysis.

**Important limitation:** These are exploratory correlations based on repeated observations from the same calves. They should not be interpreted as proof of causation or as definitive treatment effects.
