# Sales Prediction using Multiple Linear Regression

Predicting product sales from advertising spend on TV, radio, and newspaper, and finding which channels actually drive sales.

## Dataset
- **Advertising dataset**: 200 rows, 4 columns
- **Features:** `TV`, `radio`, `newspaper` (advertising budget per channel)
- **Target:** `sales`

## Approach
1. **EDA:** pair plots and a correlation heatmap to see how each channel relates to sales
2. **Baseline model:** multiple linear regression with scikit-learn on all three features
3. **Feature selection:** compared models with and without `newspaper` using the coefficients and R²
4. **Evaluation:** 80/20 train-test split, measured with RMSE and R²
5. **Feature engineering:** added a `TV x radio` interaction term
6. **Diagnostics:** prediction error plots using Yellowbrick

## Results

| Model | RMSE | R² |
|---|---|---|
| TV + radio + newspaper | 1.41 | 0.893 |
| TV + radio | 1.40 | 0.895 |
| TV + radio + TV x radio interaction | 0.70 | 0.979 |

Regression coefficients (all features): TV = 0.046, radio = 0.189, newspaper = -0.001.

## Key Findings
- **TV and radio drive sales.** Radio has the largest effect per unit of spend.
- **Newspaper has almost no effect.** Its coefficient is close to zero, and removing it did not hurt performance.
- **Channels work better together.** The TV x radio interaction term cut the error roughly in half, which suggests combined TV and radio spend has an effect beyond each channel alone.

## Tech Stack
Python, Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib, Yellowbrick

## Project Structure
- `sales_prediction.ipynb`: full analysis and model building
- `Advertising.csv`: dataset

## How to Run
1. Clone the repo and install the libraries: `pip install pandas numpy scikit-learn seaborn matplotlib yellowbrick`
2. Open `sales_prediction.ipynb` in Jupyter Notebook or Google Colab
3. Run all cells (keep `Advertising.csv` in the same folder)

## Future Improvements
- Add k-fold cross-validation for more reliable evaluation
- Compare Ridge, Lasso, and Random Forest models
- Check regression assumptions with residual analysis

## Author
Shreyash Vats | [LinkedIn](https://www.linkedin.com/in/shreyash-vats-1a22232a4/)
