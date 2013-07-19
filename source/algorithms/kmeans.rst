
K-Means
-------

K-Means falls in the general category of clustering algorithms.

When to use K-Means
"""""""""""""""""""

There is a population you are interested in characterizing, and you have a set of attributes on which the members of this population likely differ.  Here are some examples:

  "How do my competitors differ from one another on critical dimensions?"

  "How is a particular market segmented?"

  "Which dimensions are most important to differentiating between members of a population of interest?"


Quick step-by-step
""""""""""""""""""

#. Import your data. Under the drop down menu "Data" choose from the options listed, and follow the import helper. To inspect your data for correct import, you can choose inspect from the same menu.  

#. Parse your data. Once data have been imported choose SUBMIT (a button on the page). Data will parse automatically, and when finished you will be directed to a page that provides you with a hex key (a header at the top of the page reading "yourdata.hex"), and a frame of your data with summary statistics. 

#. Specify a model. Either from the listed options at the top of the page displaying your parsed data or under the drop down menu "Model" select K-Means. 

#. Source key is required and is the "yourdata.hex" previously generated at parse. 

#. K is a user defined parameter denoting the number of clusters you would like your observations to be grouped into. 

#. Max iter is the maximum number of iterations allowed. It determines the maximum number of times the algo will re-evaluate the cluster centers and generate new centroids.

#. Epsilon is an H2O specific tuning parameter such that if the movement between the old centroid and the new centroid is sufficiently small (as in epsilon small), the last iteration is kept and the algo is done. 

#. Seed is a randomly defined starting point unless the user defines otherwise. 

#. Normalize allows users to mean center and scale by the standard deviation. 

#. Cols is a list of the columns included in the parsed data. Users should select those columns representing the attributes on which they would like to cluster. 

Scoring and predicting
""""""""""""""""""""""
   
To score a model: 
     
#. Import and parse a testing data set composed of the same predictor variables that were utilized in building the original model. Group membership should be defined for the testing set so that predicted group and true group can be compared. 

#. Under the drop down menu Score select K-Means (this can also be found in the listed menu at the top of the results summary page). 

#. Specify the destination key for the model to be tested. If needed, it can be found under the Admin drop down menu by selecting Jobs. Specify the .hex key for the parsed testing data. 

#. Press submit.  

