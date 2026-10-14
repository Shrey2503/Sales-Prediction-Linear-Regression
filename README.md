Sales Prediction using Multiple Linear Regression

Predicting product sales from advertising spend on TV, radio, and newspaper, and finding which channels actually drive sales.

Dataset
Advertising dataset: 200 rows, 4 columns
Features: TV, radio, newspaper (advertising budget per channel)
Target: sales
Approach
EDA: pair plots and a correlation heatmap to see how each channel relates to sales
Baseline model: multiple linear regression with scikit-learn on all three features
Feature selection: compared models with and without newspaper using the coefficients and R²
Evaluation: 80/20 train-test split (random_state=1), measured with RMSE and R²
Feature engineering: added a TV x radio interaction term
Diagnostics: prediction error plots using Yellowbrick
Results
Model	RMSE	R²
TV + radio + newspaper	1.41	0.893
TV + radio	1.40	0.895
TV + radio + TV x radio interaction	0.59	0.981

All results are measured on the same 80/20 held-out test set.

Regression coefficients (all features): TV = 0.046, radio = 0.189, newspaper = -0.001.

Key Findings
TV and radio drive sales. Radio has the largest effect per unit of spend.
Newspaper has almost no effect. Its coefficient is close to zero, and removing it did not hurt performance.
Channels work better together. The TV x radio interaction term cut the test error by more than half, which suggests combined TV and radio spend has an effect beyond each channel alone.
Tech Stack

Python, Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib, Yellowbrick

Project Structure
sales_prediction.ipynb: full analysis and model building
Advertising.csv: dataset
How to Run
Clone the repo and install the libraries: pip install pandas numpy scikit-learn seaborn matplotlib yellowbrick
Open sales_prediction.ipynb in Jupyter Notebook or Google Colab
Run all cells (keep Advertising.csv in the same folder)

Note: Yellowbrick may not work with the newest scikit-learn versions. If the prediction error plots fail, install scikit-learn==1.5.2.

Author

Shreyash Vats | LinkedIn
