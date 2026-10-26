# Mobile Price Classification — Machine Learning

A reproducible individual coursework project comparing **K-Nearest Neighbors (KNN)** and **Decision Tree** classifiers to predict a phone’s price *category* (0–3) from its specifications.

## Dataset
- **2,000** labeled phones; **20** numerical input features; **four balanced classes** (500 records each).
- Source: [Mobile Price Classification on Kaggle](https://www.kaggle.com/datasets/iabhishekofficial/mobile-price-classification).
- Dataset filename: `train.csv` (download from the source and place beside the notebook). The dataset is not included in this starter package; check its license before redistributing.

## Methods
- Exploratory analysis: class distributions, feature correlations, and plots.
- 80/20 stratified train/test split (`random_state=42`).
- KNN with `StandardScaler` inside a scikit-learn `Pipeline`. K (1–30) selected using 5-fold stratified CV **on training data only**.
- Decision Tree (default depth) fitted on training data.
- Accuracy, confusion matrices, classification report, and feature importance.

## Results

| Model | 5-fold CV on training set | Held-out test accuracy |
|---|---:|---:|
| KNN (`k=26`) | 59.38% | 63.75% |
| Decision Tree | 81.56% | **83.00%** |

Results were reproduced using the supplied `train.csv` and the procedure above. The older assignment report used different preprocessing and model-selection steps, so its reported CV numbers should **not** be treated as directly comparable. KNN's 59.38% figure is a post-selection training-set CV summary; the GridSearchCV tuning score should not be treated as an unbiased estimate of generalization. The held-out test set is used once for final comparison.

**Key insight:** RAM is strongly associated with the target price category in this dataset, and the Decision Tree performed better than KNN under this experiment. These are dataset-specific results and do not predict actual currency prices.

## Run locally
1. Install Python 3.10+ and create a virtual environment (recommended).
2. Install dependencies: `pip install -r requirements.txt`.
3. Download `train.csv` from the Kaggle dataset linked above and place it in this directory.
4. Launch `jupyter notebook`, open `MobilePriceClassification_ML.ipynb`, and choose **Run All**.

## Repository files
- `MobilePriceClassification_ML.ipynb` — cleaned, reproducible notebook.
- `requirements.txt` — Python dependencies.
- `README.md` — project overview and usage instructions.

## Scope
Educational ML classification project, originally completed as an individual assignment and revised for reproducibility. No web app or production deployment is claimed.
