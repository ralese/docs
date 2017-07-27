Retrieve a specific RFQ
=======================

To retrieve a specific RFQ from your RFQ list send a :py:class:`GET` request to :py:class:`/v1/rfqs/$RFQ_ID`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/application/x-www-form-urlencoded" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "http://indoproc.com/esourcing/v1/rfqs/9"
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/x-www-form-urlencoded
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2

The response will be a JSON array with a key called :py:class:`rfqs`. This will be set to an object of RFQ arrays, each of which will contain the standard RFQ attributes.

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "_id", "Integer", "The unique identifier for the RFQ."
   "title", "string", "RFQ title"
   "due_date", "string", "the due date of RFQ in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "required_date", "string", "the required date of RFQ items in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "description", "string", "An optional free-form text field to describe the RFQ"
   "lines", "object", "An object contains lists of item in the RFQ"
   "rfq_type", "string", "The type of the RFQ (Public/Private)"
   "rfq_category", "String", "The category of the RFQ"
   "rfq_location", "String", "The RFQ Location"
   "rfq_date", "string", "RFQ created date in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "rfq_no", "Integer", "Numeral count of RFQ that created by the creator company"
   "comp_name", "String", "Name of company who create the RFQ"
   "status", "String", "the status of the RFQ"
   "total_estimated_price", "Integer", "Total estimated price of the RFQ"
 
RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 200 OK

RESPONSE BODY

.. code-block:: js
   :linenos:
 
   {
       "rfq":
        {
            "_id": 107,
            "title": "Lorem Ipsum",
            "due_date": "1500632385539",
            "required_date": "1501237194007",
            "description": "Lorem Ipsum Dolor Sit Amet",
            "lines": {
                "0": {
                    "product_name": "Super Table",
                    "specification": "Dimension: 4 x 3 x 1 in meter",
                    "uom": "Pcs",
                    "qty": 12,
                    "estimated_price": 12000000,
                    "line_id": "597954094a7b61116115d662",
                    "each_price": 1000000,
                    "status": "active",
                    "docs": {}
                }
            },
            "rfq_type": "private",
            "rfq_category": "Elektronik",
            "rfq_location": "Bali",
            "rfq_date": "1501088400000",
            "rfq_no": 44,
            "comp_name": "Indoproc",
            "status": "open",
            "total_estimated_price": 12000000
        }
   }


