# Dairy Calf Feed Intake, Growth, and Feed Efficiency: An Exploratory Data Analysis

## Project Overview

Feed intake and body-weight development are important components of dairy calf management. Understanding how feeding patterns change during early life can help researchers investigate the relationship between nutritional intake, animal growth, and the development of feeding behavior during the preweaning period.

This project analyzes published dairy calf research data to explore patterns in feed intake and body-weight development under two treatment conditions: **Control** and **Hay**.

The analysis examines daily grain intake, hay intake, total mixed ration (TMR) intake, and weekly average body weight. It also investigates exploratory relationships between feed intake and body weight, with particular attention to the influence of calf age on these relationships.

The project uses Python for data preparation, data-quality assessment, descriptive statistics, visualization, and exploratory statistical analysis. It demonstrates how quantitative methods can be applied to animal science questions while recognizing the limitations of small datasets, repeated measurements, and observational comparisons.

The study data were obtained from a published dairy calf experiment by Downey et al. (2022). The original study included 22 calves, with 11 assigned to the Control group and 11 to the Hay group.

This project is an exploratory secondary-data analysis. It does not constitute a new feeding experiment, and its descriptive findings should not be interpreted as definitive evidence of treatment effects.

## Research Question

**How do feed intake and body weight change during the preweaning period in dairy calves, and how do the observed relationships between feed intake and body weight change after accounting for calf age?**

### Research Objectives

The analysis was designed to:

1. Examine weekly average body-weight trajectories for calves in the Control and Hay groups.
2. Describe daily grain intake patterns across calf age.
3. Examine changes in hay intake during the available measurement period.
4. Compare daily average TMR intake between the two treatment groups.
5. Explore the relationships between feed intake and body weight.
6. Compare original intake–weight correlations with correlations calculated after an exploratory adjustment for age.
7. Assess data completeness and identify limitations affecting the interpretation of the results.
8. Establish a reproducible workflow for exploring animal science research data using Python.

## Animal Science Background and Research Motivation

Calf growth and feeding behavior are related aspects of early-life animal development. Feed intake changes as calves mature, and body weight generally changes with age. Consequently, relationships observed between intake and body weight may partly reflect the shared influence of age.

This creates an important analytical challenge: a positive correlation between feed intake and body weight does not necessarily mean that higher intake independently explains greater body weight.

A useful exploratory analysis should therefore examine both variables over time and consider whether their relationship changes after accounting for age.

This project investigates that issue using published data on calf growth and feeding patterns. It also compares descriptive intake trajectories between treatment groups while recognizing that differences in observed averages do not, by themselves, establish statistically significant treatment effects.

The central scientific motivation is to understand what can—and cannot—be concluded from longitudinal animal science data when measurements are collected repeatedly from the same animals.

## Study Description

| Component | Description |
|---|---|
| Research subject | Dairy calves |
| Original study | Downey et al. (2022) |
| Number of calves | 22 |
| Control group | 11 calves |
| Hay group | 11 calves |
| Study focus | Feed intake and body-weight development |
| Main feeding measurements | Grain, hay, and TMR intake |
| Growth measurement | Body weight and average daily gain (ADG) |
| Analytical approach | Exploratory quantitative analysis |
| Programming environment | Python and Google Colab |

### Original Research Sources

