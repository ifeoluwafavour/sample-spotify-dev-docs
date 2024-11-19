Rate limits
###########

If your app makes a lot of Web API requests in a short period of time then it may receive a 429 error response from Spotify. This indicates that your app has reached our Web API rate limit. The Web API has rate limits in order to keep our API reliable and to help third-party developers use the API in a responsible way.

Spotify's rate limit
====================

Spotify's API rate limit is calculated based on the number of calls that your app makes to Spotify in a rolling 30 second window. If your app exceeds the rate limit for your app then you'll begin to see 429 error responses from Spotify's Web API, and you may hear from users about unexpected behavior that they have noticed while using your app. The limit varies depending on whether your app is in development mode or extended quota mode.

Exceptions
========== 
Be aware that Spotify does sometimes implement other limits outside of the API-wide rate limit. A few API endpoints, like the playlist image upload endpoint, have a custom rate limit that may differ from your app-wide rate limit. See the body of your API response from Spotify for more information about the error that you have received.

