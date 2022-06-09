# Sports-Analytics
Given data about one season, this script predicts how many games the same baseball team will win next season using linear models, Least Squares Estimates, and Least Absolute Shrinkage and Selection Operator Estimates.

Algorithm:
I used a Linear model to characterize the relationship between the statistics and the number of wins.  Given a number of statistics x1,...,x122 for a single team for a single year, I modeled the number of wins next "y" year using:

x1w1 + x2w2 + ... + x122w122 = y

I captured the equation using matrices: (x1 x2 ... x122) (w1        = (y)
                                                          w2
                                                          ...
                                                          w122)

Each row of the  matrix represents the statistics for a single team for a single year, and the corresponding row in the  matrix is the number of games that team won in the next year.

1. Generating Predictions
 The method generate_predictions(self, inputs) in the LinearModel class produces an nx1 matrix, the values predicted by the linear model when provided with the data matrix X.
 
 2. Calculating Prediction Error
The method prediction_error(self,inputs,actual_result) in the LinearModel class produces the mean-squared error between the values predicted by the model and the actual results.

3. Fitting the Model: Least Squares Estimate
The optimal weights were computed by minimizing the Mean Squared Error. The method fit_least_squares(input_data, output_data) computes the least squares estimate for the weights. The function returns a LinearModel object which has been fit using Least Squares to approximately match the data.

4. Fitting the Model: LASSO Estimate

In this algorithm, we begin with an initial guess for the minimal weights. We then use the  which minimizes MSE as the initial guess; The method fit_lasso creates a Linear Model which predicts the output vector given the input matrix using the LASSO method.

5. Running the Predictions

Created and fit a model to the 1954-2000 data using the Least-Squares Estimation and LASSO estimation with 3 different lambda values between 1000 and 100,000. Printed out each model's prediction error on the 1954-2000 data and the 2001-20012 data.




