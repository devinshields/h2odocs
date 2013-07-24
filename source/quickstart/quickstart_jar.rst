From a pre-compiled jar
-----------------------------------------
 

Quick Step-by-step
""""""""""""""""""
1. Download the latest release of H2O as a .jar file  from 

::

  h2o download http://www.0xdata.com/h2o/

2. From your terminal change your working directory to the same directory where your .jar file is saved.

3. At the prompt enter the following command.

::
 
  java -Xmx1g -jar h2o.jar -name mystats-cloud

4. Wait a few moments and the following output will appear in your terminal window:

::

  04:57:15.900 main      INFO WATER: ----- H2O started -----
  04:57:15.901 main      INFO WATER: Build git branch: master
  04:57:15.901 main      INFO WATER: Build git hash: 9b956b258f276b5187cecde2be193c6485bd4517
  04:57:15.902 main      INFO WATER: Build git describe: 9b956b2
  04:57:15.902 main      INFO WATER: Built by: 'tomk'
  04:57:15.902 main      INFO WATER: Built on: 'Tue Jul 23 14:13:38 PDT 2013'
  04:57:15.902 main      INFO WATER: Java availableProcessors: 8
  04:57:15.906 main      INFO WATER: Java heap totalMemory: 0.08 gb
  04:57:15.906 main      INFO WATER: Java heap maxMemory: 0.99 gb
  04:57:15.918 main      INFO WATER: ICE root: '/tmp'
  04:57:15.955 main      WARN WATER: Multiple local IPs detected:
  +                                    /172.16.175.1  /192.168.183.1  /192.168.1.28
  +                                  Attempting to determine correct address...
  +                                  Using /192.168.1.28
  04:57:15.997 main      INFO WATER: Internal communication uses port: 54322
  +                                  Listening for HTTP and REST traffic on  http://192.168.1.28:54321/
  04:57:16.029 main      INFO WATER: H2O cloud name: 'mystats-cloud'
  04:57:16.029 main      INFO WATER: (v0.3) 'mystats-cloud' on /192.168.1.28:54321, discovery address /236.151.114.91:60567
  04:57:16.031 main      INFO WATER: Cloud of size 1 formed [/192.168.1.28:54321]
  04:57:16.032 main      INFO WATER: Log dir: '/tmp/h2ologs'

5. Point your web-browser to 

::

  http://localhost:54321/ 

The user interface will appear in your browser, and now H2O is ready to go. 

Useful Notes
""""""""""""   

First time users may need to download and install Java
in order to run H2O. The program is available free on the web, 
and can be quickly installed. Even though you will use java to 
run H2O, no programming is necessary. 

In the java command entered into the terminal the term -Xmx1g was 
used. Xmx is the amount of memory given to H2O.  If your data set is large,
give H2O more memory (for example, -Xmx4g gives H2O four gigabytes of
memory).  For best performance, Xmx should be 4x the size of your
data, but never more than the total amount of memory on your
computer.