- **Research dataset:** [Dryad repository — DOI 10.25338/B8V054](https://datadryad.org/dataset/doi:10.25338/B8V054)
- **Research article:** [Journal of Dairy Science — DOI 10.3168/jds.2021-21439](https://doi.org/10.3168/jds.2021-21439)

The original article and associated dataset should be consulted for the experimental design, treatment definitions, feeding protocols, measurement procedures, and the original authors' conclusions.

## Datasets Analyzed

Four main data components were used in the analysis.

### 1. Weekly Calf Body Weight and Average Daily Gain

The body-weight data were used to summarize growth patterns across the observation period.

Weekly average body weight was compared between the Control and Hay groups to visualize how the group-level trajectories developed over time.

The analysis also examined observed weight change and average daily gain (ADG), while distinguishing calculations made from the available body-weight endpoints from the ADG measure supplied by the original study.

Body weight is a growth measurement, whereas ADG expresses the rate of weight gain over a specified period. The two should not be treated as interchangeable measurements.

### 2. Daily Grain Intake

The grain-intake data were used to examine how average daily grain intake changed with calf age and differed between the two treatment groups.

The analysis focused on descriptive patterns, including increases, fluctuations, and differences between the group averages.

### 3. Daily Hay Intake

The hay-intake data were used to characterize changes in recorded hay consumption across the available observation period.

Because hay-intake measurements were not complete for every expected record, the available observations were interpreted with consideration of missing data.

### 4. Daily Total Mixed Ration Intake

The TMR dataset was used to compare average daily intake between the Control and Hay groups during the available measurement period.

The analysis focused on the pattern of observed group averages rather than treating individual daily comparisons as independent experimental replications.

### Measurement Units

Feed intake measurements were reported on a dry-matter basis in the source data. The visualizations express grain, hay, and TMR intake in grams of dry matter, while body weight is expressed in kilograms.

The source dataset's definitions should be consulted when interpreting the precise measurement intervals and aggregation procedures.

## Data Preparation and Quality Assessment

Data quality assessment was an important part of the analytical workflow because the datasets differed in measurement coverage and completeness.

The preparation process included:

- Loading and inspecting the research datasets.
- Examining dataset dimensions and column data types.
- Checking missing values and duplicate records.
- Reviewing treatment-group coverage.
- Examining the age ranges covered by each feeding dataset.
- Summarizing the available body-weight and intake measurements.
- Identifying differences in the completeness of the grain, hay, and TMR datasets.

### Missing Data

The following missingness figures were reported in the project analysis:

| Dataset | Reported missing records |
|---|---:|
| Grain intake | 8.33% |
| Hay intake | 23.01% |
| TMR intake | 20.33% |

These percentages describe missingness in the analyzed datasets as reported by the project. They should be interpreted in the context of each dataset's structure and expected measurement coverage.

Missing values were retained as missing rather than automatically imputed. This avoids introducing unobserved intake measurements without a justified imputation method.

However, the presence of missing data can affect the number of available observations and may influence the representativeness of calculated averages and correlations.

## Methods

The project was conducted in Python using Google Colab, with pandas for data manipulation, Matplotlib for visualization, and SciPy for exploratory statistical procedures.

### 1. Data inspection

Each dataset was loaded and inspected to understand its structure, variables, treatment coverage, and age range.

### 2. Data-quality checks

The analysis examined missing values, duplicate records, column types, and differences in observation coverage across datasets.

### 3. Descriptive growth analysis

Body-weight observations were summarized by treatment and week to examine the development of average body weight over time.

Observed weight change was also examined to describe the overall growth recorded during the relevant observation period.

### 4. Feed-intake visualization

Daily average grain, hay, and TMR intake were plotted against calf age.

These visualizations were used to identify broad patterns and fluctuations in feeding measurements rather than to establish causal treatment effects.

### 5. Treatment-group comparison

Daily average TMR intake was compared descriptively between the Control and Hay groups during the 13 days examined.

The comparison focused on the direction and magnitude of observed group-level differences. Daily averages alone do not provide a valid estimate of statistical significance because the same animals may contribute observations over multiple days.

### 6. Correlation analysis

Exploratory correlations were calculated between feed intake and body weight.

The analysis compared the original intake–weight correlations with correlations obtained after an exploratory residual-based adjustment for age.

This comparison was intended to investigate whether age could explain part of the association between feed intake and body weight.

### 7. Interpretation of results

The results were interpreted with attention to sample size, missing observations, repeated measurements, differences in measurement periods, and the distinction between descriptive associations and causal conclusions.

## Visual Results and Interpretation

The following figures summarize the main visual outputs of the project.

### Figure 1. Weekly Average Calf Body Weight by Treatment

![Line chart showing weekly average calf body weight for the Control and Hay groups over weeks 0–8.](figures/weekly_average_calf_weight.png)

*Figure 1. Weekly average body weight of dairy calves in the Control and Hay groups.*

The figure shows an overall increase in average body weight across the observation period in both treatment groups.

The two trajectories are broadly similar, although the relative positions of the group averages vary across weeks. The Hay group has slightly higher averages at several intermediate observations, while the Control group has a higher average at the final plotted week.

These patterns describe the observed group averages. They do not establish whether the differences are statistically significant or whether the feeding treatment caused them.

A rigorous treatment-effect assessment would need to account for the experimental design, the individual calf as the experimental unit, repeated observations, and the appropriate statistical model.

### Figure 2. Daily Average Grain Intake by Treatment

![Line chart showing daily average grain intake for the Control and Hay groups across calf age.](figures/daily_grain_intake_by_treatment.png)

*Figure 2. Daily average grain intake, measured as grams of dry matter, by treatment group across calf age.*

Average grain intake generally increases with calf age in both groups, although the daily averages fluctuate throughout the observation period.

The two trajectories follow broadly similar upward patterns, with differences in their relative positions at various ages. Greater separation between the group averages is visible in some of the later observations.

The figure illustrates the importance of considering age when comparing intake between groups. Intake changes substantially over time, so an unadjusted comparison may combine age-related changes with potential treatment-related differences.

Because the figure presents group averages, it also does not reveal the full distribution of intake among individual calves.

### Figure 3. Daily Average Hay Intake

![Line chart showing daily average hay intake in grams of dry matter across calf age.](figures/daily_average_hay_intake.png)

*Figure 3. Daily average hay intake during the available measurement period.*

The figure shows an overall upward trajectory in recorded hay intake, accompanied by day-to-day fluctuations.

The final plotted observation is noticeably higher than the preceding observations. This value warrants careful interpretation rather than automatic treatment as a typical daily intake level.

The available data do not establish whether the increase reflects a sustained change, an individual observation, or another feature of the measurement process.

Missing measurements and the limited number of calves also affect the interpretation of the daily averages.

### Figure 4. Daily Average TMR Intake by Treatment

![Line chart comparing daily average total mixed ration intake between the Control and Hay groups during the measurement period.](figures/daily_tmr_intake_by_treatment.png)

*Figure 4. Daily average TMR intake, measured as grams of dry matter, by treatment group during the available measurement period.*

The TMR figure shows an overall increase in average intake in both treatment groups, with fluctuations across the measurement period.

The Hay group has a higher observed daily average than the Control group on 12 of the 13 days examined, according to the reported project results.

This is a descriptive comparison of the plotted daily averages. It should not be interpreted as proof that the Hay treatment increased TMR intake.

A formal treatment comparison would need to account for individual-level variation, repeated observations, the original experimental design, and the availability of valid measurements for each animal and day.

## Key Findings

The following findings summarize the results reported by the exploratory analysis.

### 1. Body weight increased in both groups

Mean body weight increased over the study period for both the Control and Hay groups.

The observed average weight change was approximately 41.4 kg for the Control group and 41.8 kg for the Hay group.

These are descriptive endpoint-based changes. The small difference between these group summaries should not be interpreted as evidence of a treatment effect without an appropriate statistical comparison.

### 2. Grain intake generally increased with age

Average grain intake followed an overall upward trajectory in both groups, although daily means fluctuated.

This pattern illustrates the importance of considering age when studying the relationship between feed intake and growth.

### 3. Hay intake increased over its observation period

The recorded hay-intake averages generally increased during the measurement period.

The data also contained missing observations, so the pattern should be interpreted in the context of the available records rather than assumed to represent complete measurements for every calf on every day.

### 4. TMR intake was descriptively higher in the Hay group on most observed days

The Hay group had a higher observed daily average TMR intake than the Control group on 12 of the 13 days examined.

This finding describes the observed averages and does not establish that the treatment caused higher intake or that the difference was statistically significant.

### 5. Original intake–weight correlations weakened after age adjustment

Grain and hay intake had positive original correlations with body weight. These correlations were weaker after the exploratory residual-based adjustment for age.

The age-adjusted TMR intake–weight correlation was close to zero.

These results suggest that age may account for part of the association observed between some intake measurements and body weight.

However, the residual-based approach is exploratory and does not fully account for the repeated-measures structure of the data. The resulting correlations should not be interpreted as definitive estimates of independent relationships.

### 6. Missing data differed across feeding datasets

Missing records were reported for grain, hay, and TMR intake, with the highest reported percentage in the hay dataset.

Differences in missingness and age coverage can affect comparability across the feeding analyses.

### Summary of Findings

| Research component | Reported finding | Interpretation |
|---|---|---|
| Body weight | Increased in both groups | Both groups showed overall growth during the observation period |
| Endpoint weight change | Approximately 41.4 kg for Control and 41.8 kg for Hay | Descriptive group summaries, not a treatment-effect estimate |
| Grain intake | Generally increased with age | Intake patterns were age-dependent and fluctuated daily |
| Hay intake | Generally increased during the available period | Missing observations should be considered |
| TMR intake | Hay group average was higher on 12 of 13 days | Descriptive difference requiring appropriate statistical evaluation |
| Grain and hay correlations | Weaker after age adjustment | Age may explain part of the original association |
| TMR correlation | Age-adjusted correlation close to zero | Little linear association remained in the exploratory age-adjusted calculation |
| Missing data | Present in all three intake datasets | Data completeness differed across feeding measurements |

## Scientific Interpretation

### Why age matters when studying feed intake and growth

Calf age is closely related to both body weight and feeding patterns. As calves mature, body weight generally increases, and intake measurements may change as well.

Consequently, a positive correlation between intake and body weight can arise partly because both variables change with age.

An age-adjusted analysis can help explore whether the association remains after accounting for an age-related pattern. However, the interpretation depends on the adjustment method, the data structure, and the statistical assumptions.

In this project, the weaker correlations after the exploratory age adjustment suggest that the original relationships should not be interpreted without considering age.

### Why group averages are not enough to establish treatment effects

Averages are useful for visualizing overall patterns, but they can conceal individual differences among calves.

Moreover, repeated measurements from the same calf are not statistically independent. Measurements taken from one animal across several days or weeks are usually more closely related to one another than measurements taken from different animals.

Therefore, the number of daily measurements should not be treated as though it represents an equivalent number of independent experimental animals.

A formal treatment-effect analysis should use the individual calf as the experimental unit and account for repeated observations and the original study design.

### Why the findings should remain exploratory

The analysis uses a relatively small sample of 22 calves, and the feeding datasets differ in age coverage and missingness.

These constraints limit the strength of conclusions that can be drawn from correlations and descriptive treatment comparisons.

The project is most appropriately interpreted as an exploratory examination of published animal science data that identifies patterns and motivates further analysis.

## Limitations

Several limitations affect the interpretation of the results.

### 1. Small sample size

The original study included 22 calves, with 11 animals in each group.

Although repeated observations provide information about changes over time, they do not increase the number of independent experimental animals.

### 2. Repeated measurements

The same calves contributed measurements over multiple time points. Treating all daily or weekly observations as independent would underestimate the dependence within animals and could lead to inappropriate statistical inference.

The exploratory correlation analysis does not fully account for this repeated-measures structure.

### 3. Missing feeding measurements

Missing values were present in all three feeding datasets:

- Grain intake: 8.33%.
- Hay intake: 23.01%.
- TMR intake: 20.33%.

Missingness can affect the number of observations contributing to each daily average and each correlation.

The analysis retained missing values rather than automatically imputing them, but this does not eliminate potential bias associated with incomplete observations.

### 4. Different observation periods

The grain, hay, and TMR datasets cover different age ranges.

Consequently, direct comparisons between the intake variables should consider differences in measurement coverage and the stage of calf development represented.

### 5. Exploratory age adjustment

The residual-based adjustment was used to investigate whether age influenced the intake–weight correlations.

It is not a substitute for a longitudinal model that appropriately represents individual animals, treatment allocation, repeated observations, and potential non-linear age effects.

### 6. Descriptive treatment comparisons

Differences between plotted treatment-group averages do not independently establish statistical significance or causal treatment effects.

Formal comparisons should follow the original study design and use appropriate animal-level statistical models.

### 7. Average daily gain definitions

The endpoint-based ADG calculation used in this project differs from the study-provided ADG measure.

These quantities may represent different calculation periods or definitions and should not be compared as though they were identical without examining the original study's methods.

### 8. Secondary-data analysis

This project uses data from a published study rather than independently collected experimental measurements.

Interpretation should remain consistent with the original study's design, measurement procedures, and documented limitations.

## Future Research Directions

The current analysis provides a foundation for several possible extensions.

### 1. Longitudinal modeling of calf growth

Use an appropriate repeated-measures or mixed-effects model to examine body-weight trajectories while accounting for individual differences between calves.

### 2. Treatment-by-age analysis

Investigate whether growth trajectories differ between treatments over time using a model that reflects the original experimental design.

### 3. Age-adjusted feeding relationships

Examine intake–weight associations using methods that account for non-linear age patterns and repeated measurements within animals.

### 4. Missing-data assessment

Investigate whether missing intake records are associated with treatment, age, or other observed variables and evaluate how missingness may affect the results.

### 5. Comparison with original study findings

Compare the exploratory outputs with the published article's statistical analyses to distinguish descriptive patterns reproduced in this project from conclusions supported by the original experimental analysis.

### 6. Feed efficiency analysis

If the available data and original study definitions support it, investigate an appropriate measure of feed efficiency or feed conversion. Such analysis would require clearly defined intake and growth intervals and a suitable statistical approach.

These are potential extensions, not completed analyses or established findings of this project.

## Tools and Technologies

The analysis used the following tools:

- **Python:** General-purpose data analysis and scientific computing.
- **pandas:** Data manipulation, data inspection, and summary calculations.
- **Matplotlib:** Visualization of calf growth and feeding patterns.
- **SciPy:** Exploratory statistical procedures.
- **Google Colab:** Notebook-based analysis and execution.
- **GitHub:** Project documentation, version control, and portfolio presentation.

These tools support the investigation of animal science questions. The primary focus of the project is calf growth, feeding patterns, and the interpretation of nutritional and growth measurements.

## Repository Structure

The repository should separate the analytical notebook, source or prepared data, figures, and exported results.

```text
dairy-calf-feed-intake-growth-analysis/
├── data/
│   └── [prepared research datasets]
├── figures/
│   ├── weekly_average_calf_weight.png
│   ├── daily_grain_intake_by_treatment.png
│   ├── daily_average_hay_intake.png
│   └── daily_tmr_intake_by_treatment.png
├── notebooks/
│   └── [analysis notebook]
├── results/
│   └── feed_intake_weight_correlations.csv
├── requirements.txt
├── LICENSE
└── README.md
```

*Note: Bracketed entries are illustrative placeholders. Replace them with the actual filenames in your repository before publication.*

### Exported Results

#### `feed_intake_weight_correlations.csv`

This file contains the reported comparison of feed-intake and body-weight correlations before and after adjustment for age.

Its intended purpose is to:

- Summarize the relationships between grain, hay, and TMR intake and body weight.
- Compare original correlations with exploratory age-adjusted correlations.
- Record sample sizes and statistical results generated by the analysis.

These results should be interpreted as exploratory because the correlations do not fully account for repeated observations from the same calves.

## Reproducibility

Reproducibility allows readers to inspect how the published data were processed and how the reported figures and statistical outputs were generated.

The repository is intended to contain the analytical notebook, relevant data files or documented data-access instructions, exported results, figures, and dependency information.

### Steps to reproduce the analysis

1. Clone or download the repository.
2. Access the published data from the [Dryad dataset](https://datadryad.org/dataset/doi:10.25338/B8V054).
3. Open the analytical notebook in Google Colab or a compatible Jupyter environment.
4. Follow the notebook's data-loading and preparation instructions.
5. Install the dependencies specified in `requirements.txt`.
6. Execute the notebook cells in sequence.
7. Compare the generated visualizations and statistical outputs with the exported results.

Successful reproduction depends on the actual notebook, file paths, dependency versions, and procedures documented in the repository.

## Conclusion

This project explores dairy calf growth and feeding patterns using published animal science research data.

The analysis documents increasing average body weight in both treatment groups, generally increasing grain and hay intake across the available measurement periods, and higher observed TMR intake averages in the Hay group on most of the examined days.

It also investigates how relationships between feed intake and body weight change after an exploratory adjustment for age. The weaker age-adjusted grain and hay correlations, together with the near-zero age-adjusted TMR correlation, highlight the importance of considering age when interpreting intake–weight relationships.

The findings remain descriptive and exploratory. The small number of calves, repeated measurements, missing feeding observations, and limitations of the age-adjustment approach prevent the results from being interpreted as definitive treatment effects.

Overall, the project demonstrates how quantitative methods can be applied to animal science data while maintaining attention to data quality, longitudinal structure, and scientific interpretation. It contributes to my developing research portfolio in animal science, livestock production, and agricultural data analysis.

## About the Author

**Richard Antwi**

BSc in Agriculture, majoring in Animal Science

Research interests include animal nutrition, livestock growth and production, sustainable agricultural systems, and quantitative approaches to agricultural research.

This project forms part of my agricultural research portfolio, which applies data preparation, statistical analysis, and visualization to questions concerning animal growth, feeding patterns, and agricultural productivity.

---

**Data source:** Downey et al. (2022), published dairy calf research dataset.

**Research subject:** Dairy calf growth and feed intake.

**Analytical approach:** Exploratory secondary-data analysis.

*This repository documents an independent exploratory analysis of published research data. The findings should be interpreted in the context of the original experimental design and the limitations described above.*
