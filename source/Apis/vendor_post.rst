Add New Vendors
===============

To create a new vendor to your account send a :py:class:`POST` request to :py:class:`/v1/vendors`.

CURL EXAMPLE

.. code-block:: js
   :linenos:

   curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer 12d3ee8b78ea8d4d09175ebf65c25584d7b269b2" "http://indoproc.com/esourcing/v1/vendors" -D "$REQUEST_BODY"
 
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
   
   "sup_name", "string", "Supplier's company name"
   "sup_type", "string", "Supplier's Company type (PT, CV, PO, Firma, BUMN, Koperasi)"
   "contact_person", "string", "Supplier company's contact_person / PIC"
   "sup_email", "string", "contact person / PIC 's email"
   "sup_phone", "string", "contact person / PIC 's phone number"
   "categories", "array", "vendor's categories"
   
These are the sample of Request Body:

.. code-block:: js
   :linenos:

   {
      "sup_name" : "Meia Sarah Sehat Makmur",
      "sup_type" : "PT",
      "contact_person" : "Meia Sarahian",
      "sup_email" : "meia@sarah.com",
      "sup_phone" : "08996477764",
      "categories" : ["Building & Construction", "Elektronik"]
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
   
   "_id", "integer", "The unique identifier for the vendor, you can use this attribute to retrieve the vendor list by sending :py:class:`GET` request"

.. code-block:: js
   :linenos:
 
   {
       "vendor": {
            "_id": 39
        }
   }

