# Mobile Price Classification — Machine Learning

An individual Machine Learning project comparing **K-Nearest Neighbors (KNN)** and **Decision Tree** classifiers to predict mobile phone price categories based on technical specifications.

## Dataset

- **2,000 mobile phones** with **20 numerical input features**.
- Four balanced price categories: Low (0), Medium (1), High (2), and Very High (3).
- Features include RAM, battery power, camera resolution, screen dimensions, and connectivity.
- **Source:** [Mobile Price Classification — Kaggle](https://www.kaggle.com/datasets/iabhishekofficial/mobile-price-classification).
- **Dataset file:** `train.csv`, included in this repository.

## Methodology

The project follows a supervised machine learning workflow:

1. **Exploratory Data Analysis (EDA):** Examined feature distributions, class balance, and correlations.
2. **Data Preprocessing:** Applied feature scaling using StandardScaler within a scikit-learn Pipeline.
3. **Data Splitting:** Divided the dataset into 80% training and 20% testing using stratified sampling (`random_state=42`).
4. **Model Training:** Implemented KNN and Decision Tree classifiers.
5. **Model Selection:** Selected the KNN hyperparameter using 5-fold stratified cross-validation on training data.
6. **Model Evaluation:** Compared performance using accuracy, confusion matrices, classification reports, and feature importance.

## Model Performance

| Model | 5-Fold CV Accuracy | Test Accuracy |
|---|---:|---:|
| K-Nearest Neighbors (K=26) | 59.38% | 63.75% |
| Decision Tree | 81.56% | **83.00%** |

The models were evaluated using cross-validation on the training data and a separate held-out test set. Preprocessing and model selection were performed using training-only procedures to prevent data leakage and support reliable evaluation.

### Key Findings

- **Decision Tree achieved the highest test accuracy of 83.00%.**
- RAM demonstrated a strong relationship with mobile phone price categories.
- Decision Tree performed better than KNN by prioritizing informative features.
- The models predict price categories rather than actual monetary prices.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## How to Run

1. Clone or download this repository.
2. Install Python 3.10 or later.
3. Install the required libraries:

   ```bash
   pip install -r requirements.txt
   ```

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `MobilePriceClassification_ML.ipynb`.
6. Select **Run All Cells** to execute the complete analysis.


## Conclusion

This project demonstrates the application of supervised machine learning techniques to a multiclass classification problem. By comparing KNN and Decision Tree classifiers, it highlights the importance of data preprocessing, appropriate model evaluation, and feature analysis in building reliable predictive models.
