# Olympic-Team-Medal-Predictor
Linear regression model which predicts how much medals a country will win in the Olympics

# Forming a Hypothesis:
We can predict how many medals a country will win in the Olympics

# Finding the Data
Data was obtained from kaggle, contains columns such as Team, Year, Athlete, Prev_Medals, Height, Width and Medals. The data ranges from the years 1964 - 2016.

# Reshaping the Data
Our data is already in the form it needs to be in. Values can be pulled from a single row to make the predictions we need. Everything is available in a single row. 

The first version of this project predicts the amount of medal by using the Athletes( a column containing the amount of atheltes a country sent in that year) and Prev_Medals (a column containning the amount of medals won in the previous olympics). This was due the correlation between these columns and the target column(medal) being so high.

![Screenshot-2025-01-16-230056.png](https://i.postimg.cc/MHBWgFzz/Screenshot-2025-01-16-230056.png)

# Cleaning the Data
Removed rows containing  missing values from Prev_Medals column (Example: A row containng Albania in 1992 is removed as they did not compete in the '94 Olympics). 

# Performance Metric
Error metric used to measure model performance is is Mean Absolute Error:
![Equation](https://arize.com/wp-content/uploads/2024/04/mean-absolute-error-formula.png)
The metric calculates the error by subtracting the actual from the predicted amount of medals and getting its aboulte value. It then gets an average of all these values.

# Splitting the Data
Data was split into training an test sets based of their Year column. All the data prior to 2012 was palced into the training dataset and the rest was used to test the model.

# Training the Model
Model was trained using linear regression.The equation is: 
$y = \textit{ax} + B$
This basically draws a line of best fit (a model) and we can then use this model to make predicitons. Two predictors where used to guess the medal count of a country. The equation then becomes: 
$y = \textit{a1x1 +a2x2} + B$
 
# Results for V1
The MAE of the linear regression model was found to be approx 3.298 Medals. This value is much lower than the standard deviation of 33.627 Medals the data has. An error ratio was obtained by devidiing the error for that team by the actual medals the team got. This error ratio told us that the model tends to perform very well for countries which tend to get a lot of medals, such as FRA and USA, but poorer for countries that dont obtain as much medals, such as EGY and MAR.

[![Screenshot-2025-01-16-231322.png](https://i.postimg.cc/WtRff94L/Screenshot-2025-01-16-231322.png)](https://postimg.cc/RJRRWLfX)
 
