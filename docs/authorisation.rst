Authorisation 
#############

The Spotify API uses the Oauth2.0 authorisation framework. You will need to obtain an access token to interact with Spotify’s data. 

Create an account
=================

Log into `Spotify Developer Dashboard <https://developer.spotify.com/dashboard>`_ to create a developer account if you haven't already. You will need to read the latest `Developer Terms of Service <https://developer.spotify.com/terms>` to complete your account set up.

Create an app
=============

On your dashboard, click *Create App* and a form will appear. Fill out the form with the appropriate information:
* App name: your app name
* App description: a brief description of your app 
* Website (optional): the link to your app’s website
* Redirect URI: the link to the website Spotify will redirect users to upon authentication success or failure

Check the Development Terms of Service checkbox and click *Save* to create your app

.. note::
	An app provides you with the Client ID and Client Secret needed to request an access token.

Request access token
====================

* On your dashboard, click the name of the app you just created
* At the far right, click *Settings*
* Copy your *Client ID*
* Click on View client secret to view and copy your Client Secret as well

Now that you have your Client ID and Client Secret, you are ready to request your access token. The following code uses cURL to make a POST request to the token endpoint URI.

.. code-block::

	curl -X POST "https://accounts.spotify.com/api/token" \
    	 -H "Content-Type: application/x-www-form-urlencoded" \
    	 -d "grant_type=client_credentials&client_id=your-client-id&client_secret=your-client-secret"

.. note::
	Edit out the backslash (\) if you use Windows command prompt.

The response will include an access token valid for 1 hour. 

.. code-block::

	{
	  "access_token": "BQDBKJ5eo5jxbtpWjVOj7ryS84khybFpP_lTqzV7uV-T_m0cTfwvdn5BnBSKPxKgEb11",
	  "token_type": "Bearer",
	  "expires_in": 3600
	}

Follow the instructions in the :doc:`sample_api_call` section to make your first API call. 

