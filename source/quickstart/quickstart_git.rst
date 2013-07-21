From source code (Github)
----------------------------

These instructions assume you are using Linux, MacOSX, or Cygwin (on Windows).

#. Create a git clone of the H2O repository.
 ::
 $ git clone https://github.com/0xdata/h2o.git


#. Build H2O from source.  You must have Java JDK 1.6 or higher.
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
 
#.  The build produces target/h2o.jar.  Now run h2o.jar from the command line.
Note that Xmx is the amount of memory given to H2O. If your data set is large,
increase the number immediately following Xmx from the default of 2. As a rule,
the amount of memory given should be about 4 times the size of your data, but no 
larger than the total memory of your computer. 
 ::

    $ java -Xmx2g -jar target/h2o.jar

 (Output below)

 ::

	03:45:41.980 main      INFO WATER: Internal communication uses port: 54322
	+                                  Listening for HTTP and REST traffic on  http://10.197.32.113:54321/
	03:45:42.047 main      INFO WATER: (v0.3) 'ubuntu' on /10.197.32.113:54321, discovery address /227.66.218.231:58178
	03:45:42.053 main      INFO WATER: Cloud of size 1 formed [/10.197.32.113:54321]


#. Point your web browser to the HTTP URL (``http://your-ip-address:54321``);
H2O will run from there.  
