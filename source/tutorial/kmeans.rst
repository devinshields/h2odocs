K Means Tutorial
""""""""""""""""

The purpose of this tutorial is to walk the new user through a 
K-means analysis beginning to end. By the end of this tutorial
you should know how to specify, run and interpret a K-means model.

If you have never used H2O before, please see the quickstart guide
for how to run H2O on your computer. 

Getting Started
"""""""""""""""

This tutorial uses a publicly available data set that can be found 

::
 'here<archive.ics.uci.edu/ml/datasets/seeds>'

The data are composed of 210 observations, 7 attributes, and an priori grouping assignment. All data are positively valued and continuous. Before modeling, parse data into H20 as follows:

#. Under the drop down menu "Data" select Upload and use the helper to upload your data. 
#. When data are uploaded you will be directed to a page with the header "Request Parse".  All settings can be left in default, but double check that your first row is a header row before leaving that option selected. Press Submit. 

#. Pressing Submit parses your data into H2O and generates a .hex key (data name.hex).

.. image::
  ..tutorial/KMparse.png


Building a Model
""""""""""""""""

#. Once your data are parsed a horizontal menu will appear at the top
   of the screen reading "Build model using ... ". You can select 
   K Means here, or you can go to the drop down menu "Model" and
   select K Means there.

#. In the field for Source Key enter the .hex key generated when you
   parsed your data. 

#. Choose your number of K. There is no hard and fast rule for how to
   do this. For this dataset we will choose 3 clusters. 

#. Note that you can normalize, though we will not do so here. 

#. Max iter and Epsilon are both user defined tuning parameters that
   control the modeling process. Max iter allows the user to specify
   the maximum number of iterations the algorithm processes. Epsilon 
   specifies a threshold for the movement between one set of
   cluster centers and the next. If the new center moves less than
   epsilon, the algorithm terminates. 

#. Cols is a list of the columns of attributes that should be used 
   in defining the clusters. Here we select all but column 7 (the 
   a priori known clusters for this particular set). 

#. Press submit.

.. image::
  ..tutorial/KMrequest.png


K-Means Output
""""""""""""""

The output is a matrix of the cluster assignments, and the
coordinates of the cluster centers in terms of the originally 
chosen attributes. Your cluster centers may differ slightly. 
K-Means randomly chooses starting points and converges on 
optimal centroids. The cluster number is arbitrary, and should
be thought of as a factor. 

.. image::
  ..tutorial/KMinspect.png 

K-means Score
"""""""""""""

For further information on the model select K-Means from the
drop down menu Score. Specify the K means model key, and the 
.hex key for the data set originally used. 

.. image::
  ..tutorial/KMrscore.png

The output obtained when submit is pressed is the number of rows 
assigned to each cluster, and the squared error per cluster. 

.. image::
  ..tutorial/KMscore.png

K-means Apply
"""""""""""""

To generate a prediction (assign the observations in a data set
to a cluster) select K-means Apply from the Score drop down menu.
Specify the model you wish to apply and the .hex for the data 
you would like to apply it to, and press submit. 

That has been done here; cluster assignments have been generated
for the original data. Because the data have been sufficiently well 
researched that we know cluster assignments in advance we are able 
to compare the assigned cluster with the actual cluster. 
When this was done, a less than 10% error rate was found. 

.. image::
  ..tutorial/KMapply.png

 
