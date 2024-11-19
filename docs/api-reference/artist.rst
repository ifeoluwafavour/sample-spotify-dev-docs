Artist
######

Get Artist
**********

Get the information for a single Spotify artist identified by their unique Spotify ID.

**GET** */artists/{id}*

Parameters
==========

Path parameter
--------------

.. list-table::
	:header-rows: 0 

	* - {id} string Required
	  - The Spotify ID of the artist

Sample Request
==============

.. code-block:: console

	curl --request GET \
	  --url https://api.spotify.com/v1/artists/0TnOYISbd1XYRBk9myaseg \
	  --header 'Authorization: Bearer 1POdFZRZbvb...qqillRxMr2z'


Sample Response
===============

.. code-block:: console

	{
	  "external_urls": {
	    "spotify": "string"
	  },
	  "followers": {
	    "href": "string",
	    "total": 0
	  },
	  "genres": [
	    "Prog rock",
	    "Grunge"
	  ],
	  "href": "string",
	  "id": "string",
	  "images": [
	    {
	      "url": "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228",
	      "height": 300,
	      "width": 300
	    }
	  ],
	  "name": "string",
	  "popularity": 0,
	  "type": "artist",
	  "uri": "string"
	}


Response Definitions
====================

200 - The artist’s information





















