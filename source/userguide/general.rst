General
=======

H2O System Requirements
-----------------------

64-bit Java 1.6 or higher (Java 1.7 is fine, for example)

Minimum of 2g ram available on the machine where H2O will be running
(Note that users may have to adjust the amount of memory allocated to H2O regardless of the 
total amount of memory available on their machines. Details for how to
do this can be found in the quick start guide.)

A reasonably modern web browser (for example, the latest version of
Firefox, Safari or IE.)

Users who are running H2O on a server must ensure that the data are
available to that server (either via their network settings, or
because the data are on the same server.) Users who are running H2O on
a laptop must ensure that the data are available to that laptop. The
specification of network settings is beyond the scope of this
documentation.    

User Interaction
----------------

Users have several options for interacting with H2O. 

A web browser can be used to communicate directly with the embedded
web server inside any of the H2O nodes.  All H2O nodes contain an
embedded web server, and they are all equivalent peers. 

Users can also choose to interface with the H2O embedded web server
via the REST API. The REST API accepts HTTP requests and returns
JSON-formatted responses. 

A third way is of the user to use the H2O.R package from 0xdata, which
provides an R-language package for users who wish to use R. This
package uses H2O's REST API under the hood. 

Data sets are not transmitted directly through the REST API. Instead,
the user sends a command (containing and HDFS path to the data set,
for example) either through the brewers or via the REST API to ingest
data from disk. 

The data set is assigned a KEY in H2O that the user may refer to in
the future commands to the web server. 

How Data is Ingested into H2O
-----------------------------

For step by step instructions on how to carry out data ingestion and
parse, please see the Data section of this user guide. 

Supported input data file formats include CSV, Gzip-compressed CSV, MS
Excel (XLS), ARRF, HIVE file format, and others. 


Using H2O
---------

Step by step instructions on how to use each of the tool sets can be
found in User Guides by selecting the algorithm of choice. Users have
a variety of options for accessing and running H2O. For instructions
on how to get started using H2O (for example through R, using Java, or
via git-hub), please see the Quick Start Guides. New users may also
find the glossary useful for familiarizing themselves with H2O's
computing and statistics terms. 
