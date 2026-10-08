# Diabetes Prediction using Artificial Neural Network

This project uses an **Artificial Neural Network (ANN)** to predict whether a person is likely to have diabetes based on medical and diagnostic features.

The project also compares different **activation functions** and **optimizers** to understand their effect on model performance.

## Project Workflow

```text
Diabetes Dataset
       ↓
Exploratory Data Analysis
       ↓
Train / Validation / Test Split
       ↓
Feature Scaling
       ↓
Artificial Neural Network
       ↓
Early Stopping
       ↓
Model Evaluation
       ↓
Activation Function Comparison
       ↓
Optimizer Comparison
```

## Dataset

The project uses the **Pima Indians Diabetes Dataset**.

The target column is:

* `Outcome` → 0 = No Diabetes
* `Outcome` → 1 = Diabetes

The input features include:

* Pregnancies
* Glucose
* BloodPressure
* SkinThickness
* Insulin
* BMI
* DiabetesPedigreeFunction
* Age

The notebook expects the dataset file to be named:

```text
diabetes.csv
```

## Exploratory Data Analysis

The notebook performs:

* Dataset inspection
* Missing-value checking
* Correlation analysis
* Correlation heatmap
* Feature distributions
* Glucose vs Outcome analysis
* BMI vs Outcome analysis

## Data Preprocessing

The dataset is divided into:

* 70% Training data
* 15% Validation data
* 15% Test data

The split uses:

```python
random_state=42
```

and stratification is applied to maintain the class distribution.

### Feature Scaling

`StandardScaler` is used to standardize the input features.

The scaler is fitted only on the training data and then applied to the validation and test sets.

## ANN Architecture

The neural network uses the following architecture:

```text
Input Layer
     ↓
Dense(16) + ReLU
     ↓
Dropout(0.2)
     ↓
Dense(8) + ReLU
     ↓
Dense(1) + Sigmoid
```

### Training Configuration

* Optimizer: Adam
* Learning Rate: 0.001
* Loss Function: Binary Crossentropy
* Batch Size: 32
* Maximum Epochs: 150
* Early Stopping Patience: 15

## Model Evaluation

The model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC

### Initial ANN Results

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 81.03% |
| Precision | 77.14% |
| Recall    | 65.85% |
| F1-Score  | 71.05% |
| ROC-AUC   | 89.17% |

## Activation Function Comparison

Different activation functions were tested.

| Activation Function |   Accuracy | Precision | Recall |   F1-Score |    ROC-AUC |
| ------------------- | ---------: | --------: | -----: | ---------: | ---------: |
| Sigmoid             |     81.90% |    77.78% | 68.29% |     72.73% |     90.37% |
| ReLU                | **90.52%** |    89.47% | 82.93% | **86.08%** | **95.25%** |
| Tanh                |     83.62% |    78.95% | 73.17% |     75.95% |     90.89% |
| Leaky ReLU          |     86.21% |    83.78% | 75.61% |     79.49% |     92.00% |

### Best Activation Function

**ReLU** achieved the best overall performance:

* Accuracy: **90.52%**
* F1-Score: **86.08%**
* ROC-AUC: **95.25%**

## Optimizer Comparison

The project also compares different optimization methods.

| Optimizer              |   Accuracy |  Precision | Recall |   F1-Score |    ROC-AUC |
| ---------------------- | ---------: | ---------: | -----: | ---------: | ---------: |
| Batch Gradient Descent |     79.31% |     74.29% | 63.41% |     68.42% |     86.41% |
| SGD                    | **89.66%** |     89.19% | 80.49% | **84.62%** |     94.57% |
| Mini-Batch GD          |     79.31% |     75.76% | 60.98% |     67.57% |     87.28% |
| Momentum               |     88.79% |     88.89% | 78.05% |     83.12% |     94.34% |
| RMSprop                |     88.79% |     88.89% | 78.05% |     83.12% |     93.14% |
| Adam                   |     86.21% | **90.32%** | 68.29% |     77.78% | **94.93%** |

### Best Optimizer

Based on F1-Score:

**SGD → 84.62% F1-Score**

Based on ROC-AUC:

**Adam → 94.93% ROC-AUC**

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* TensorFlow / Keras
* Jupyter Notebook

## How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Diabetes-Prediction
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the environment

**Windows:**

```bash
.venv\Scripts\activate
```

**Linux/macOS:**

```bash
source .venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Start Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook and run the cells.

## Project Structure

```text
Diabetes-Prediction/
│
├── pima-indians-diabetes-database(1).ipynb
├── diabetes.csv
├── README.md
├── requirements.txt
└── .gitignore
```

## Key Learning Outcomes

This project demonstrates:

* Exploratory Data Analysis
* Data preprocessing
* Train/validation/test splitting
* Feature standardization
* Artificial Neural Networks
* Dense layers
* Dropout
* Activation functions
* Binary classification
* Binary crossentropy
* Early stopping
* Gradient descent
* SGD
* Momentum
* RMSprop
* Adam
* Model evaluation and comparison

## Disclaimer

This project is intended for **educational and machine-learning purposes only**. It should not be used as a medical diagnostic system.

## Author

**Palak Bajaj**

B.Tech CSE | VIT-AP University
