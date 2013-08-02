
Random Forest (RF)
------------------

RF is a powerful classification tool. When given a set of data, RF
generates a forest of classification trees, rather than a single classification 
tree. Each of these trees generates a classification for a given set of 
attributes. The classification from each tree can be thought of as a vote; the most votes determines the classificaiton. 

When to use RF
""""""""""""""
RF is a good choice when your objective is classification. For example:

  "Given a large set of observations and attributes, the goal is to classify observations by spending habits."

Quick step-by-step
""""""""""""""""""

#. Import data. Under the drop down menu Data choose from the options listed and follow the import helper.

#. Parse data. Once data have been imported choose SUBMIT (a button on the page). Data will parse automatically, and when finished you will be directed to a page that provides you with a hex key ("data.hex"). A frame of data with summary statistics will also be displayed. 

#. Specify model. From the drop down menu Model, or the horizontal menu displayed at the top of the page after parse choose Random Forest. 

#. The user must specify Data key, the .hex key generated when data were parsed. 

#. The user must also specify the response variable, and the predictor variables. Note that highlighting a predictor EXCLUDES it from the classification.

#. Specification of N-tree is 50 by default. This tuning parameter allows users to specify the number of classification trees they wish to build. 

#. All other parameters are tuning parameters, to be adjusted at the analyst's choice. Not adjusting them does not impede a model from being built, but will influence results.

  Select SUBMIT, a button at the bottom of the model page in order to generate the model and associated output.

Predicting
""""""""""
 
#. Parse the data to predict on. Note that this
   data should have the same variables as those used in generating the
   model. 

#. Under the drop down menu Score select Predict.
   
#. Enter the destination key for the random forest to be applied (which can be found under
   Jobs in the Admin drop down menu if needed), and the .hex key for
   the data to be predicted on. 

#. Press Submit

#. The resulting column is a row by row match with the data submitted,
   giving a predicted value. This output can be downloaded and saved
   as a .csv file. 

Defining a Model
""""""""""""""""""

Response variable: The variable on which you would like to classify


Ntree: the number of trees the user would like to generate for classification


Features: a user defined tuning parameter for controlling model complexity (by number of nodes); the number of features on which the trees are to split. In practice features is bounded between 1 and the total number of features in the data. In different fields features may also be called attributes or traits. 

Depth: a user defined tuning parameter for controlling model complexity (by number of edges); depth is the longest path from root to the furthest leaf. 

Stat type: a choice of criteria that determines the optimum split at each node. 
	Entropy: (also known as information gain), entropy is a measure of uncertainty in a classification scheme. For example, if a two class population is 90% class A, and 10% class B, then there is a .90 probability that a randomly selected member of the population is A. This scheme has lower entropy than a population where 50% is class A, and 50% is class B. the objective of using the entropy impurity measure is to minimize this uncertainty.  
	
	Gini: an impurity measure based on the disparities in attribute correlation between the most and least dominant classes in a node. The objective of using this impurity measure is to choose the feature split that best isolates the dominant class.

Ignore: is the set of columns other than the response variable that should be omitted from building the tree. 
 

Sampling strategy: serves a similar purpose as class weights; 
	Random Sampling: pulls subsets on which trees are built such that every observation has an equal chance of being drawn. 

	Stratified Sampling: partitions data set by classification before sampling, and then samples from each subset. This implies that each class will be represented in every split, even if the class being drawn in a random sample was a low probability event. 


Sample: User defined percentage of the observations in the data set to sample for the building of each tree. 

Out of bag error estimate: Every tree RF internally constructs a test/ train split. The Kth tree is built by pulling a sample on the data set, bootstrapping, and using the result to build a tree. Observations not used to build the tree are then run down the tree to see what classification they are assigned. The OOB error rate is calculated by calculating the error rate for each class and then averaging over all classes. 

Bin Limit: a user defined tuning parameter for controlling model complexity, bin limit caps the the maximum number of groups into which the orginal data are to be categorized.

Seed: A large number that allows the analyst to recreate an analysis by specifying a starting point for black box processes that would otherwise occur at a randomly chosen place within the data.

Class Weight: When observerd classifications in training data are uneven, users may wish to correct this by weighting. Weights should be assigned so that if chosen at random, an observation of each classification has an equal chance. For example, if there are two classifications A and B in a data set, such that As occur about 10% of the time, and Bs occur the rest, A should given a weight of 5, and B of .56. 
 


Interpreting Results
""""""""""""""""""""

RF results of initial interest are comprised of a model key and a confusion matrix. The model key specifies the full forest of trees to be used for predicting classifications. 


The confusion matrix is formatted like this:

+------------------+-----------+---------+----------+
| Actual/Predicted |  Class A  | Class B |   Error  |
+==================+===========+=========+==========+
| Class A          |    a      |    b    |     e    |
+------------------+-----------+---------+----------+
| Class B          |    c      |    d    |     f    |
+------------------+-----------+---------+----------+
| Totals           |    g      |    h    |     i    |
+------------------+-----------+---------+----------+

a = the number of correct predictions of class a

b = the number of incorrect predictions of class a

c = the number of incorrect predictions of class b

d = the number of correct predictions of class b

e = incorrect class A predictions/ total in class A

f = incorrect in class B predictions/ total in class B

g = total of class A column 

h = total of class B column

i = total incorrect predictions/total observations
 
 



