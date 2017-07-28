Get Specific Vendor
===================

To get specific vendor on your account send a :py:class:`GET` request to :py:class:`/v1/vendors/$VENDOR_ID`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "https://indoproc.com/esourcing/v1/vendors/1"
 
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
 
RESPONSE HEADERS

.. code-block:: js
   :linenos:
   
   content-type: application/json; charset=utf-8
   status: 200 OK

RESPONSE BODY

.. code-block:: js
   :linenos:
   
   {
        "_id": 1,
        "sup_name": "Axxon Retails",
        "sup_type": "PT",
        "contact_person": "Alvin",
        "sup_email": "alvin@axxpha.com",
        "sup_phone": "08785855645",
        "categories": {
            "0": "Custom Printing",
            "1": "Komputer & Aksesoris",
            "2": "Elektronik",
            "3": "Perlengkapan Kantor"
        },
        "comp_srl": "1"
    }
	


