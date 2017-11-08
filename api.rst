=========
Overview
=========

Error handling
==============

The API will return a JSON response for certain errors. For example, if you
make a GET request to https://tempus.xyz/api/maps/doesnotexist/fullOverview,
you will get HTTP 404 and:

.. sourcecode:: js

    {
        "error": "Map not found."
    }

All errors will be structured as above, so you can use the messages directly
in whatever application you are writing.
