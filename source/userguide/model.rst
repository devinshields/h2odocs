
model
=====


For detailed information on the specifications of each model, please
see Algorithms. Tutorials for each algorithm are available in Tutorial
Documentation. 

In general, a model of the users choosing can be specified either by finding the list of algorithms at the top of the Inspect page when data are parsed or by selecting the appropriate model from the drop down menu Model. 

Each model requires that the user provide a .hex key associated with a data set. Users can often begin typing the name of the original data source, and select the appropriate .hex key from the auto fill menu that will appear. Users can also find .hex keys for data sets specifically by selecting View All from the Data drop down menu, or for all H2O actions by selecting Jobs from the Admin drop down menu. 

If a large data set is used in the training and testing of a model, H2O's capabilities can be bounded by the amount of memory available on the machine. To utilize H2O's full capability, the amount of memory available should be about 4 times the file size of the data set, but not more than the machine's total available memory. For instructions on how to change the amount of memory allocated to H2O see the Quick Start Documentation. Advanced users should run H2O on a cloud computing resource or server. 


