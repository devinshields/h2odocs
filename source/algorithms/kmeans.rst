
K-Means
-------

K-Means falls in the general category of clustering algorithms. 

When to use K-Means
"""""""""""""""""""

Data are a set of attributes on which the members of this population
likely differ. The objective is classification.
Here are some examples:

  "How do competitors differ from one another on critical dimensions?"

  "How is a particular market segmented?"

  "Which dimensions are most important to differentiating between
  members of a population of interest?"


Quick step-by-step
""""""""""""""""""
For a fully worked example see Tutorials.


#. Import  data. Under the drop down menu Data choose from the options
   listed, and follow the import helper.  


#. Parse data. Once data have been imported choose SUBMIT (a button on
   the page).  When parse finishes the page redirects to output of a
   data frame with summary statistics and the H2O assigned .hex key.
  

#. Specify a model. Model options are listed both at the top of the
   page displaying parsed data, as well as under the drop down menu
   Model. Select K-means. 


#. Source key is required. It is the .hex key previously
   generated at parse for the source data. 


#. K is a user defined parameter denoting the number of clusters. 


#. Max iter is the maximum number of iterations allowed. It determines
   the maximum number of times the algo will re-evaluate the cluster
   centers and generate new centroids.


#. Epsilon is an H2O specific tuning parameter such that if the
   movement between the old centroid and the new centroid is
   less than epsilon, the last iteration is
   kept and the process terminates.  


#. Seed remains constant for each instance of H2O, allowing the user
   to recreate models by consistently specifying randomized components
   of the algorithm. 


#. Normalize scales data by standard deviation and mean centers at 0. 


#. Cols is a list of the columns included in the parsed data. Users
   should select those columns representing the attributes on which
   they would like to cluster. 


Scoring and predicting
""""""""""""""""""""""
   
To score a model: 
     
#. Import and parse a testing data set consistent with the one used
   in building the model being scored. 


#. Group membership should be defined for the testing set so that predicted
   group and true group can be compared. 


#. Under the drop down menu Score select K-Means (this can also be
   found among the links at the top of the results summary page).
 

#. Specify the destination key for the model to be tested. If needed,
   it can be found under the Admin drop down menu by selecting
   Jobs. Specify the .hex key for the parsed testing data. 


#. Press submit.  


Defining a K-Means model
""""""""""""""""""""""""

  Source key: the .hex key associated with the data set you would like
  to cluster


  K: the desired  number of clusters. There is no set rule or formula
  for defining K, it is up to the user and is
  often based on heuristics. 


  Max iter: the maximum number of iterations the algorithm is to go
  through if no stopping point is reached before then.
 

  Epsilon: A user defined parameter such that if the movement of
  cluster centers to an improved position is less than epsilon, the
  algorithm stops. The purpose of the epsilon tuning parameter is to
  allow the user to determine at what point small marginal
  improvements in the model are not of additional information value to
  the user.


  Note that max iter and epsilon serve similar objectives; the user
  can achieve the same ends by using one or the other rather than both.


  Seed: A means for specifying the algorithm components
  dependent on randomization. Note that the seed stays the same for
  each instance of H2O, allowing the user to create models with the
  same starting conditions in alternative configurations.


  Normalize: Requests that each attribute be tranformed to mean center
  and 0 and have a standard deviation of 1. 


  Cols: The columns from the data set that contain the attribute data.



Interpreting a Model
""""""""""""""""""""

Output from K-Means is a table with one more column than the number of
attributes used to cluster. The the names of attributes, and "cluster"
appear in the header row. The column cluster gives an arbitrary number
to each cluster built, and the attributes give the coordinates of the
center of that cluster. 

+--------+-----------+-----------+
|Clusters|Attribute 1|Attribute 2|
+========+===========+===========+
|   0    | centroid  | centroid  |
|        |  value    |  value    |
+--------+-----------+-----------+

