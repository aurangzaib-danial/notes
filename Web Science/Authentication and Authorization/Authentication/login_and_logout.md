
# Login and Logout

## Logging in or Authenticating the user

We authenticate the credentials that a user sends and if authenticated then that user's **id** is set in the session data of the user.

- Login simply means saving the 'user id' in the session data of the user.
- As session's are also cookies, whenever the they make a new request, their cookies are also sent to the browser.
- If the session includes a user id then we do not have to have to ask the user for authentication again.
- Adding a user id to session means that we trust that the user is who they claim to be and now they do not have to authenticate again in the current session. 

USER ID inside a user's session is a token for their identify.

For example

Going to a private members club, the guard will check my ID and put a wrist band on my hand. Next time, whenever I leave and then comeback, I can just show my wrist band.

Ordering at the club, I can just show my wrist band to the waiter and he will identify me.

Just like above, when a user is successfully authenticated by a server then the server issues a token for the user that is stored inside the session data and when the user makes a new request, that token is automatically submitted by the User Agent using session cookie.


## Logging out

Logout means to clear the user id from the session data. If we remove the token(sign) from the session then the user has to provide their credentials again.

Logging out is important because the user might be using a public computer or they want to let someone else use their computer etc.
