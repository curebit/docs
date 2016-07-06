.. _api_v2/offers:
.. include:: /partials/common.rst

Offers
======

This API allows you to access offers.

|br|

.. code-block:: url

   GET /offers/<id>

Returns offer.

.. container:: ptable

   ================= ========================================================
   Parameter         Description
   ================= ========================================================
   site_slug         Your Talkable Site ID. You can get this from your
                     Talkable dashboard after you log in and create a site.
   id                Offer ID obtained with :ref:`origin creation <api_v2/origins>`.
   interpolations    Optional: array of interpolations to return in response
   ================= ========================================================

Example
-------

.. code-block:: url

   GET https://www.talkable.com/api/v2/offers/89238912?site_slug=my-store&api_key=i9uil7nQgDjucCiTJu

Sample response:

.. code-block:: javascript

   {
     "ok": true,
     "result": {
       "offer": {
         "id": 89238912,
         "short_url_code": "dZpBwd",
         "email": "customer@example.com",
         "show_url": "https://www.talkable.com/x/iEov9g",
         "claim_url": "https://www.talkable.com/x/5B3xO1"
       }
     }
   }
