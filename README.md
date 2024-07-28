
# Monetary Analysis of Argentina from the Perspective of the Quantity Theory of Money

This project explores the relationship between the money supply and inflation, as well as their relation to real output in Argentina, using data from the World Bank and statistical analysis.

## Table of Contents
1. [Introduction](#introduction)
2. [Data](#data)
3. [Methodology](#methodology)
4. [Results](#results)
5. [Requirements](#requirements)
6. [Installation](#installation)
7. [Usage](#usage)
8. [Contributing](#contributing)
9. [License](#license)

## Introduction

The Quantity Theory of Money suggests that the price level of an economy is directly related to the amount of money in circulation. This project focuses on analyzing this relationship within the context of Argentina, using historical data to assess the validity of the theory in the long term. It also evaluates if the money supply affects real output growth and the impact of inflation on real GDP growth.

## Data

Data was sourced from the World Bank using the `pandas_datareader` library. The dataset includes historical series on the broad money, inflation, and GDP (current and constant) in Argentina. The data ranges from 1960 to 2023.

To access the data, you can use the following command:

```python
from pandas_datareader import wb
```

## Methodology

A linear regression model was used to examine the relationship between the money supply and inflation under normalized conditions in Argentina. Notably, three hyperinflation years were excluded from the regression analysis as outliers. The strength of the relationship was evaluated using the coefficient of determination (R²), which was found to be 0.92, indicating a strong correlation. Checks were conducted to verify linearity, homoscedasticity, and normality of the residuals.

Furthermore, the full dataset, including periods of hyperinflation, was analyzed using a Granger Causality test and a Random Forest Model to account for outliers and potential non-linear relationships. The Granger Causality test confirmed that inflation is Granger-caused by the money supply. The Random Forest model yielded an R² of 0.81 with a Mean Squared Error (MSE) of 0.033.

A correlation matrix was also constructed to explore the relationships between variables, confirming a strong correlation between money supply and inflation, and low correlations between money supply and real output, as well as between inflation and real output.


## Results

1. Linear Regression Analysis
    The linear regression analysis was conducted to examine the relationship between Broad Money (money supply) and inflation. The regression results indicate a strong positive correlation between these two variables, as evidenced by an R-squared value of 0.92. This suggests that 92% of the variance in inflation can be explained by changes in the money supply.

    The estimated coefficient for Broad Money in the regression model is approximately 1.015. This implies that a 1% increase in the growth rate of the money supply is associated with an approximate 1.015% increase in the inflation rate. This strong correlation underscores the significant impact of changes in the money supply on inflation rates in Argentina.

2. Implications of Monetary Policy
    The results of the regression analysis have important implications for monetary policy in Argentina. The strong relationship between money supply growth and inflation suggests that loose monetary policies—such as those that rapidly increase the money supply—can lead to substantial inflationary pressures. 

    Policymakers must, therefore, consider the implications of expanding the money supply too rapidly. While such policies might aim to stimulate economic growth, data showed that no correlation existed between expanding money supply and real GDP growth in the long term. However, they can lead to runaway inflation if not carefully managed. The data suggests a need for more disciplined monetary policies to avoid exacerbating inflationary pressures, which can erode purchasing power and destabilize the economy.

3. Velocity of Money
    An interesting aspect of the data analysis involves the velocity of money, which measures how frequently money is exchanged in an economy. The analysis of the velocity of money in Argentina shows that it has varied significantly over time, reflecting changes in economic activity and confidence in the currency.

    The correlation matrix indicated that the velocity of money did not have a strong direct correlation with inflation or GDP growth. This suggests that while the velocity of money can fluctuate, its direct impact on inflation may be less significant compared to the influence of money supply growth itself. However, it's important to consider that changes in velocity can still play a crucial role, especially in contexts where changes in money supply are not as pronounced or during periods of hyperinflation.

4. Granger Causality Test
    The Granger causality test further confirmed that changes in the money supply Granger-cause changes in inflation, particularly when considering one or two lags. This finding indicates a predictive relationship where past values of the money supply can help forecast future inflation rates. The robustness of this result across both training and test datasets strengthens the argument that money supply growth is a key determinant of inflation in Argentina.

5. Random Forest Analysis
    To account for potential non-linear relationships and outliers, a Random Forest model was employed. This model achieved an R-squared value of 0.81, with a mean squared error of 0.033. While the R-squared is slightly lower than that of the linear regression, the Random Forest model's ability to handle complex interactions and outliers provides additional validation of the strong linkage between money supply and inflation. The results from the Random Forest analysis also suggest that, even when considering potential non-linearities, the main driver of inflation remains changes in the money supply.

Conclusion
    The results of this analysis provide robust evidence that changes in the money supply have a significant impact on inflation in Argentina. The findings suggest that Argentina's historical episodes of high inflation can be largely attributed to periods of rapid money supply growth, often driven by expansionary monetary policies. While inflation has been increasingly rising alongside the money supply, this trend has not been mirrored in real GDP growth, which has remained relatively constant at around 2.33%. This indicates that monetary expansions are primarily translating into higher inflation and a loss of confidence in the local currency, rather than stimulating real economic growth.


## Requirements

- Python 3.8 or higher

To run the analysis, you will need the following Python packages:
- `pandas` for data manipulation
- `numpy` for numerical operations
- `matplotlib` and `seaborn` for visualization
- `statsmodels` for statistical modeling
- `scikit-learn` for machine learning models
- `pandas_datareader` for accessing World Bank data

## Installation

You can install the necessary packages using pip:

```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn pandas_datareader
```

## Usage

To run the analysis, follow these steps:
1. Clone this repository.
2. Ensure you have the necessary packages installed.
3. Run the provided Python scripts or Jupyter notebooks, which include data loading, cleaning, analysis, and visualization.

## Contributing

Contributions to this project are welcome! If you have suggestions or improvements, please open an issue or submit a pull request. Please adhere to the code of conduct and contribute to a constructive and collaborative community.

## License

This project is licensed under the GNU General Public License. See the [LICENSE](LICENSE.txt) file for details.
