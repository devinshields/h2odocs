Using R (after installing H2O)
------------------------------

From the R Console
""""""""""""""""""

These instructions assume you are using a recent version of R, and are familiar with the basics of using command line. In order to use H2O from inside of R, users will first need to follow the quick start instructions for installing H2O via github. 

Assuming the user has already installed the h2o directory from github, **from the terminal** change the current directory to …/h2o/R

::

  $ cd "file path"/h2o/R

Once in the correct directory /h2o/R enter the command

::

  $ R CMD build h2o-package

which creates a .tar.gz file, and returns the following output:

::

  * checking for file ‘h2o-package/DESCRIPTION’ ... OK
  * preparing ‘h2o’:
  * checking DESCRIPTION meta-information ... OK
  * checking for LF line-endings in source and make files
  * checking for empty or unneeded directories
  * building ‘h2o_1.7.0.99999.tar.gz’

Minimize the terminal window and return to the R console. 

In the R console install the library by entering the following command at the prompt:

::

  >install.packages("**directory for h2o R**/ **tar.gz file name**", repos = NULL, type = "source")
  
**To find the directory for h2o R**, in the terminal window enter 

::

  $ pwd

This command *prints working directory*, and returns a path to the h2o R directory that R can follow. Copy the output to your R console in place of "**directory for h2o R**"

**To find the tar.gz file name**, in the terminal window enter 

::

  $ ls

This command prints a list of all of the files in that directory. From that list find the file with the extension .tar.gz, and use this file name in place of  ** tar.gz file name **" in the R command prompt. 

For example, a user at 0x data enters the following into her R terminal at the command prompt:

::

  >install.packages("/Users/Irene/Documents/h2o/R/h2o_1.7.0.99999.tar.gz", repos = NULL, 
  type = "source")

Which returns the following output

::

  * installing *source* package ‘h2o’ ...
  ** R
  ** demo
  ** inst
  ** preparing package for lazy loading
  Creating a generic function for ‘colnames’ from package ‘base’ in package ‘h2o’
  Creating a generic function for ‘nrow’ from package ‘base’ in package ‘h2o’
  Creating a generic function for ‘ncol’ from package ‘base’ in package ‘h2o’
  Creating a generic function for ‘summary’ from package ‘base’ in package ‘h2o’
  Creating a generic function for ‘as.data.frame’ from package ‘base’ in package ‘h2o’
  ** help
  *** installing help indices
  ** building package indices
  ** testing if installed package can be loaded
  * DONE (h2o)

To start running H2O from the R console the user must build a path for R to talk to H2O, which requires starting an instance of H2O. Users will need to return to the terminal. 

::

  > require(h2o)

which returns the following output

::

  Loading required package: h2o
  Loading required package: RCurl
  Loading required package: bitops
  Loading required package: rjson

In the R terminal enter

::

  > localH2O = new("H2OClient")

Minimize the R console and **return to the terminal.**
In the terminal enter the following commands

::
  
  $ cd .. # moves the user up one level in the directory
  $ cd target # moves the user into the directory where the h2o program is located
  $ java -Xmx2g -jar h2o.jar -name mystats-cloud # java command to run the h2o program 

This starts the h2o program, and returns output similar to the following: 

::

  10:57:27.038 main      INFO WATER: ----- H2O started -----
  10:57:27.041 main      INFO WATER: Build git branch: master
  10:57:27.041 main      INFO WATER: Build git hash: 67035d229a31ea5f7415e81f5cc192da700ea276
  10:57:27.042 main      INFO WATER: Build git describe: 67035d2
  10:57:27.042 main      INFO WATER: Build project version: 1.7.0.99999
  10:57:27.042 main      INFO WATER: Built by: 'Irene'
  10:57:27.042 main      INFO WATER: Built on: 'Tue Aug  6 10:55:12 PDT 2013'
  10:57:27.042 main      INFO WATER: Java availableProcessors: 2
  10:57:27.048 main      INFO WATER: Java heap totalMemory: 0.08 gb
  10:57:27.049 main      INFO WATER: Java heap maxMemory: 2.67 gb
  10:57:27.049 main      INFO WATER: ICE root: '/tmp'
  10:57:27.093 main      INFO WATER: Internal communication uses port: 54322
  +                                  Listening for HTTP and REST traffic on  http://  192.168.1.32:54321/
  10:57:27.183 main      INFO WATER: H2O cloud name: 'mystats-cloud'
  10:57:27.183 main      INFO WATER: (v1.7.0.99999) 'mystats-cloud' on /192.168.1.32:54321,   discovery address /236.151.114.91:60567
  10:57:27.192 main      INFO WATER: Cloud of size 1 formed [/192.168.1.32:54321]
  10:57:27.448 main      INFO WATER: Log dir: '/tmp/h2ologs'

Minimize the terminal window. *Users should be aware that in order for H2O to successfully run through R, an instance of H2O must also simultaneously be running. If the instance of H2O is stopped, the R program will no longer run, and work done will be lost.*

Return to the R console and enter 

::

  > h2o.checkClient(localH2O)

Which returns the following output

