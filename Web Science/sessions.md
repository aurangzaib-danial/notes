
# Sessions

Sessions are temporary period of users interaction with the server.
There are many different ways through which a server can implement sessions.

# Storage

Sessions store data that can be reused in subsequent requests.

There are 3 main ways servers can implement sessions and save sessions data.

1. Cookie Store
2. Cache
3. Database

## Cookie Store

This is by default used by Rails. It stores data on the User Agent as a session cookie and signs it with a secret.

### Advantages

- Fast
- Server does not have to remember anything related to the session.

### Problem

These sessions can reused by a hacker if the hacker copies the session data. Changing the user's password does not clear the session data. Also, session data is stored in a cookie which can only be max 4kb in size.

We need to use Devise for generating a salt for a session so when the user changes password then the salt also changes. Session hijacked by a hacker will become invalid. But all other sessions of the user will also become invalid. Devise salt is based on the password in database. On every request, devise will hit the database. This destroys the purpose of cookie store.

If a hacker copies any of the session data, they can replay it. Logging out does not make old session's invalid.

### When to use?

Smallar and simple applications, when replayable is not a very big concern.

### When not to use?

For a application like a bank app, where security is of real concern.

## Cache

These are saved in the memory of the server.


## Database

These are saved in the database.

# Session Token

A session token is sent to the user when they successfully authenticate with the server. This token is stored inside a session cookie. After authenticating, when the user makes a new request to the server, the server does not ask for authentication again if the User Agent also sends the token.

So the token is used instead of using credentials again. Saving credentials inside a cookie is very insecure.

Token is generated using a secret that is only known to the server. If a token is tempered then the server rejects it and issues a new one.

Benefits of a token
- We can change the token secret in the server, that makes all sessions invalid, in case of hacked sessions.
- Tokens that are generated using a secret and also a salt, allows a user to logout from all computers when they change their password.
