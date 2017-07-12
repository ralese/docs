Getting Started
===============

To list all of the Block Storage volumes on your account send a :py:class:`GET` request to :py:class:`/v2/volumes`.

The response will be a JSON object with a key called :py:class:`volumes`. This will be set to an array of volume objects, each of which will contain the standard volume attributes.

The :py:class:`region` may be provided as query paramater in order to restrict results to volumes available in a specific region. For exmple: :py:class:`/v2/volumes?region=nycl`

.. csv-table::
   :header: "Name", "Type", "Description"
   :widths: 2, 2, 6
   
   "id", "string", "The unique identifier for the Block Storage volume."
   "region", "object", "The region that the Block Storage volume is located in. When setting a region, the value should be the slug identifier for the region. When you query a Block Storage volume, the entire region object will be returned."
   "droplet_ids", "array", "An array containing the IDs of the Droplets the volume is attached to. Note that at this time, a volume can only be attached to a single Droplet."
   "name", "string", "A human-readable name for the Block Storage volume. Must be lowercase and be composed only of numbers, letters and '-', up to a limit of 64 characters."
   "description", "string", "An optional free-form text field to describe a Block Storage volume."
   "size_gigabytes", "number", "The size of the Block Storage volume in GiB (1024^3)."
   "created_at", "string", "A time value given in ISO8601 combined date and time format that represents when the Block Storage volume was created."
   "droplet_ids", "array", "This attribute is an array of the Droplets that the volume is attached to."
   
CURL EXAMPLE::

 curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer b7d03a6947b217efb6f3ec3bd3504582" "https://api.digitalocean.com/v2/volumes?region=nyc1"

REQUEST HEADERS::

 Content-Type: application/json
 Authorization: Bearer b7d03a6947b217efb6f3ec3bd3504582
 
RESPONSE HEADERS::

 content-type: application/json; charset=utf-8
 status: 200 OK
 ratelimit-limit: 5000
 ratelimit-remaining: 4823
 ratelimit-reset: 1444931833

RESPONSE BODY

.. code-block:: js
   :linenos:
 
   {
    "volumes": [
     {
      "id": "506f78a4-e098-11e5-ad9f-000f53306ae1",
      "region": {
       "name": "New York 1",
       "slug": "nyc1",
       "sizes": [
        "512mb",
        "1gb",
        "2gb",
        "4gb",
        "8gb",
        "16gb",
        "32gb",
        "48gb",
        "64gb"
       ],
       "features": [
        "private_networking",
        "backups",
        "ipv6",
        "metadata"
       ],
       "available": true
      },
      "droplet_ids": [

      ],
      "name": "example",
      "description": "Block store for examples",
      "size_gigabytes": 10,
      "created_at": "2016-03-02T17:00:49Z"
     }
    ],
    "links": {
    },
    "meta": {
     "total": 1
    }
   }