::

  Successfully connected to http://127.0.0.1:54321 

Users can now run H2O from their running R console. Additional R documentation can be found here

::

  https://github.com/0xdata/h2o/blob/master/R/h2o-package/h2o_package.pdf   

From R Studio
"""""""""""""

These instructions assume you are using a recent version of R, and are familiar with the basics of using command line. In order to use H2O from inside of R, users will first need to follow the quick start instructions for installing H2O via github. 

Assuming the user has already installed the h2o directory from github, **from the terminal** change the current directory to …/h2o/R

::

  $ cd "file path"/h2o/R

Once in the correct directory /h2o/R enter the command

::

  $ R CMD build h2o-package

which creates a .tar.gz file, and returns the following output:

::

  * checking for file ‘h2o-package/DESCRIPTION’ ... OK
  * preparing ‘h2o’:
  * checking DESCRIPTION meta-information ... OK
  * checking for LF line-endings in source and make files
  * checking for empty or unneeded directories
  * building ‘h2o_1.7.0.99999.tar.gz’

Minimize the terminal window and return to the R Studio GUI.
While location within the GUI may differ depending on each user's unique configuration, find the menu with **tabbed options Files, Plots, Packages, Help** 

Select the *Packages* tab

Choose *Install Packages* 

From the drop down menu select *Package Archive.*

Navigate through the helper that appears to H2O R directory. For example, a user at 0xdata would go to Documents ==> h2o ==> R and select the file ending in **'.tar.gz'. Click Open.**

On the resulting helper button **click Install.**

The R package will install. 

To start running H2O from the R console the user must build a path for R to talk to H2O, which requires starting an instance of H2O. Users will need to return to the terminal. 

::

  > require(h2o)

which returns the following output

::

  Loading required package: h2o
  Loading required package: RCurl
  Loading required package: bitops
  Loading required package: rjson

In the R terminal enter

::

  > localH2O = new("H2OClient")

Minimize the R console and **return to the terminal.**
In the terminal enter the following commands

::
  
  $ cd .. # moves the user up one level in the directory
  $ cd target # moves the user into the directory where the h2o program is located
  $ java -Xmx2g -jar h2o.jar -name mystats-cloud # java command to run the h2o program 

This starts the h2o program, and returns output similar to the following: 

::

  10:57:27.038 main      INFO WATER: ----- H2O started -----
  10:57:27.041 main      INFO WATER: Build git branch: master
  10:57:27.041 main      INFO WATER: Build git hash: 67035d229a31ea5f7415e81f5cc192da700ea276
  10:57:27.042 main      INFO WATER: Build git describe: 67035d2
  10:57:27.042 main      INFO WATER: Build project version: 1.7.0.99999
  10:57:27.042 main      INFO WATER: Built by: 'Irene'
  10:57:27.042 main      INFO WATER: Built on: 'Tue Aug  6 10:55:12 PDT 2013'
  10:57:27.042 main      INFO WATER: Java availableProcessors: 2
  10:57:27.048 main      INFO WATER: Java heap totalMemory: 0.08 gb
  10:57:27.049 main      INFO WATER: Java heap maxMemory: 2.67 gb
  10:57:27.049 main      INFO WATER: ICE root: '/tmp'
  10:57:27.093 main      INFO WATER: Internal communication uses port: 54322
  +                                  Listening for HTTP and REST traffic on  http://  192.168.1.32:54321/
  10:57:27.183 main      INFO WATER: H2O cloud name: 'mystats-cloud'
  10:57:27.183 main      INFO WATER: (v1.7.0.99999) 'mystats-cloud' on /192.168.1.32:54321,   discovery address /236.151.114.91:60567
  10:57:27.192 main      INFO WATER: Cloud of size 1 formed [/192.168.1.32:54321]
  10:57:27.448 main      INFO WATER: Log dir: '/tmp/h2ologs'

Minimize the terminal window. *Users should be aware that in order for H2O to successfully run through R, an instance of H2O must also simultaneously be running. If the instance of H2O is stopped, the R program will no longer run, and work done will be lost.*

Return to the R console and enter 

::

  > h2o.checkClient(localH2O)

Which returns the following output

::

  Successfully connected to http://127.0.0.1:54321 

Users can now run H2O from their running R console. Additional R documentation can be found in the R section of the main user documentation page. Users can also enter **??h2o** at any time to access help. 


Helpful Tips
""""""""""""

**Users can change the amount of memory allocated to H2O.** In the Java command entered in the terminal to start H2O the term **-Xmx2g** was used. Xmx is the amount of memory given to H2O. If your data set is large, give H2O more memory (for example, -Xmx4g gives H2O four gigabytes of memory). For best performance, Xmx should be 4x the size of your data, but never more than the total amount of memory on your computer. 

Each time a user wants to run a new instance of h2o a .tar.gz file must be created using the command **R CMD build h2o-package at the terminal prompt.** *It is not necessary to install the h2o package in R more than once.* 

Because H2O and H2O.R work together, they must be revised together. **If you receive an error indicating that H2O and the R package you are using are at different revisions** return to the "Quickstart from Github" and follow the instructions for updating H2O. 













