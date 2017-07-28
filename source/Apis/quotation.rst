List of Quotation by RFQ ID
===========================

To get list of all quotation inside RFQ on your account send a :py:class:`GET` request to :py:class:`/v1/quotations/$RFQ_ID/$QUOTATION_KEY`.

:py:class:`$RFQ_ID` is unique ID of an RFQ that you should put on your request.

:py:class:`$QUOTATION_KEY` is an optional unique ID for specific quotation that you want to get.

This list also accept 2 GET parameter, such as status and fields. Status can be filled with "success" if you want to get only the winning quotation. Fields can be input with string of field that you want to get, ie: "sup_name,quotation_detail".

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "https://indoproc.com/esourcing/v1/quotations/90"
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/x-www-form-urlencoded
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2

The response will be a JSON object with a key called :py:class:`quotations`. This will be set to an array of quotation objects, each of which will contain the standard quotation attributes.

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "quotation_key", "Integer", "The unique identifier for the Supplier or Company that submit the quotation."
   "sup_name", "string", "String that contains supplier name"
   "revision_no", "Integer", "Number that describe revision count on quotation"
   "quotation_date", "string", "the quotation date on RFQ; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "notes", "string", "string that contains notes for that quotation"
   "quotation_detail", "Array", "An array of object that contains item codes with quotation price and document for each item from user."
   "quotation_attachment", "Array", "An array contains quotation documents"
   "status", "string", "string that contains status of rfq whether qualified or not qualified. This variable will be shown if use has made decision."
 
RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 200 OK

RESPONSE BODY

.. code-block:: js
   :linenos:
 
	{
		"rfq": {
			"id": 90
		},
		"quotations": [
			{
				"quotation_key": 22,
				"sup_name": "PT Magenta Pharmacy",
                "quotation_date": "1496657311389",
                "notes": "Price will be updated if they are changes",
                "quotation_detail": {
                    "593525c34a7b615bcd317032": {
                        "price": "10000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317033": {
                        "price": "20000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317034": {
                        "price": "150000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317035": {
                        "price": "10000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317036": {
                        "price": "12000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317037": {
                        "price": "40000",
                        "docs": []
                    }
                }
            },
            {
                "quotation_key": "comp_42",
                "sup_name": "CV Sanita Pharma",
                "quotation_date": "1496657535290",
                "notes": "Price will be locked from our system",
                "quotation_detail": {
                    "593525c34a7b615bcd317032": {
                        "price": "10000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317033": {
                        "price": "12000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317034": {
                        "price": "13000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317035": {
                        "price": "14000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317036": {
                        "price": "11000",
                        "docs": []
                    },
                    "593525c34a7b615bcd317037": {
                        "price": "13000",
                        "docs": []
                    }
                }
            }
        ]
    }


