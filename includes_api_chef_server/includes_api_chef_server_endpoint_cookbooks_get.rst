.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.


The ``GET`` method is used to return a hash of all cookbooks and cookbook versions. 

This method has the following parameters:

.. list-table::
   :widths: 200 300
   :header-rows: 1

   * - Parameter
     - Description
   * - ``num_versions=n``
     - |num_versions|

**Request**

.. code-block:: none

   GET /organizations/NAME/cookbooks

**Response**

The response is similar to:

.. code-block:: none

   {
     "apache2" => {
       "url" => "https://localhost/cookbooks/apache2",
       "versions" => [
         {"url" => "https://localhost/cookbooks/apache2/5.1.0",
          "version" => "5.1.0"},
         {"url" => "https://localhost/cookbooks/apache2/4.2.0",
          "version" => "4.2.0"}
       ]
     },
     "nginx" => {
       "url" => "https://localhost/cookbooks/nginx",
       "versions" => [
         {"url" => "https://localhost/cookbooks/nginx/1.0.0",
          "version" => "1.0.0"},
         {"url" => "https://localhost/cookbooks/nginx/0.3.0",
          "version" => "0.3.0"}
       ]
     }
   }

**Response Codes**

.. list-table::
   :widths: 200 300
   :header-rows: 1

   * - Response Code
     - Description
   * - ``200``
     - |response code 200 ok|
   * - ``401``
     - |response code 401 unauthorized|
   * - ``403``
     - |response code 403 forbidden|
