# Flood Prediction Using Bayesian Inference

This project applies Bayesian inference to predict flood occurrences based on meteorological features such as rainfall, temperature, and humidity. The model is implemented using `PyMC` for probabilistic programming.

## Dataset
The dataset used (`FloodPrediction.csv`) contains historical flood occurrence data along with meteorological parameters:
- **Rainfall** (mm)
- **Max_Temp** (°C)
- **Min_Temp** (°C)
- **Relative_Humidity** (%)
- **Flood?** (Binary: 1 for flood, 0 for no flood)

## Installation
Ensure you have the required libraries installed:

```bash
pip install pymc numpy pandas arviz matplotlib seaborn
```

## Workflow
1. **Data Preprocessing**:
   - Missing values in the `Flood?` column are replaced with 0.
   - Feature standardization is performed for numerical variables.

2. **Bayesian Model Definition**:
   - Priors are assigned to model parameters.
   - A logistic regression model is defined using a Bernoulli likelihood.
   - Inference is conducted using the NUTS sampler with 2000 posterior draws and 1000 tuning steps.

3. **Model Evaluation**:
   - Posterior distributions of parameters are analyzed.
   - Feature importance is computed based on the absolute values of the posterior means.
   - Posterior predictive checks validate the model’s accuracy.

4. **Performance Assessment**:
   - The model achieves **94% accuracy**.
   - Feature importance ranking:
     1. **Rainfall** (Most significant)
     2. **Min_Temp**
     3. **Relative_Humidity**
     4. **Max_Temp** (Least significant)

## Usage
Run the Jupyter Notebook to execute the full workflow:

```bash
jupyter notebook Flood_Prediction.ipynb
```

## Visualization
- The posterior distributions of model parameters are plotted using `ArviZ`.
- Class distribution analysis ensures balance in flood occurrence data.

## Results
- The model performs well in predicting flood occurrences based on meteorological conditions.
- Rainfall is the most influential factor in flood prediction.

## Contributing
Feel free to contribute by improving feature engineering, adding more predictors, or optimizing the Bayesian model.

## License
This project is released under the MIT License.

