List of Quotation by RFQ ID
===========================

To list all quotation inside RFQ on your account send a :py:class:`GET` request to :py:class:`/v1/quotations`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "https://indoproc.com/esourcing/v1/quotations/"
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/x-www-form-urlencoded
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2

The response will be a JSON object with a key called :py:class:`quotations`. This will be set to an array of quotation objects, each of which will contain the standard quotation attributes.

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "sup_id", "Integer", "The unique identifier for the Supplier or Company that submit the quotation."
   "sup_name", "string", "String that contains supplier name"
   "revision_no", "Integer", "Number that describe revision count on quotation"
   "quotation_date", "string", "the quotation date on RFQ; contains Unix Time Stamp (miliseconds since Jan 01 1970 in UTC)"
   "notes", "string", "string that contains notes for that quotation"
   "quotation_detail", "Array", "An array of object that contains item codes with quotation price and document for each item from user."
   "quotation_attachment", "Array", "An array contains quotation documents"
   "status", "string", "string that contains status of rfq whether qualified or not qualified"
 
RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 200 OK

RESPONSE BODY

.. code-block:: js
   :linenos:
 
   {
    "1": {
        "sup_id": "1",
        "sup_name": "PT. Angkasa Beverage",
        "revision_no": 0,
        "quotation_date": "Fri May 05 2017 17:26:41 GMT+0700 (SE Asia Standard Time)",
        "notes": "Test data 1",
        "quotation_detail": {
            "590c4a664a7b6137ff7ba8c2": {
                "price": "10000000",
                "docs": {
                    "0": {
                        "file_name": "18ced9e0568fa564ccc5495480e58e04.jpg",
                        "doc_name": "Arm_Astalos.jpg"
                    }
                }
            },
            "590c4a664a7b6137ff7ba8c3": {
                "price": "18000000",
                "docs": {
                    "0": {
                        "file_name": "e6199f0964b6e02a237d83d75007382d.jpg",
                        "doc_name": "Arm_Gammoth.jpg"
                    }
                }
            }
        },
        "quotation_attachment": {
            "0": {
                "file_name": "2e79ce72899d1112d93be41bc2577a2d.jpg",
                "doc_name": "Arm_Mizutsune.jpg"
            }
        },
        "status": "unsuccess"
    },
    "comp_38": {
        "sup_id": "38",
        "sup_name": "Bernard Ltd",
        "revision_no": 0,
        "quotation_date": "Fri May 05 2017 17:28:37 GMT+0700 (SE Asia Standard Time)",
        "notes": "Ask us",
        "quotation_detail": {
            "590c4a664a7b6137ff7ba8c2": {
                "price": "9000000",
                "docs": {
                    "0": {
                        "file_name": "23d345480d798293fc9cdb4efb58f2a0.jpg",
                        "doc_name": "Arm_Mizutsune.jpg"
                    }
                }
            },
            "590c4a664a7b6137ff7ba8c3": {
                "price": "12000000",
                "docs": {
                    "0": {
                        "file_name": "264a442b5ee14a2864c02c24ed1b8596.jpg",
                        "doc_name": "Arm_Mizutsune.jpg"
                    }
                }
            }
        },
        "quotation_attachment": {
            "0": {
                "file_name": "dba262521b176f1ff37ca159178bb110.jpg",
                "doc_name": "Arm_Mizutsune.jpg"
            }
        },
        "status": "success"
    }
   }


