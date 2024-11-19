Playlist
########

Get playlist
*************

Retrieve a Spotify user’s playlist

**GET** */playlist{playlist_id}*  

Parameters
===========

Path parameter
--------------

.. list-table::
	:header-rows: 0 

	* - {playlist_id} :sup:`string required`
	  - The ID of the playlist. Example: 3cEYpjA9oz9GiPac4AsH4n

Query parameters
-----------------

.. list-table::
	:header-rows: 0 

	* - market :sup:`string` 
	  - An ISO 3166-1 alpha-2 country code. If a country code is specified, only content that is available in that market will be returned. If a valid user access token is specified in the request header, the country associated with the user account will take priority over this parameter. Note: If neither market or user country are provided, the content is considered unavailable for the client. Users can view the country that is associated with their account in the account settings. Example: market=NG
	* - fields :sup:`string` 
	  - Filters for the query: a comma-separated list of the fields to return. If omitted, all fields are returned. For example, to get just the playlist's description and URI: fields=description,uri. A dot separator can be used to specify non-reoccurring fields, while parentheses can be used to specify reoccurring fields within objects. For example, to get just the added date and user ID of the adder: fields=tracks.items(added_at,added_by.id). Use multiple parentheses to drill down into nested objects, for example: fields=tracks.items(track(name,href,album(name,href))). Fields can be excluded by prefixing them with an exclamation mark, for example: fields=tracks.items(track(name,href,album(!name,href))). Example: fields=items(added_by.id,track(name,href,album(name,href))) 
	* - additional fields :sup:`string` 
	  - A comma-separated list of item types that your client supports besides the default track type. Valid types are: track and episode. Note: This parameter was introduced to allow existing clients to maintain their current behaviour and might be deprecated in the future. In addition to providing this parameter, make sure that your client properly handles cases of new types in the future by checking against the type field of each object.

Sample request
==============

.. code-block:: console

	curl --request GET \
	  --url https://api.spotify.com/v1/playlists/3cEYpjA9oz9GiPac4AsH4n \
	  --header 'Authorization: Bearer 1POdFZRZbvb...qqillRxMr2z'

Sample response
===============

.. code-block:: console

	{
	  "collaborative": false,
	  "description": "string",
	  "external_urls": {
	    "spotify": "string"
	  },
	  "followers": {
	    "href": "string",
	    "total": 0
	  },
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
	  "owner": {
	    "external_urls": {
	      "spotify": "string"
	    },
	    "followers": {
	      "href": "string",
	      "total": 0
	    },
	    "href": "string",
	    "id": "string",
	    "type": "user",
	    "uri": "string",
	    "display_name": "string"
	  },
	  "public": false,
	  "snapshot_id": "string",
	  "tracks": {
	    "href": "https://api.spotify.com/v1/me/shows?offset=0&limit=20",
	    "limit": 20,
	    "next": "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
	    "offset": 0,
	    "previous": "https://api.spotify.com/v1/me/shows?offset=1&limit=1",
	    "total": 4,
	    "items": [
	      {
	        "added_at": "string",
	        "added_by": {
	          "external_urls": {
	            "spotify": "string"
	          },
	          "followers": {
	            "href": "string",
	            "total": 0
	          },
	          "href": "string",
	          "id": "string",
	          "type": "user",
	          "uri": "string"
	        },
	        "is_local": false,
	        "track": {
	          "album": {
	            "album_type": "compilation",
	            "total_tracks": 9,
	            "available_markets": [
	              "CA",
	              "BR",
	              "IT"
	            ],
	            "external_urls": {
	              "spotify": "string"
	            },
	            "href": "string",
	            "id": "2up3OPMp9Tb4dAKM2erWXQ",
	            "images": [
	              {
	                "url": "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228",
	                "height": 300,
	                "width": 300
	              }
	            ],
	            "name": "string",
	            "release_date": "1981-12",
	            "release_date_precision": "year",
	            "restrictions": {
	              "reason": "market"
	            },
	            "type": "album",
	            "uri": "spotify:album:2up3OPMp9Tb4dAKM2erWXQ",
	            "artists": [
	              {
	                "external_urls": {
	                  "spotify": "string"
	                },
	                "href": "string",
	                "id": "string",
	                "name": "string",
	                "type": "artist",
	                "uri": "string"
	              }
	            ]
	          },
	          "artists": [
	            {
	              "external_urls": {
	                "spotify": "string"
	              },
	              "href": "string",
	              "id": "string",
	              "name": "string",
	              "type": "artist",
	              "uri": "string"
	            }
	          ],
	          "available_markets": [
	            "string"
	          ],
	          "disc_number": 0,
	          "duration_ms": 0,
	          "explicit": false,
	          "external_ids": {
	            "isrc": "string",
	            "ean": "string",
	            "upc": "string"
	          },
	          "external_urls": {
	            "spotify": "string"
	          },
	          "href": "string",
	          "id": "string",
	          "is_playable": false,
	          "linked_from": {},
	          "restrictions": {
	            "reason": "string"
	          },
	          "name": "string",
	          "popularity": 0,
	          "preview_url": "string",
	          "track_number": 0,
	          "type": "track",
	          "uri": "string",
	          "is_local": false
	        }
	      }
	    ]
	  },
	  "type": "string",
	  "uri": "string"
	}


Response definitions
====================

200: a playlist

.. list-table::
	:header-rows: 0 

	* - collaborative :sup:`boolean`
	  - true if the owner lets other users to modify the playlist
	* - description :sup:`string Nullable`
	  - The playlist description. Only returned for modified, verified playlists, otherwise null.
	* - external_urls :sup:`object`
	  - Known external URLs for this playlist.
	* - followers :sup:`object`
	  - Information about the followers of the playlist.
	* - {followers}/{href} :sup:`string Nullable`
	  - This will always be set to null, as the Web API does not support it at the moment.
	* - href :sup:`string`
	  - A link to the Web API endpoint providing full details of the playlist.
	* - id :sup:`string`
	  - The Spotify ID for the playlist
	* - images :sup:`array of ImageObject` 
	  - Images for the playlist. The array may be empty or contain up to three images. The images are returned by size in descending order. 
	* - name :sup:`string`
	  - The name of the playlist
	* - owner :sup:`object`
	  - The user who owns the playlist
	* - {owner}/{external-urls} :sup:`object`
	  - Known public external URLs for this user.
	* - tracks :sup:`object`
	  - The tracks of the playlist

400 - Bad or expired token. This can happen if the user revoked a token or the access token has expired. You should re-authenticate the user.

.. code-block:: console

	{
	 "error": {
	   "status": 400,
	   "message": "string"
	 }
	}

.. list-table::
	:header-rows: 0

	* - error :sup:`object Required`
	  - 
	* - {error}/status :sup:`integer Required`
	  - The HTTP status code (also returned in the response header; see Response Status Codes for more information). Range: 400 - 599
	* - {error}/message :sup:`string`
	  - A short description of the cause of the error.



