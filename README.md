# Olympic Team Medal Predictor

A linear regression model designed to predict the number of medals a country will win in the Olympics.

## Hypothesis
The number of medals a country wins in the Olympics can be predicted using historical data and the amount of atheltes the send.

## Dataset
- **Source**: Data obtained from Kaggle .
- **Columns**: Includes `Team`, `Year`, `Athlete`, `Prev_Medals`, `Height`, `Weight`, and `Medals`.
- **Time Period**: Covers the Olympics from 1964 to 2016.

## Data Preparation
### Reshaping the Data
The dataset is already well-structured. Predictions can be made using rows that contain all the necessary features. 

### Feature Selection
In version 1 of the model:
- Features: `Athletes` (number of athletes a country sent that year) and `Prev_Medals` (medals won in the previous Olympics).
- Rationale: These features show a high correlation with the target variable (`Medals`).

<p align="center">
  <img src="https://i.postimg.cc/MHBWgFzz/Screenshot-2025-01-16-230056.png" alt="Correlation Heatmap">
</p>

### Data Cleaning
- Removed rows with missing values in the `Prev_Medals` column.
- Example: Albania in 1992 was excluded as they did not compete in the 1994 Olympics.

## Performance Metric
**Mean Absolute Error (MAE):**
\[
\text{MAE} = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|
\]
- **Explanation**: Measures the average absolute difference between predicted and actual medal counts.
- **Interpretation**: A lower MAE indicates better model performance.

![MAE Formula](https://arize.com/wp-content/uploads/2024/04/mean-absolute-error-formula.png)

## Data Splitting
- **Training Data**: Olympics data prior to 2012.
- **Testing Data**: Data from 2012 onwards.

## Model Training
The model uses **linear regression**:
\[
y = a_1x_1 + a_2x_2 + B
\]
Where:
- \( y \): Predicted medal count.
- \( x_1, x_2 \): Predictors (`Athletes`, `Prev_Medals`).
- \( a_1, a_2 \): Coefficients learned during training.
- \( B \): Intercept.

## Results
- **MAE**: ~3.298 medals.
- **Standard Deviation of Medals**: 33.627 medals.
- **Error Ratio**: Highlights that the model performs well for countries with higher medal counts (e.g., USA, FRA) but less effectively for countries with lower counts (e.g., EGY, MAR).

<p align="center">
  <img src="https://i.postimg.cc/WtRff94L/Screenshot-2025-01-16-231322.png" alt="Error Analysis">
</p>

## Acknowledgments
This project was inspired by and built with the help of a YouTube video by https://www.youtube.com/@Dataquestio on building linear regression models. You can find the video here [(link to video)](https://www.youtube.com/watch?v=Hr06nSA-qww&ab_channel=Dataquest).
