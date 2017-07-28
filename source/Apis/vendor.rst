List all Vendor List
====================

To list all of the vendor on your account send a :py:class:`GET` request to :py:class:`/v1/vendors`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "https://indoproc.com/esourcing/v1/vendors/"
 
REQUEST HEADERS

.. code-block:: js
   :linenos:

   Content-Type: application/x-www-form-urlencoded
   Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2

The response will be a JSON object with a key called :py:class:`vendors`. This will be set to an array of vendor objects, each of which will contain the standard vendor attributes.

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "_id", "Integer", "Unique identifier for the Vendor."
   "sup_name", "string", "String that contains company name of vendor"
   "sup_type", "string", "String that contains company type of vendor"
   "contact_person", "string", "String that contains a person name that you should contact for this vendor"
   "sup_email", "string", "String that contains an email of contact for this vendor"
   "sup_phone", "string", "String that contains a phone of contact for this vendor"
   "categories", "Array", "An array that contains all categories for this vendor"
   "comp_srl", "String", "The unique identifier for the creator company"
   "links", "Object", "Object that contains link from next and last url of vendor data"
   "meta", "Object", "Object that contains count of vendors data in your account"
 
RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 200 OK

RESPONSE BODY

.. code-block:: js
   :linenos:
   
	{
		"vendors": [
            {
                "_id": 27,
                "sup_name": "Antavalue Building Construction",
                "sup_type": "PT",
                "contact_person": "Samuel",
                "sup_email": "samuel@antavalue.com",
                "sup_phone": "0923-0999-0293",
                "categories": {
                    "0": "Industrial & Tools",
                    "1": "Building & Construction"
                },
                "comp_srl": "8"
            },
            {
                "_id": 28,
                "sup_name": "Klondike Valueline",
                "sup_type": "PT",
                "contact_person": "Akhmad",
                "sup_email": "akhmad90@klondikeval.com",
                "sup_phone": "0988-3321-5232",
                "categories": {
                    "0": "Custom Printing"
                },
                "comp_srl": "8"
            }
        ],
        "links": {
            "next": "http://etender.bernard.indoproc.xyz/v1/vendors?page=2",
            "last": "http://etender.bernard.indoproc.xyz/v1/vendors?page=2"
        },
        "meta": {
            "total": 25
        }
    }
	