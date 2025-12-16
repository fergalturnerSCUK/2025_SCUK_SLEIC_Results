# SLEIC 2025 - Save the Children Results Analysis

This repository contains analysis and visualisations for the 2025 SLEIC project results. The analysis is high level presentation of learning results to support a short summary blog, published by Save the Children UK on the 17th December 2025.

## Overview

This analysis evaluates the impact of educational interventions on numeracy and literacy outcomes across multiple schools and providers using mixed-effects statistical models and time-series visualisations.

## Repository Structure

```
2025 Results Blog/
├── Code/
│   ├── Years of Schooling Equivalence Calculation.ipynb          # Analysis of Grade Effect on Numeracy
│   └── Summary Figures.ipynb                                     # Learning outcomes visualisations
├── Data/
│   ├── aser_baseline_clean.csv                                   # Numeracy assessment data
│   └── Learning Outcomes Summary.csv                             # Learning gains & mean scores for all providers and years (incomplete data)
└── Results/
    └── [Generated figures and visualisations]
```

## Analysis Files

### 1. Years of Schooling Equivalence Calculation.ipynb

**Purpose:** Analyzes the relationship between grade level and numeracy achievement using mixed-effects modeling.

**Key Methods:**
- Mixed-effects regression with random intercepts and random slopes for grade effects
- Z-score standardization of numeracy outcomes
- Specification tests for linearity assumptions
- School-level clustering analysis

**Key Findings:**
- **Grade Effect:** Each additional grade level is associated with a **0.347 SD increase** in numeracy scores (95% CI: 0.303–0.390, p<0.001)
- **Substantial School Clustering:** 43% of variance in numeracy scores is attributable to school effects (ICC = 0.433)
- **Individual-Level Variation:** 55% of variance is individual-level, while 2% reflects school-specific grade trajectories
- **Linearity:** Grade effects are approximately linear across grade transitions (SD of step sizes = 0.083)

**Outputs:**
- `numeracy_by_grade_and_age.png` - Visualization of grade and age effects on standardized numeracy scores
- Other findings described in Markdown in the notebook

### 2. Summary Figures.ipynb

**Purpose:** Visualises learning gains and mean scores across subjects, providers, and student demographics over a 3-year period.

**Key Analyses:**
- Time-series comparison of learning gains by provider (Years 1–3)
- Gender-disaggregated learning gains analysis
- Comparison of outcomes against performance targets
- Treatment vs. control school mean score trajectories

**Key Outputs:**
- `gains_by_provider.png` - Maths and English learning gains across providers
- `gains_by_sex.png` - Save the Children learning gains disaggregated by gender
- `gains_against_targets.png` - Achievement against final and interim targets by gender
- `meanscores_subject_year.png` - Treatment and control school trajectories

## Data Requirements

### aser_baseline_clean.csv
Numeracy assessment data including:
- Student characteristics: Age, Sex, Grade
- School identifiers (de-identified)
- Numeracy domain scores: Number Recognition, Addition, Subtraction, Multiplication, Division

### Learning Outcomes Summary.csv
Learning outcomes data including:
- Provider/LOT identifiers
- Year (1–3)
- Subject (English, Maths)
- Treatment group classification (Treatment/Control)
- Student demographics (All Students, Boys, Girls)
- Learning gains and mean scores

## Technical Stack

- **Python 3.x**
- **pandas** - Data manipulation and analysis
- **numpy** - Numerical computations
- **matplotlib & seaborn** - Visualization
- **statsmodels** - Mixed-effects regression and statistical testing

## Running the Analysis

### Prerequisites

Install required packages:

```bash
pip install pandas numpy matplotlib seaborn statsmodels
```

### Execution

1. Open `EYS Calculation.ipynb` in Jupyter Notebook or VS Code
   - Analyzes grade-level numeracy effects
   - Includes interpretation in the file, and outputs a single indicative figure

2. Open `Summary Figures.ipynb` in Jupyter Notebook or VS Code
   - Creates learning outcomes visualizations
   - Generates provider and gender-disaggregated figures

### Note on File Paths

Both notebooks use **relative paths** to reference data and output directories:
- Data files: `../Data/`
- Results folder: `../Results/`

This makes the analysis portable—no path modifications needed when sharing the entire folder structure.

## Key Insights

### Numeracy Progression
- Clear linear progression in numeracy scores across grades
- School-level factors explain ~43% of variation in student achievement
- Age and sex are significant predictors when controlling for grade

### Learning Outcomes
- Subject-specific gains vary considerably (maths vs. English)
- Gender disaggregation reveals differential outcomes by student demographics
- Multi-year trends indicate trajectory of intervention effectiveness

## Reproducibility

All analyses are fully reproducible:
- Data files are included in the repository
- Notebooks contain all code and commentary
- Random seed control (where applicable) ensures consistent results
- Figure outputs are saved to `Results/` folder

## Sharing & Collaboration

This folder is designed to be self-contained and portable:
- Relative paths ensure compatibility across different systems
- No external database dependencies
- All raw data included
- Generated figures integrated into the analysis notebooks

Simply zip the entire `2025 Results Blog` folder and share with collaborators.

## Contact & Questions

For questions about this analysis, please contact f.turner@savethechildren.org.uk
## Version History

**Last Updated:** December 16, 2025
