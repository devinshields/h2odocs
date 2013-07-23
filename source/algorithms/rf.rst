
Random Forest (RF)
-------------

RF is a powerful classificaiton tool. When given a set of data, RF
gererates a forest of classification trees, rather than a single classification 
tree. Each of these trees generates a classification for a given set of 
attributes, and the final classification is the assignment with the highest 
level of consensus among all of the trees. 

When to use RF
""""""""""""""
RF is a good choice When you are interested in determining the critical attributes or features of a data set, you wish to better understand segments within yourdata set, or when your analytical objective is clustering. Here are some examples

  "There are 1000 variables in this data set. Of those, which most charactarize differences between one observation and another with respect to the desired outcome variable?"

  "Given a large set of observations and attributes, the goal is to classify observations by spending habits."

Quick step-by-step
""""""""""""""""""

#. Import your data. Under the drop down menu "Data" choose from the options listed and follow the import helper. To imspect your data for correct import, you can choose ispect from the same menu. 

#. Parse your data. Once data have been imported choose SUBMIT (a button on the page). Data will parse automatically, and when finished you will be automatically directed to a page that provides you with a hex key ("yourdata.hex"). A frame of your data with summary statistics will also be displayed. 

#. Specify your model. From the drop down menu "Model", or the horizontal menu displayed at the top of the page after parse choose Random Forest. 

#. The user must specify "Data key", the .hex key generated when you parsed your data. 

#. The user must also specify the response variable, and the predictor variables. Note that highlighting a predictor EXCLUDES it from the classification. Note that predictors can take on many forms, but the response variable  must be quantitative.

#. Specification of N-tree is 50 by defualt. This tuning parameter allows users to specify the number of classification trees they wish to build. 

#. All other parameters are tuning parameters, to be adjusted at the analyst's choice. Not adjusting them does not impede a model from being built, but will influence results.

  Select SUBMIT, a button at the bottom of the model page in order to generate the model and associated output.
