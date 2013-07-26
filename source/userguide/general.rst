General
=======

H2O System Requirements
-----------------------

H2O node software requirements

   64-bit Java 1.6 or higher (Java 1.7 is fine, for example)

H2O node hardware requirements

   

User Interaction
----------------

Users have several options for interacting with H2O. 

A web browser can be used to communicate directly with the embedded web server inside any of the H2O nodes.  All H2O nodes contain an embedded web server, and they are all equivalent peers. 

Users can also choose to interface with the H2O embedded web server via the REST API. The REST API accepts HTTP requests and returns JSON-formatted responses. 

A third way is of the user to use the H2O.R package from Oxdata, which provides an R-language package for users who wish to use R. This package uses H2O's REST API under the hood. 

Data sets are not transmitted directly through the REST API. Instead, the user sends a command (containing and HDFS path to the data set, for example) either through the brewers or via the REST API to ingest data from disk. 

The data set is assigned a KEy in H@O that the user may refer to tin the future commands to the web server. 

How Data is Ingested into H2O
-----------------------------

For step by step instructions on how to carry out data ingestion and parse, please see the Data section of this user guide. 

Supported input data file formats include CSV, Gzip-compressed CSV, MS Excel (XLS), ARRF, HIVE file format, and others. 