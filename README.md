# mmm-demo-tutorial
# a

Toy Marketing Mix Model (MMM) pipeline used as a training example
for Git 101. It is **not** a real client project — inputs are
synthetic data.

## What it does

Reads weekly sales and media spend (TV, digital, OOH), applies a
geometric adstock transform to each channel, fits a linear
regression to estimate each channel's contribution to sales, and
writes the results and the trained model to disk.

## Structure

data/inputs/      # raw + scoring input CSVs (gitignored)
data/outputs/     # results + predictions CSVs (gitignored)
data/model/       # trained model .pkl (gitignored)
notebooks/        # exploration only: ingestion -> EDA -> feature eng -> modeling
utils/func.py     # production functions consumed by inference/predict.py
inference/predict.py # production inference script

## Setup

conda env create -f environment.yml
conda activate mmm-demo-tutorial

## Run

# exploration
jupyter lab notebooks/mmm_demo_pipeline.ipynb

# production inference
python inference/predict.py