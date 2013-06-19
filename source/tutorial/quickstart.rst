H2O QuickStart (from a command line, using a pre-compiled jar)
==============================================================

1.  Download the latest release of H2O from `here (http://www.0xdata.com/h2o) <http://www.0xdata.com/h2o/>`_.

|

2.  Start H2O from your command line.

 ::

    java -Xmx2g -jar h2o.jar

 Xmx is the amount of memory given to H2O.  If your data set is large,
 give H2O more memory (for example, -Xmx4g gives H2O four gigabytes of
 memory).  Xmx should never be more than the total amount of memory on
 your computer.

|

3.  You should see output like this:

 ::

	03:45:41.980 main      INFO WATER: Internal communication uses port: 54322
	+                                  Listening for HTTP and REST traffic on  http://10.197.32.113:54321/
	03:45:42.047 main      INFO WATER: (v0.3) 'ubuntu' on /10.197.32.113:54321, discovery address /227.66.218.231:58178
	03:45:42.053 main      INFO WATER: Cloud of size 1 formed [/10.197.32.113:54321]
	03:45:42.059 main      INFO HDFS: Using HDFS version cdh4

|

4.  Point your web browser to the HTTP URL (for the example above, ``http://10.197.32.113:54321``)
