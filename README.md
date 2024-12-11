This is the 12/11/2024 version of my study on the appropriate way to split a data set into training and validation. 
I compared two models (multiple linear regression aka MLM) and a a Random Forest Regressor (RFR) from the sklearn package. 
I also compared two measures of accuracy (or error rather), the mean absolute error (MAE) and the root means square error (RMSE)
I used simulated data with n=1000 points. 

I used M=2 variables sampled from a standard normal distribution along with a random error sampled from a normal distribution with SD=.5.
I generated my simulated response variable as y=X1+X2+error.  In particular this is a linear model. 

I used the train_test_split function from the sklearn package to randomly split the 10000 data points into various ratios, starting
from .001 (so 99.9% of the data was used to train and only .1% used to validate) up through .999 (wherein only .1% of the data was used to train)
and I plotted the four error measurement variables (MLM using RMSE, MLM using MAE, RFR using MAE, RFR usiing RMSE) so they could be compared. 

Results:  Predictably the linear model worked better since the response variable was in fact a linear combination of independent variables. Also 
the MAE errors were lower than the RMSE errors.  This may in fact be a mathematical consequence of the Cauchy-Schwarz Inequality (but I should verify this).

Most interestingly there occurred a minimum error for all four variables right around a ratio of .05 (so 95% of the data is used to train and 5% to validate).
