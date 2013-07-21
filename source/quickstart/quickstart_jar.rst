From a pre-compiled jar
-----------------------------------------
Note that first time users may need to download and install java. 
The program is avialable free on the web. Even though you wil use java
to run H2O, no programming is necessary. 

Quick Step-by-step
""""""""""""""""""
#. Download the latest release of H2O as a .jar file  from `here (http://www.0xdata.com/h2o) <http://www.0xdata.com/h2o/>`_.

#. From your terminal change your working directory to the same directory where your .jar file is saved.

#. At the prompt enter the following command.

java -Xmx1g -jar h2o.jar -name mystats-cloud

Wait a few moments and the following output will appear in your terminal window:

09:05:52.025 main   INFO WATER: ICE root: '/tmp'
09:05:52.223 main   INFO WTER: Internal communication uses port: 54322
                    Listening for HTTP and REST traffic on 
		    http:// your IP address:54321
09:05:52.416 main   INFO WATER: H2O cloud name: 'mystats-cloud'
90:05:52.416 main   INFO WATER: (v0.3) 'mystats-cloud' on / your IP address:54321,
discovery address /236.151.114.91:60567
09:05:52.423 main   INFO WATER: Cloud of size 1 formed [/your IP address:54321

#. Point your web-browser to http:// your IP address:54321/ 
The user interface will appear in your browser, and now H2O is ready to go. 

Useful Notes
""""""""""""   

First time users may need to download and install Java
in order to run H2O. The program is available free on the web, 
and can be quickly installed. Even though you will use java to 
run H2O, no programming is necessary. 

In the java command entered into the terminal the term -Xmx1g was 
used.Xmx is the amount of memory given to H2O.  If your data set is large,
give H2O more memory (for example, -Xmx4g gives H2O four gigabytes of
memory).  For best performance, Xmx should be 4x the size of your
data, but never more than the total amount of memory on your
computer.
