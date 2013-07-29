From source code (Github)
----------------------------

These instructions assume you are using Linux, MacOSX, or Cygwin (on Windows).

1. Create a git clone of the H2O repository.

 ::
  
  git clone https://github.com/0xdata/h2o.git


2. Build H2O from source.  You must have Java JDK 1.6 or higher.
   After the build finishes, some JUnit tests will run automatically.

 ::

    $ cd h2o
    $ make
    (a lenghthy output will be generated)



3.  The build produces target/h2o.jar.  Now run h2o.jar from the
    command line.  Note that Xmx is the amount of memory given to
    H2O. If your data set is large, increase the number immediately
    following Xmx from the default of 2. As a rule, the amount of
    memory given should be about 4 times the size of your data, but no
    larger than the total memory of your computer. 

 ::

    $ java -Xmx2g -jar target/h2o.jar

 (Output below)

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

4. Point your web browser to the HTTP URL (``http://your-ip-address:54321``); H2O will run from there.  

