# Battery Voltage Prediction from EIS Signature

This project involves predicting the **voltage** of a battery based on its **EIS (Electrochemical Impedance Spectroscopy)** signature. The data consists of multiple CSV files extracted from a ZIP archive, each containing measurements like voltage, current, temperature, and time. The goal is to predict the voltage using machine learning models, visualize the results, and calculate accuracy.

## Features

- Extracts and combines data from multiple CSV files.
- Preprocesses the data by scaling the features.
- Trains an optimized machine learning model using Random Forest Regression.
- Evaluates the model with metrics such as **R² Score** and **Mean Absolute Error (MAE)**.
- Plots **Actual vs Predicted Voltage** graph for visual comparison.
- Saves the consolidated results (original data with predicted values) in `consolidated_results.csv`.

## Requirements

- Python 3.x
- Required libraries:
  - pandas
  - numpy
  - matplotlib
  - scikit-learn
  - zipfile

You can install the required libraries using pip:

```bash
pip install pandas numpy matplotlib scikit-learn
```

## Project Structure

```
.
├── datas1.zip               # The zip file containing the CSV files
├── consolidated_results.csv  # Output file with the original data and predicted voltage values
├── battery_voltage_prediction.py  # Python script for data processing, training, and evaluation
└── README.md                # This README file
```

## How to Run

1. **Upload the ZIP file** (`datas1.zip`) containing the CSV files to your environment.
   
2. **Run the Python script** to extract the data, train the model, and generate the results:

```bash
python battery_voltage_prediction.py
```

3. **Results**:
   - The model will generate a graph comparing **Actual vs Predicted Voltage**.
   - The R² Score and Mean Absolute Error will be displayed to evaluate the model.
   - A new file named `consolidated_results.csv` will be created, containing the original data with the predicted voltage values.

### Graph Example:
- **Actual vs Predicted Voltage**: This scatter plot shows how closely the predicted values match the actual voltage readings.

### Model Accuracy:
- The **R² Score** is printed to show the accuracy of the model. A higher value (close to 1) indicates a better fit between predicted and actual data.
- The **Mean Absolute Error (MAE)** gives you an estimate of the model's prediction error.

## Notes

- The model uses **Random Forest Regressor** for prediction, which is optimized using **Grid Search** for hyperparameter tuning.
- The CSV files should contain the following columns:
  - `Voltage_measured`: The target value (voltage) to predict.
  - `Current_measured`: The current measured during the test.
  - `Temperature_measured`: The temperature of the battery during the test.
  - `Current_load`: The current load applied.
  - `Voltage_load`: The voltage under load.
  - `Time`: Time stamps for the measurements.

