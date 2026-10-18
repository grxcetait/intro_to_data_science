# Length of Stay of Mental Health Inpatients in Scotland, 1997–2022

**Question:** How has the length of stay of mental health inpatients in Scottish hospitals changed between 1997/98 and 2021/22, and how does this vary with age, sex, diagnosis and readmission rates?

Group project for *Introduction to Data Science* (University of Edinburgh, 2023), analysing 25 years of Public Health Scotland open data in R.

## Key findings

![Average length of stay by financial year, with linear fit](figures/average-stay.png)

- **Average length of stay fell from about 40 days to about 31 days**, a decline of roughly half a day per year (linear model fitted to annual averages).
- **Short stays became more common and long stays less common** between 1997/98 and 2021/22.
- **The number of inpatients fell over the period**, despite population growth, consistent with the reported reduction in NHS mental health beds since 2010.
- **Readmission rates within 28 days fell until about 2007 and have risen since**, with a peak in 2020 that coincides with the COVID-19 pandemic.
- **Older age groups account for more inpatients** in every year studied.

## Methods

- Cleaned and reshaped 14 raw Public Health Scotland tables with `tidyverse`, filtering to Scotland-wide totals and the years of interest.
- Mapped ICD-10 diagnosis codes to readable diagnosis categories.
- Converted binned length-of-stay categories (e.g. "1–7 days") to midpoint values to estimate an annual average stay.
- Fitted a linear regression of average stay against year with `tidymodels`, and checked the residuals.
- Visualised trends with `ggplot2` and presented results as `xaringan` slides.

## Limitations

- Length of stay is only published in bins, so averages depend on the value assigned to each bin, particularly the open-ended "> 6 months" category.
- The tables share no common keys, so variables such as diagnosis could not be linked directly to length of stay.
- The analysis is descriptive: the trends are correlations, and the explanations offered (bed numbers, policy changes, COVID-19) are hypotheses rather than tested causes.

## Repository structure

```
├── analysis/          # Exploratory analysis (investigation.Rmd)
├── report/            # Final written report (report.Rmd + rendered HTML)
├── presentation/      # Slides (xaringan), with images and theme
├── data/              # Raw Public Health Scotland CSVs (see data/README.md)
├── figures/           # Key figures used in this README
└── ids-project.Rproj  # RStudio project file
```

## Reproducing the analysis

Requires R with `tidyverse`, `tidymodels`, `xaringan`, `xaringanthemer` and `palmerpenguins`:

```r
install.packages(c("tidyverse", "tidymodels", "xaringan", "xaringanthemer", "palmerpenguins"))
```

Open `ids-project.Rproj` in RStudio, then knit `report/report.Rmd` or `presentation/presentation.Rmd`.

## Data

Public Health Scotland, *Mental Health Inpatient Activity*, published on the [Scottish Health and Social Care Open Data platform](https://www.opendata.nhs.scot/dataset/mental-health-inpatient-activity) under the Open Government Licence.
