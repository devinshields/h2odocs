ImportFiles
^^^^^^^^^^^

Description
"""""""""""

   Read in a file from the local host filesystem into H2O
   memory. (Warning: Every host in the cluster must have this file
   visible locally!)

URL
"""

   http://<h2oHost>:<h2oApiPort>/ImportFiles.json

Input parameters
""""""""""""""""

   path [required]

      Path name of file to import.

Output JSON elements
"""""""""""""""""""""""

   succeeded [array of objects]

      A list of files that have been successfully imported, and their
      respective DKV storage keys.

   failed [array of objects]

      A list of files that were requested to be imported, but could not be.

Error JSON elements
"""""""""""""""""""""""

   error [string]

      Required argument not specified.

      File not found.

HTTP response codes
""""""""""""""""""""""
   
   200 OK

      Success and error responses are identical.

Success Example
"""""""""""""""

.. literalinclude:: ImportFiles_success_1.rest

Error Example
"""""""""""""

.. literalinclude:: ImportFiles_error_1.rest
