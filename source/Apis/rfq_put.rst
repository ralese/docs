Edit an RFQ
===========

To edit an existing RFQ on your account send a :py:class:`PUT` request to :py:class:`/v1/rfqs`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X POST -H "Content-Type: application/application/x-www-form-urlencoded" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "http://indoproc.com/esourcing/v1/rfqs/$id" -D "$REQUEST_BODY"

$id is a parameter that should be filled by RFQ ID.
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/x-www-form-urlencoded
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2
   
REQUEST BODY

These are the attributes that can be added to the array of request body:

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "title", "string", "RFQ title"
   "due_date", "string", "the due date of RFQ in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "required_date", "string", "the required date of RFQ items in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "description", "string", "An optional free-form text field to describe the RFQ"

These are the sample of Request Body:

.. code-block:: js
   :linenos:

   {
       "title": "Lorem Ipsum",
       "due_date": "1500632385539",
       "required_date": "1501237194007",
       "description": "Lorem Ipsum Dolor Sit Amet"
   }

RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 201 Created

RESPONSE BODY

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "_id", "integer", "The unique identifier for the RFQ, you can use this attribute to retrieve the RFQ list by sending :py:class:`GET` request"

.. code-block:: js
   :linenos:
 
   {
       "rfq": {
            "_id": 1
        }
   }

