H2O QuickStart (from Github)
===============================

These instructions assume you are using Linux, MacOSX, or Cygwin (on Windows).

1.  Create a git clone of the H2O repository.

 ::

    $ git clone https://github.com/0xdata/h2o.git

|

2.  Build H2O from source.  You must have Java JDK 1.6 or higher.
    After the build finishes, some JUnit tests will run automatically.

 ::

    $ cd h2o
    $ ./build.sh

 (Output below)

 ::

    cleaning...
     - wiping tmp...
    building classes...
    warning: [options] bootstrap class path not set in conjunction with -source 1.6
    Note: Some input files use unchecked or unsafe operations.
    Note: Recompile with -Xlint:unchecked for details.
    1 warning
    building initializer...
    ~/0xdata/ws/tmp/h2o/lib ~/0xdata/ws/tmp/h2o
    ~/0xdata/ws/tmp/h2o
    creating jar file... target/h2o.jar
    copying jar file... target/h2o.jar to target/h2o-02.33.24-061913.jar
    creating src jar file... target/h2o-sources.jar
    copying jar file... target/h2o-sources.jar to target/h2o-sources-02.33.24-061913.jar
    running JUnit tests...
    OK

|
 
3.  The build produces target/h2o.jar.  Now run h2o.jar from the command line.

 ::

    $ java -Xmx2g -jar h2o.jar

 (Output below)

 ::

	03:45:41.980 main      INFO WATER: Internal communication uses port: 54322
	+                                  Listening for HTTP and REST traffic on  http://10.197.32.113:54321/
	03:45:42.047 main      INFO WATER: (v0.3) 'ubuntu' on /10.197.32.113:54321, discovery address /227.66.218.231:58178
	03:45:42.053 main      INFO WATER: Cloud of size 1 formed [/10.197.32.113:54321]
	03:45:42.059 main      INFO HDFS: Using HDFS version cdh4

 Xmx is the amount of memory given to H2O.  If your data set is large,
 give H2O more memory (for example, -Xmx4g gives H2O four gigabytes of
 memory).  For best performance, Xmx should be 4x the size of your
 data, but never more than the total amount of memory on your
 computer.

|

4.  Point your web browser to the HTTP URL (for the example above, ``http://10.197.32.113:54321``)
