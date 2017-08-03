Create an RFQ
=============

To create a new RFQ to your account send a :py:class:`POST` request to :py:class:`/v1/rfqs`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "http://indoproc.com/esourcing/v1/rfqs" -D "$REQUEST_BODY"
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/json
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2
   
REQUEST BODY

These are the attributes that can be added to the object of request body:

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "title", "string", "RFQ title"
   "due_date", "string", "the due date of RFQ in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "required_date", "string", "the required date of RFQ items in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "description", "string", "An optional free-form text field to describe the RFQ"
   "lines", "object", "An object contains lists of item in the RFQ. See the :py:class:`lines` attributes format below."
   "rfq_type", "string", "The type of the RFQ (Public/Private)"
   "rfq_category", "String", "The category of the RFQ"
   "rfq_location", "String", "The RFQ Location"

These are the attributes of items that can be added to :py:class:`lines` object described above:
   
.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "product_name", "string", "Name of product/item"
   "specification", "string", "Specification of item"
   "uom", "string", "Unit of Measurement"
   "qty", "Integer", "Quantity of item"
   "estimated_price", "Integer", "Total price of the specific item"
   "external_id", "string", "[Optional] Field that used to link to external detail identifier"
   
These are the sample of Request Body:

.. code-block:: js
   :linenos:

   {
       "title": "Lorem Ipsum",
       "due_date": "1500632385539",
       "required_date": "1501237194007",
       "description": "Lorem Ipsum Dolor Sit Amet",
       "lines": [
           {
                "product_name": "Super Table",
                "specification": "Dimension: 4 x 3 x 1 in meter",
                "uom": "Pcs",
                "qty": 12,
                "estimated_price": 12000000
           },
		   
		   ...
		   
       ],
       "rfq_type": "private",
       "rfq_category": "Elektronik",
       "rfq_location": "Bali"
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
            "_id": 99
        }
   }

