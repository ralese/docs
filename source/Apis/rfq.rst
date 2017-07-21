List all RFQ List
=================

To list all of the RFQ on your account send a :py:class:`GET` request to :py:class:`/v1/rfqs`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "https://indoproc.com/esourcing/v1/rfqs/"
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/x-www-form-urlencoded
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2

The response will be a JSON object with a key called :py:class:`rfqs`. This will be set to an array of RFQ objects, each of which will contain the standard RFQ attributes.

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "_id", "Integer", "The unique identifier for the RFQ."
   "title", "string", "RFQ title"
   "due_date", "string", "the due date of RFQ in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "required_date", "string", "the required date of RFQ items in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "rfq_date", "string", "RFQ created date in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "description", "string", "An optional free-form text field to describe the RFQ"
   "lines", "Array", "An array contains lists of item in the RFQ"
   "rfq_no", "Integer", "Numeral count of RFQ that created by the creator company"
   "comp_srl", "String", "The unique identifier for the creator company"
   "comp_name", "String", "Name of company who create the RFQ"
   "version", "Integer", "The number of RFQ version based on number of update/data changes"
   "created_date", "string", "RFQ created date in a string type; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "created_by", "String", "Email of the RFQ creator"
 
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
            "_id": 14,
            "title": "Indomie Rasa Ayam Bawang",
            "due_date": {
                "$date": {
                    "$numberLong": "1492668000613"
                }
            },
            "required_date": {
                "$date": {
                    "$numberLong": "1493100000783"
                }
            },
            "rfq_date": {
                "$date": {
                    "$numberLong": "1492066348215"
                }
            },
            "description": "Bumbu dari ayam yang sudah mati",
            "lines": {
                "0": {
                    "product_name": "Indomie",
                    "specification": "Rasa Ayam Bawang",
                    "uom": "Box isi 48",
                    "qty": "50",
                    "estimated_price": "2500000",
                    "line_id": "58ef20294a7b614c8e224322",
                    "each_price": "50000",
                    "status": "active",
                    "docs": {}
                }
            },
            "invitation": {
                "0": {
                    "sup_name": "PT. Indofood Sukses Makmur",
                    "contact": "Anthony Salim",
                    "sup_email": "info@indofood.id",
                    "sup_id": "4",
                    "status": "pending"
                }
            },
            "rfq_no": 1,
            "comp_srl": "32",
            "comp_name": "Indoproc",
            "version": 1,
            "status": "cancelled",
            "created_date": {
                "$date": {
                    "$numberLong": "1492066345000"
                }
            },
            "created_by": "andywihalim2@gmail.com"
        },
        ],
        "links": {
            "next": "http://etender.andy.indoproc.xyz/v1/rfqs?page=2",
            "last": "http://etender.andy.indoproc.xyz/v1/rfqs?page=3"
        },
        "meta": {
            "total": 42
        }
   }


