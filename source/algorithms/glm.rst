
Generalized Linear Model (GLM)
------------------------------

   When to use GLM

	The variable you are interested in making predictions or inferences about is a rate, an event, or a 	continuous measurement. Moreover, you are interested in seeing how a set of environmental conditions 	influence that variable. 

   EX 
	"What attributes make my customers distinct from the population as a whole?"
   	"Given a set of specific manufacturing conditions, how many units produced will fail?"
   	"What conditions most influence whether a client contacts our support service?"


   Defining a GLM model

	common inputs and general terms can be found in the glossary

	Y: Your dependent variable.	X: Once you identify your dependent variable (the value you would like to predict) in the Y field, 	the X field will auto populate with all possible options (all of your other variables).  You select 	the subset of variables that you would like to use to predict with. 	Family and link:  Each of the given options differs in the assumptions made about the Y variable - the 	target of prediction. Each family is associated with a default link function, which defines the 	specialized transformation on the set of X variables chosen to predict Y. 	

	Gaussian (identity): (Y) are quantitative, continuous (or continuous predicted values can be 			meaningfully interpreted), and expected to be normally distributed 

	Binomial (logit): dependent variables take on two values, traditionally coded as 0 and 1, and follow a 		binomial distribution, can be understood as a categorical Y with two possible outcomes

	Poisson  (log): dependent variable is a count - a quantitative, discrete value that expresses the 		number of times some event occurred

	Gamma  (inverse): dependent variable is a survival measure

	Lambda: H2O provides a default value, but this can also be user defined. Lambda is a regularization 		parameter that is designed to prevent overfitting. The best value(s) of lambda depends on the degree 	to 	which you wish the variance of the cross validated coefficients to match.

	Alpha:   A user defined tuning regularization parameter that H2O sets to 0.5 by default, but which can 	take 	any value between 0 and 1, inclusive.  It functions so that there is an added penalty taken against the 	estimated fit of the model as the number of parameters increases. An alpha of 1 is the 	lasso penalty, and an 	alpha of 0 is the ridge penalty.

   Interpreting a model

	n: the number of observations (also called examples). Each observation is one row in your data. 	p: the number of estimated parameters. Each additional piece of information you ask H2O to estimate 		increases p by one. This means that if you predict using four continuous independent variables p is 4. 	If 	you predict using four independent variables, and one is a categorical with three levels p is 7. 	Degrees of Freedom: Null (total) is defined as (n-1) to account for the condition that the residuals 	must 	sum to zero. Residual is (n-1)- p : the null degrees of freedom less the number of parameters you 	are 	estimating in your model. 	Deviance: the deviance can be used to calculate test statistics that indicate how well the model fits 	the 	data. The particular goodness of fit test will depend on the specific GLM that you have chosen.	
	Null Deviance: associated with the full model 
	Residual Deviance - associated with the reduced model
	AIC: A model selection criterial that penalizes models having large numbers of predictors. AIC stands for 	Akiaike information criterion. It is defined as 	AIC = n ln SSEp - n ln n + 2p

