# Synthetic Commercial Energy Cost Analysis

An exploratory Python notebook examining how modelled non-commodity electricity charges vary with annual consumption across a synthetic group of UK commercial consumers.

This is a scenario-modelling exercise. It does not use customer billing records and should not be treated as current tariff, tax or regulatory guidance.

## Question explored

If different electricity charges are represented as fixed, volume-based and demand-sensitive components, how does the total modelled cost change as annual consumption increases?

The notebook generates 80 synthetic consumers across six sectors, calculates assumed charge components, and compares linear and second-order polynomial fits.

## Workflow

```text
Seeded synthetic consumer profiles
    -> assumed charge-component formulas
    -> total and per-kWh cost calculation
    -> correlation analysis
    -> linear and polynomial regression
    -> sector and component visualisation
```

## Running the analysis

```bash
git clone https://github.com/SidhanthChavan/Commercial-Energy-Cost-Optimisation.git
cd Commercial-Energy-Cost-Optimisation
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook NCC_vs_Volume_Analysis.ipynb
```

The dataset is generated inside the notebook; no external CSV file is required.

## Interpreting the output

The observed relationships follow partly from the formulas used to generate the synthetic charges. Correlation and regression results therefore describe the simulated assumptions, not independently observed market behaviour.

The notebook also contains a historical assumption that renewable certificates remove Climate Change Levy. That assumption is not valid for current UK renewable electricity and must be corrected before the model is used for any contemporary analysis. The accompanying report is retained as the original project write-up and should be read with the same limitation in mind.

## Repository contents

```text
.
├── NCC_vs_Volume_Analysis.ipynb
├── Technical_Report_NCC_vs_Volume.docx
├── requirements.txt
└── LICENSE
```

## Stack

Python, Pandas, NumPy, SciPy, scikit-learn, Matplotlib and Seaborn.

## Licence

See [LICENSE](LICENSE).
