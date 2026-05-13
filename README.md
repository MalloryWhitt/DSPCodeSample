# DSPCodeSample

This repository contains a Colab notebook for a toxicity classification pipeline developed for the Digital Society Project (DSP), affiliated with the V-Dem Institute at the University of Gothenburg.

## Project Background

The Digital Society Project studies how digital media and online platforms affect democratic norms and institutions. This classifier is part of a broader effort to score political tweets on a scale of 0 to 10 based on how toxic they are with respect to democratic norms, across three categories: delegitimizing media institutions, undermining electoral integrity, and inciting political violence.

## What the Notebook Does

- Fine-tunes Cardiff NLP's `twitter-roberta-base-2022-154m` model on hand-labeled tweet data using a regression head to predict continuous toxicity scores
- Applies sample weighting based on rater confidence and categorical fit
- Evaluates performance using MAE, Pearson r, Spearman rho, and high-score MAE against a stratified holdout set
- Computes human inter-rater agreement as a performance ceiling

## Results

| Metric | Model | Human Baseline |
|---|---|---|
| MAE | 1.599 | 2.303 |
| Pearson r | 0.620 | 0.436 |
| Spearman rho | 0.612 | 0.456 |

The model outperforms the human baseline on all three metrics. 

Results should be interpreted with the caveat that the model was trained on a single rater's labels and learned a strong framework for this individual's understanding of toxicity rather than an "ideal" understanding. A subsequent model trained on survey data from a larger pool of raters will provide a stronger and more generalizable model.

## Data

The training data consists of hand-labeled tweets collected and annotated by the Digital Society Project. The data is proprietary and not included in this repository.

## Running the Notebook

The notebook is provided for review purposes only and cannot be run without access to the underlying dataset.
