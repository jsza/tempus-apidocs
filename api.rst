=========
Overview
=========

Making Requests
===============

It used to be that requests needed to set ``Accept: application/json``. Now,
it may be omitted for convenience. Note that the API does not support XML at
this time.

Error handling
==============

The API will return a JSON response for certain errors. For example, this  GET
request to https://tempus.xyz/api/maps/name/doesnotexist/fullOverview:

.. sourcecode:: http

    HTTP/1.1 404 NOT FOUND
    Content-Type: text/javascript

    {
        "error": "Map not found."
    }

Some error responses will have additional information, but the ``error`` key
is always set.
