# Data

All files are from Public Health Scotland's [Mental Health Inpatient Activity](https://www.opendata.nhs.scot/dataset/mental-health-inpatient-activity) dataset (financial years 1997/98 to 2021/22), used under the Open Government Licence.

Geographic codes: `HBT`/`HBR` are health board of treatment/residence; `S92000003` is Scotland as a whole. Columns ending in `QF` are quality flags.

| File | Contents | Used in report |
|---|---|---|
| `...-length-of-stay.csv` | Number of stays by length-of-stay band | Yes |
| `...-age-sex.csv` | Patients and discharges by age group and sex | Yes |
| `...-diagnosis-trend.csv` | Patients by ICD-10 diagnosis group | Yes |
| `...-readmissions.csv` | % readmitted within 28 and 133 days | Yes |
| `icd10-lookup.xlsx` | ICD-10 code descriptions | Reference |
| `...-scotland-trend.csv` | Scotland-wide admissions, discharges, stays, patients | No |
| `...-health-board-trend.csv` | The same, by health board | No |
| `...-hospital-trend.csv` | The same, by hospital | No |
| `...-cross-boundary-flow.csv` | Patients treated outside their home health board | No |
| `...-deprivation.csv` | Activity by deprivation quintile (SIMD) | No |
| `...-geography.csv` | Rates by council area | No |
| `...-discharge-types-scot.csv` | Discharge types, Scotland | No |
| `...-discharge-types-hb.csv` | Discharge types, by health board | No |
| `...-rii.csv` | Relative index of inequality | No |
