# Quantum-Kernel-Methods-for-Market-Regime-Detection-A-Comparative-Study-with-Classical-SVMs

**Quantum Kernel SVM for S&P 500 Market Regimes**

This project implements a Quantum Kernel Support Vector Machine (QSVM) to classify S&P 500 market regimes into Bull, Bear, and Sideways trends. It includes classical baselines (SVM and Random Forest) for comparison, feature engineering from historical stock data, and visualization of predictions.

**Features**

- Historical S&P 500 data download (2005–present) via yfinance

- Feature engineering:

       Returns, volatility, moving averages (20 & 200 days)

       RSI(14), MACD, ATR(14)

- Labeling market regimes:

       Bull, Bear, Sideways

       Option for strict labels (quantiles) or median-volatility rules

- Classical baselines:

      SVM (RBF kernel)

      Random Forest

      Quantum Kernel SVM:

- Balanced sampling per class

-Angle encoding + entangling feature map

- Lightning or default qubit simulator via PennyLane

- Visualization:

        Market regime timeline

        Confusion matrices

- Export features and labels to CSV

**Installation**
pip install yfinance pennylane scikit-learn pandas numpy matplotlib tqdm

**Usage**

#Download and preprocess data: The script automatically downloads S&P 500 data and calculates features.

#Classical model training: Runs SVM and Random Forest classifiers on scaled features.

#Quantum model training: Prepares a balanced quantum training set.

Computes quantum kernel matrix.
Trains QSVM using precomputed kernel.

Evaluation: Prints classification reports.

Plots market regime timeline and confusion matrices.

Export results: Features and labels saved to sp500_features_labels.csv.

**Configuration**

You can tweak the following parameters in the script:

Parameter	Description	Default
USE_STRICT_LABELS	Use strict quantile-based labeling	False
N_QUBITS	Number of qubits for quantum feature map	3
MAX_PER_CLASS	Max training samples per class for QSVM	150
MAX_TEST_Q	Max test samples for quantum kernel	200

**Dependencies**

Python 3.8+
yfinance
pennylane
scikit-learn
pandas
numpy
matplotlib
tqdm

**References**

PennyLane Documentation: https://pennylane.ai

S&P 500 historical data: Yahoo Finance (^GSPC)

**Notes**

Quantum kernel simulation may be slow for large training sets.

Recommended to use 2–4 qubits for speed and feasibility.

Classical baselines provide a comparison point to assess quantum model performance.
