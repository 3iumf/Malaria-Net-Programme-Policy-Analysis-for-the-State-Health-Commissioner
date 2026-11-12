# Malaria Net Programme: Policy Analysis for the State Health Commissioner

A statistical analysis of a household survey (600 households, 3 Local Government Areas) to advise the State Health Commissioner on whether a malaria bed-net programme should be scaled up statewide.

Built as the Statistics policy project for the AI Engineering programme at Ayonaire Academy.

## The question

Is the programme working, and should the state expand it? The programme's targets are **80% net use** and an average haemoglobin of **11.5 g/dL**.

## Dataset

`malaria_programme_data.csv`: 600 households, 200 in each of LGA A, B and C.

| Column | Meaning |
|---|---|
| `household_id` | Unique household ID |
| `lga` | Local Government Area (A, B, C) |
| `programme` | Whether the household is in the programme (Yes/No) |
| `uses_net` | Whether the household uses a net (Yes/No) |
| `haemoglobin` | Haemoglobin level (g/dL) |
| `clinic_visits` | Number of clinic visits |
| `days_malaria_free` | Days until the next malaria episode |
| `distance_km` | Distance to the nearest clinic (km) |

## Methods

- **Descriptive statistics:** mean, variance, quartiles, IQR outlier fences, skewness, histograms
- **Probability distributions:** binomial, Poisson, exponential
- **Sampling and the Central Limit Theorem**
- **Hypothesis tests:** one-sample z-test (net use against the 80% target), Welch two-sample t-test (haemoglobin, programme vs non-programme), chi-square test of independence
- **Confidence intervals** for proportions and means
- **Effect size** (Cohen's d), Type I/II errors, statistical vs practical significance

## Key findings

- **Net use is below target:** 55.5% of households use a net (95% CI 51.5% to 59.5%), well short of 80%.
- **The programme raises net use:** 69.8% in programme households vs 41.6% in others.
- **LGA C lags:** 47% net use vs 55% (A) and 64.5% (B). Even among programme households, C reaches 59% vs 73% and 77%.
- **Haemoglobin benefit is small:** +0.25 g/dL (95% CI 0.003 to 0.49, Cohen's d = 0.16, p = 0.047). Average haemoglobin overall is 11.05 g/dL, below the 11.5 benchmark.
- **Supporting pattern:** programme households go about 125 days before the next episode vs about 88 for others (exploratory).

## Recommendation

Fix first, then scale. Target delivery and uptake in LGA C, bring non-participating households in, and run a better-designed evaluation before statewide expansion. See the full brief in `Policy_Brief_Malaria_Programme.pdf`.

## Limitations

- Only 3 LGAs, so results may not generalise statewide
- Households were not randomly assigned, so findings show association, not proven cause
- The haemoglobin result is borderline and the effect is small
- One-time survey with no before/after data

## Repository contents

```
├── malaria_policy_project.ipynb          # Full analysis notebook
├── malaria_programme_data.csv            # Survey data
├── Policy_Brief_Malaria_Programme.pdf    # 2-page brief for the Commissioner
└── README.md
```

## How to run

```bash
pip install pandas numpy scipy matplotlib jupyter
jupyter notebook malaria_policy_project.ipynb
```

## Author

**Kingsley Nwaginineme**, AI Engineer trainee, Ayonaire Academy
