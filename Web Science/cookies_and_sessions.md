# Cookies


## What are cookies?

- HTTP is a stateless protocol, does not know about previous requests.
- HTTP does not track anything.
- HTTP request completes and then is lost forever.

HTTP was made stateless by Tim Berners Lee purposely because we do not know when the user will interact with the server again so its pointless for the server to keep tabs on the user. We do not want to use up memory of server unnecessarily.

We do not have a way to remember and  track user activities on our web application.

Cookies are small pieces of data that are sent with every request to the server, so server knows who is this request coming from.

Cookies are set by the server on the user's browser.

## Session Cookies

These cookies are deleted when the user's browser is closed, that is why they are called session cookies.

Framework like Ruby on Rails store session data on the client's browser using signed cookies. This allows us to keep session related data on the user's browser and we don't have to store anything on the server.

Session is a receipt for the user who is interacting with our application.
When a user is successfully authenticated then we update this receipt to have the user ID in it. This way when the user makes a new request, we can identify them by looking for their ID in the session data.

### Signed Session Cookie

Signed cookie is a cookie that also has a signature beside its content. To verify that a session cookie is not tempered, we have to sign cookies. Cookies are signed with a secret by the web server.

It's important to know that session cookie data is encoded into BASE64. While, users cannot change the content of the cookie, they can read the contents of the cookie. This is why, we never store sensitive data about the user on the cookies.

## Persistent Cookies

These are used for storing data like users preferences e.g. theme of the website, or may be some other customize-able functionality. We do not use these cookies for authenticating the user because users can ALTER PERSISTENT COOKIES. These have a created time and may be time of expiration.

Store user related data on session cookies and store user's simple preferences on persistent cookies.
