=========
Overview
=========

Making Requests
===============

All requests must set ``Accept: application/json``. Otherwise, the website
HTML will be served.

Error handling
==============

The API will return a JSON response for certain errors. For example, this  GET
request to https://tempus.xyz/api/maps/doesnotexist/fullOverview:

.. sourcecode:: http

    HTTP/1.1 404 NOT FOUND
    Content-Type: text/javascript

    {
        "error": "Map not found."
    }

Some error responses will have additional information, but the ``error`` key
is always set.
