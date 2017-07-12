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
