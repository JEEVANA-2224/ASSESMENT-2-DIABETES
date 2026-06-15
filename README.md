# Diabetes Prediction using Artificial Neural Network (ANN)
# Project Overview

This project demonstrates how to build an Artificial Neural Network (ANN) using TensorFlow and Keras to predict whether a person has diabetes based on medical diagnostic measurements.

The project uses the Pima Indians Diabetes Dataset, which contains medical attributes and a target variable indicating diabetes outcome.

# Objectives
Load and analyze the diabetes dataset
Preprocess data for deep learning
Build an ANN model using Keras Sequential API
Train the model using TensorFlow
Evaluate model performance
Generate predictions for diabetes classification

# Technologies Used
Python
Pandas
NumPy
Scikit-learn
TensorFlow
Keras

# Dataset Information

The dataset contains:

8 Input Features
1 Target Variable (Outcome)
Features
Pregnancies
Glucose
BloodPressure
SkinThickness
Insulin
BMI
DiabetesPedigreeFunction
Age

# Target
0 → No Diabetes
1 → Diabetes
Project Workflow

# 1. Data Loading

The dataset is loaded using Pandas.

data = pd.read_csv('/diabetes.csv')

The dataset contains medical predictor variables and one output variable.

# 2. Data Preprocessing

Neural networks perform better when the data is properly preprocessed.

Steps Performed
Checked missing values
Split features and target variables
Performed train-test split
Applied feature scaling using StandardScaler
Feature Scaling Formula

Standardization transforms data using:

z=
σ
x−μ
	​

x
μ
σ
z=
σ
x−μ
	​

≈1.2
Φ(z)≈88.5%

Where:

x = original value
μ = mean
σ = standard deviation
3. Model Architecture

The ANN model is built using the Keras Sequential API.

# Architecture
Input Layer → 8 input features
Hidden Layer 1 → 12 neurons with ReLU activation
Hidden Layer 2 → 8 neurons with ReLU activation
Output Layer → 1 neuron with Sigmoid activation
ReLU Activation Function

f(x)=max(0,x)

Sigmoid Activation Function

σ(x)=
1+e
−x
1
	​


# 4. Model Compilation

The model is compiled using:

Optimizer → Adam
Loss Function → Binary Crossentropy
Metric → Accuracy
Binary Crossentropy Formula

L=−
N
1
	​

∑
i=1
N
	​

(y
i
	​

log(
y
^
	​

i
	​

)+(1−y
i
	​

)log(1−
y
^
	​

i
	​

))

# 5. Training the Model

The ANN model is trained for 100 epochs using the training dataset.

history = model.fit(
    X_train,
    y_train,
    epochs=100,
    batch_size=10
)

# During training:

Loss gradually decreases
Accuracy improves with each epoch
# 6. Model Evaluation

The trained model is evaluated using the test dataset.

loss, accuracy = model.evaluate(X_test, y_test)
Model Performance
Loss: 0.5896
Accuracy: 73.37%
7. Predictions

The model predicts whether a patient has diabetes or not.

y_pred_prob = model.predict(X_test)

Predictions are converted into binary labels:

Probability ≥ 0.5 → Diabetes
Probability < 0.5 → No Diabetes

# 8. Classification Report

The classification report provides:

Precision
Recall
F1-score
Support
print(classification_report(y_test, y_pred))

