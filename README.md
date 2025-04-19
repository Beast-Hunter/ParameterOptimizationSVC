# Parameter Optimization SVM

This project utilizes Support Vector Machines (SVM) with a random search approach to estimate room occupancy based on environmental sensor data.  The dataset used is the "Room Occupancy Estimation" dataset from the UCI Machine Learning Repository.

## 1. Overview

The goal of this project is to develop a robust and accurate occupancy prediction model using SVM.  A random search strategy is employed to efficiently explore the SVM's hyperparameter space and identify optimal settings for maximum accuracy.

## 2. Data

The dataset comprises various environmental sensor readings, including temperature, humidity, light, CO2 levels, and humidity ratio. The target variable is the number of occupants in a room.

**Data Source:** [https://archive.ics.uci.edu/static/public/864/room+occupancy+estimation.zip](https://archive.ics.uci.edu/static/public/864/room+occupancy+estimation.zip)

## 3. Methodology

1. **Data Loading and Preprocessing:**
   - The dataset is downloaded and loaded into a Pandas DataFrame.
   - Irrelevant columns ('Date' and 'Time') are removed.
   - The data is split into features (X) and the target variable (y).

2. **Creating Samples:**
   - The dataset is divided into 10 different train-test splits (70% training, 30% testing) with varying random states.  This ensures a more robust evaluation of the model's performance.

3. **Random Search for Hyperparameter Optimization:**
   - A fitness function is defined to evaluate the performance of an SVM model with specific hyperparameters (kernel, C, and gamma) using accuracy as the metric.
   - A random search algorithm iterates 100 times for each sample, exploring different combinations of hyperparameters.
   - The best performing hyperparameters for each sample are recorded.

4. **Model Evaluation:**
   - The best performing model (based on the maximum accuracy across all 10 samples) is selected.
   - A learning curve is generated to visualize the model's convergence behavior.

## 4. Code

The Python code utilizes various libraries:
- pandas: For data manipulation.
- numpy: For numerical operations.
- scikit-learn: For data preprocessing, model training, and evaluation.
- matplotlib and seaborn: For data visualization.
- random:  For the random search.

The core components of the code include:
- Data loading and preprocessing
- Creating train-test splits
- Defining the fitness function for SVM evaluation
- Implementing the random search
- Plotting the convergence graph

## 5. Results

![Convergence](https://github.com/user-attachments/assets/c00ed532-b754-4cc8-932b-8e2469c64129)
