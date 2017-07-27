List all RFQ List
=================

To list all of the RFQ on your account send a :py:class:`GET` request to :py:class:`/v1/rfqs`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/application/x-www-form-urlencoded" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "http://indoproc.com/esourcing/v1/rfqs/"
 
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
   "rfq_date", "string", "RFQ created date in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "description", "string", "An optional free-form text field to describe the RFQ"
   "lines", "object", "An object contains lists of item in the RFQ"
   "rfq_no", "Integer", "Numeral count of RFQ that created by the creator company"
   "comp_name", "String", "Name of company who create the RFQ"
   "status", "String", "the status of the RFQ"
 
RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 200 OK

RESPONSE BODY

.. code-block:: js
   :linenos:
 
   {
       "rfqs": [
        {
            "_id": 9,
            "title": "Pengadaan Lorem Ipsum Dolor Sit Amet",
            "due_date": "1492668000613",
            "required_date": "1493100000783",
            "rfq_date": "1492066348215",
            "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            "lines": {
                "0": {
                    "product_name": "Lorem Ipsum",
                    "specification": "quis 28, lorem-ipsum 55",
                    "uom": "Units",
                    "qty": "50",
                    "estimated_price": "2500000",
                    "line_id": "58ef20294a7b614c8e224322",
                    "each_price": "50000",
                    "status": "active",
                    "docs": {}
                }
            },
            "rfq_no": 1,
            "comp_name": "PT. Inkomaro Indoproc",
            "version": 1,
            "status": "Active"
        },
		
		...
		
        ],
        "links": {
            "next": "http://etender.andy.indoproc.xyz/v1/rfqs?page=2",
            "last": "http://etender.andy.indoproc.xyz/v1/rfqs?page=3"
        },
        "meta": {
            "total": 42
        }
   }


