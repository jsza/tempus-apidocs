=========
Resources
=========

These are all available under https://tempus.xyz/api

Maps
----

.. http:any:: /maps/id/{id}

    :arg id: A map ID.

    Retrieve a `Map`_ resource.

    :statuscode 404: Map not found.

    .. sourcecode:: js

        {
            "error": "Map not found."
        }


.. http:any:: /maps/name/{name}

    :arg name: A map name.

    Retrieve a `Map`_ resource.

    :statuscode 404: Map not found.

    .. sourcecode:: js

        {
            "error": "Map not found."
        }

Map
---

.. http:get:: /fullOverview

    Retrieve the full overview for a map.

    .. sourcecode:: json

        {
            "map_info": {
                "id": 1,
                "name": "jump_beef"
            },
            "tier_info": {
                "demoman": 2,
                "soldier": 2
            },
            "authors": [
                {
                    "id": 53,
                    "name": "Bevo"
                }
            ],
            "videos": {
                "demoman": null,
                "soldier": "uGZygTWjoB8"
            },
            "soldier_runs": [
                {
                    "duration": 61.6796624660492,
                    "id": 76057,
                    "name": "pumpkidder",
                    "steamid": "STEAM_0:1:20342129"
                },
            ],
            "demoman_runs": [
                {
                    "duration": 54.3825755119324,
                    "id": 5164,
                    "name": "Zike1017 \u30c4",
                    "steamid": "STEAM_0:1:45050273"
                }
            ],
            "zone_counts": {
                "bonus": 1,
                "bonus_end": 1,
                "course": 3,
                "course_end": 2,
                "map": 1,
                "map_end": 1,
                "misc": 8,
                "trick": 1
            }
        }


    :>json integer map_info: Name and ID.
    :>json string tier_info: Tier grouped by class.
    :>json object authors: Those who made the map.
    :>json object videos: YouTube video IDs grouped by class.
    :>json array soldier_runs: Array of soldier runs.
    :>json array demoman_runs: Array of demoman runs.
    :>json object zone_counts: Total number of zones in the database,
                               grouped by type.

.. http:any:: /zones/typeindex/{type}/{index}

    :arg type: Zone type.
    :arg index: Zone index.

    Retrieve a `Zone`_ resource for this map, type and index.

    :statuscode 404: Zone not found.

    .. sourcecode:: js

        {
            "error": "Zone not found."
        }


Players
-------

.. http:any:: /players/id/{id}

    :arg id: A player ID.

    Retrieve a `Player`_ resource.

    :statuscode 404: Player not found.

    .. sourcecode:: js

        {
            "error": "Player not found."
        }

.. http:any:: /players/steamid/{steamid}

    :arg steamid: A player's 64-bit Steam Community ID.

    Retrieve a `Player`_ resource.

    :statuscode 404: Player not found.

    .. sourcecode:: js

        {
            "error": "Player not found."
        }

Player
------

.. http:get:: /info

    Retrieve a player's info.

    .. sourcecode:: json

        {
            "id": 39902,
            "name": "fox",
            "steamid": "STEAM_0:0:43167835",
            "first_seen": 1416160045.73942,
            "last_seen": 1510146209.76025,
            "country": "Ukraine"
        }

    :>json integer id: Player ID.
    :>json string name: In-game name.
    :>json string steamid: Steam ID.
    :>json float first_seen: Unix timestamp of first connect.
    :>json float last_seen: Unix timestamp of most recent connect.
    :>json string country: Country name.

.. http:get:: /rank

    Retrieve a player's rank info.

    .. sourcecode:: json

        {
            "player_info": {
                "id": 39902,
                "name": "fox",
                "steamid": "STEAM_0:0:43167835",
                "first_seen": 1416160045.73942,
                "last_seen": 1510146209.76025,
                "country": "Ukraine"
            },
            "rank_info": {
                "points": 254988.0,
                "rank": 1,
                "total_ranked": 54212
            },
            "class_rank_info": {
                "3": {
                    "points": 202270.5,
                    "rank": 1,
                    "title": "Emperor",
                    "total_ranked": 40324
                },
                "4": {
                    "points": 52717.5,
                    "rank": 6,
                    "title": "Prince",
                    "total_ranked": 28427
                }
            }
        }

    :>json object player_info: Player's info. See **GET /info** above.


.. http:get:: /stats

    Retrieve a player's rank statistics.

    .. sourcecode:: json

        {
            "player_info": {
                "country": "Ukraine",
                "country_code": "UA",
                "first_seen": 1416160045.73942,
                "id": 39902,
                "last_seen": 1510146209.76025,
                "name": "fox",
                "steamid": "STEAM_0:0:43167835"
            },
            "rank_info": {
                "points": 255003.0,
                "rank": 1,
                "total_ranked": 54212
            },
            "class_rank_info": {
                "3": {
                    "points": 202285.5,
                    "rank": 1,
                    "title": "Emperor",
                    "total_ranked": 40324
                },
                "4": {
                    "points": 52717.5,
                    "rank": 6,
                    "title": "Prince",
                    "total_ranked": 28427
                }
            },
            "country_rank_info": {
                "rank": 1,
                "total_ranked": 434
            },
            "country_class_rank_info": {
                "3": {
                    "rank": 1,
                    "total_ranked": 276
                },
                "4": {
                    "rank": 1,
                    "total_ranked": 243
                }
            },
            "pr_stats": {
                "bonus":
                    { "count": 927, "points": 14437.0 },
                "course":
                    { "count": 500, "points": 11680.0 },
                "map":
                    { "count": 783, "points": 45410.0 },
                "trick":
                    { "count": 122, "points": 0.0 }
            },
            "top_stats": {
                "bonus":
                    { "count": 271, "points": 5451.0 },
                "course":
                    { "count": 121, "points": 8740.0 },
                "map":
                    { "count": 205, "points": 26355.0 },
                "trick":
                    { "count": 78, "points": 0.0 }
            },
            "wr_stats": {
                "bonus":
                    { "count": 277, "points": 15730.0 },
                "course":
                    { "count": 167, "points": 38350.0 },
                "map":
                    { "count": 247, "points": 88850.0 },
                "trick":
                    { "count": 23, "points": 0.0 }
            },
            "zone_count": {
                "bonus":
                    { "count": 481 },
                "bonus_end":
                    { "count": 481 },
                "checkpoint":
                    { "count": 886 },
                "course":
                    { "count": 260 },
                "course_end":
                    { "count": 163 },
                "linear":
                    { "count": 302 },
                "map":
                    { "count": 399 },
                "map_end":
                    { "count": 398 },
                "misc":
                    { "count": 311 },
                "special":
                    { "count": 114 },
                "trick":
                    { "count": 104 }
            }
        }

    :>json object player_info: Player's info. See **GET /info** above.
    :>json object zone_count: Total number of zones in the database, grouped by
                              type.
