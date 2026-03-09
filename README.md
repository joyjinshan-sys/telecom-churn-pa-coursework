# Telecom Customer Churn Prediction (Agent-Assisted, Reproducible Workflow)

## Project Summary
This project builds an end-to-end churn prediction solution for telecom customers, aligned to a six-stage ML workflow:
1. Problem framing
2. Exploratory data analysis
3. Data preparation
4. Model exploration and shortlisting
5. Threshold tuning and final evaluation
6. Final solution and limitations

Main notebook:
- `notebooks/telecom_churn_new.ipynb`

## Repository Structure
```text
New project/
├── data/
│   └── Telecom_customer churn.csv
├── notebooks/
│   └── telecom_churn_new.ipynb
├── results/
│   ├── splits/
│   ├── validation_results.csv
│   ├── test_metrics.csv
│   ├── decile_lift_table.csv
│   ├── calibration_curve.png
│   └── run_manifest.json
├── requirements.txt
├── environment.yml
└── README.md
```

## Environment
- Python 3.10+
- Install dependencies:

```bash
pip install -r requirements.txt
```

Or create a conda environment:

```bash
conda env create -f environment.yml
conda activate telecom-churn-pa
```

## Data
Expected data file:
- `data/Telecom_customer churn.csv`

Target variable:
- `churn` (binary: 0/1)

## How to Run
From project root:

```bash
cd notebooks
jupyter notebook telecom_churn_new.ipynb
```

In the notebook, run all cells top-to-bottom.

## Reproducibility Controls
- Fixed random seed (`RANDOM_SEED = 42`)
- Strict train/validation/test split discipline
- Train-only fit for all parameter-learning preprocessing steps
- Unified `Pipeline(preprocessor -> model)` for model training
- Validation-only threshold tuning, then locked test evaluation
- Run metadata and dataset fingerprint saved in `results/run_manifest.json`

## Outputs
After a full run, key outputs are generated in `results/`:
- `validation_results.csv`
- `test_metrics.csv`
- `decile_lift_table.csv`
- `calibration_curve.png`
- split artifacts in `results/splits/`

## Coursework Deliverables Mapping
- Report PDF: main narrative and results
- Code repository: this project directory
- Agent workflow evidence: appendices (usage log + decision register)

## Notes
- Keep relative paths unchanged to preserve grader portability.
- If metrics differ slightly across machines, this is expected due to minor environment-level numerical variation.
