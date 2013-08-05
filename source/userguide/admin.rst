Admin
=====


Jobs
-----

Users can access information on each action undertaken in an instance of H2O by accessing Jobs under the Admin drop down menu. From here it is possible to find .hex keys associated with models and parsed data. If a an action was canceled, that is displayed here as well.

Cluster Status
--------------

The status and location of a cluster can be verified by selecting Cluster Status from the Admin drop down menu. 

Advanced
--------

Timeline: displays for the user a time ordered list of H2O status events (when a cluster was started). When running a multi cluster analysis, it may happen from time to time that a node dies. This could occur for instance, if a server goes down. 

Stack Dump: Advanced users and those oriented toward programming can find error information here.  

Inspect Log: provides a detailed accounting of all activities and events within an instance of H2O. For example, one event in the inspect log shows up as  

::
  
  05-Aug 12:01:45.751 192.168.1.84    2286  # Session INFO WATER: K$0e01c0a8015432d4ffffffff$dd9054ce-2a11-4b59-9421-a4f16c11856e V:1496

Shutdown: When users are finished running a particular instance of H2O, the program should be exited by selecting Shutdown from the Admin drop down menu. Even if the user closes the browser window in which the H2O instance is running, without explicitly stopping H2O, the cluster associated with an H2O instance still exists. The user could return to the browser based interface at any time, and access all of the prior jobs within that instance of H2O. Resources are still being allocated to H2O. In order to entirely quit an instance of H2O and free up the resources allocated to the program, the user may use Shutdown to kill the cluster. 

 


