# Galaxy Morphology Classification

This repository contains notebooks, analysis and artifacts used for building and evaluating convolutional neural networks to classify galaxy morphologies.

---
## Overview

- Goal: build, compare and evaluate CNN models to classify galaxy images into morphology classes.
- Notebooks include exploratory data analysis (EDA), dataset description, training and prediction notebooks.
- Large model weights, generated reports and bulky assets are intentionally excluded from source control (see `.gitignore`).

---
## Directory structure (files included in repo)

Below is the top-level structure of the repository 

- .gitignore                        (list of ignored files/dirs)
- 7_class_cnn.ipynb                 (7-class model training & experiments notebook)
- data_description.md               (dataset description and notes)
- eda.ipynb                         (exploratory data analysis notebook)
- requirements.txt                  (Python dependencies)

Files and directories intentionally excluded (examples from `.gitignore`):

- model weights (.keras files) and large checkpoints (e.g. `*.keras`)
- `figures/`, `graphs/`, `galaxy_morphology_arxiv/`, `images_training_rev1/`, `venv/`
- pre-generated reports such as `classification_reports.txt`, `model_performance_report.csv`
- auxiliary TeX build files (`main.aux`, `main.blg`, `main.log`, `main.out`)

If you need any of the excluded large files, contact the project owner(they were excluded to keep the repository lightweight).

---
## Quick start — run the notebooks

1. Create and activate a Python environment (recommended):

```bash
# create virtual environment
python3 -m venv .venv
source .venv/bin/activate

# install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

2. Start Jupyter Lab / Notebook in the repository folder and open the notebooks:

```bash
jupyter lab    # or: jupyter notebook
```

3. Suggested order to explore and reproduce results:

- `eda.ipynb` — run exploratory analyses and understand dataset distributions and transforms.
- `data_description.md` — read the dataset description and notes about classes, sources and preprocessing.
- `7_class_cnn.ipynb` — main training and evaluation notebook for the 7-class classification problem.

Notes:
- Notebooks assume the dataset files are available locally in the expected paths. Large image folders and models are excluded from the repo; update the paths in the notebooks if you placed datasets or model weights elsewhere.

---
## Dataset

Please visit this site and download 'images_training_rev1.zip' from [kaggle](https://www.kaggle.com/competitions/galaxy-zoo-the-galaxy-challenge/data?select=images_training_rev1.zip) and extract it and place it under the main project directory

See `data_description.md` for a full description of the dataset used, including:

- classes and labels
- number of samples per class
- preprocessing applied (resize, normalization, augmentation)
- recommended train/validation/test splits

If you want a compact workflow for a 5-class experiment (not provided as a separate notebook here), you can adapt the 7-class notebook by:

1. Filtering the dataset labels to the 5 target classes in the dataset loader cell.
2. Updating the model output units to `5` and adjusting the loss/metrics if needed.
3. Re-run the same training and evaluation cells (early stopping, checkpoints, and metrics logging).

---
## Notebooks and scripts

- `7_class_cnn.ipynb` — training loops, model definitions and evaluation for the 7-class problem.
- `eda.ipynb` — data exploration and visualizations used to inform modeling choices.
- `data_description.md` — human-readable dataset description and notes.

---
## Models and artifacts

Trained model weights and many report files are large and intentionally excluded by `.gitignore`. Examples of excluded artifacts:

- `*.keras` model weight files (e.g. `efficientnet_b0_7class_finetuned.keras`)
- `model_performance_report.csv`, `classification_reports.txt` and large figure directories

Please run the [code](7_class_cnn.ipynb) to run and save all the models.

---
## Metrics and evaluation

Primary evaluation metrics used in the project:

- Accuracy
- Precision, Recall and F1-score (per-class and macro-averaged)
- Confusion matrix
- ROC / PR curves (when applicable per class)

Typical evaluation workflow in the notebooks:

1. Save per-epoch metrics while training (loss, accuracy, val_loss, val_accuracy).
2. After training, generate predictions for the test set and compute the full classification report (precision/recall/F1) and confusion matrix.
3. Save a concise performance summary and per-class recall values to a report file (this repository excludes the report files — see `.gitignore`).

---
## Installation of libraries

The primary Python dependencies are recorded in `requirements.txt`. Install into an isolated venv or conda env.

Recommended quick setup:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

If you prefer conda:

```bash
conda create -n galaxy python=3.10
conda activate galaxy
pip install -r requirements.txt
```

---
## Reproducing training and evaluation

1. Ensure the dataset is placed where the notebooks expect (or edit the path variables in the notebook cells).
2. Open and run the cells from `eda.ipynb` then `7_class_cnn.ipynb`.
3. Use the provided checkpoints (if you have them locally) or train from scratch; training time depends on hardware.

Tips:
- Use GPU acceleration if available. Ensure CUDA and GPU drivers match the installed TensorFlow/PyTorch versions.
- For quick runs, reduce dataset size or train for fewer epochs.

---
## Contribution

- Possible additions:
  - Add a small `5_class_example.ipynb` that adapts the 7-class pipeline to 5 classes.
  - Add a notebook to predict on all the classes available without filtering.

---

