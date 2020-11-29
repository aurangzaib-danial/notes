
# OAuth2

OAuth simple put is a strategy for asking another web service to authenticate users on our behalf.

OAuth2 is the successor of OAuth. It comes with new techniques and security improvements.

## Why use another web service?

Services like GitHub, Google, Twitter, Facebook etc. are very popular among users worldwide. It's safe to assume that almost 90% of Internet users are already registered with these web services. This way, the user can just authorize any of these services to send their information to our application.

## Benefits of OAuth

- Users do not have to register or provide any information to our application. They can just ask a popular web service to provide it for them. This way they do not have to type or think about what password should they use etc.
- There is a lot to web security than one can imagine. A web application own authentication system has to support tons of features and also every aspect has to be tested. It is very time consuming and error prone process. The Good news is that services like Google etc. are really good at authenticating users. Even if the user's Google password is stolen by a hacker, Google still has options like 2Factor Authentication, location based authentication etc. for protecting their users.
- It's safe to completely drop building an authentication system by ourselves and just depend on Google etc. We do not have to spend time on building features like **forgot password, account recovery** etc.

## How OAuth works?
1. A consumer application registers with a service provider like Google.
    - Consumer has to provide a URL where the service provider will redirect the users.
2. Service provider issues the consumer an application ID and a secret.
3. The consumer provides a link on their website like 'Login with Google'.
4. When the user clicks the 'Login with Google', the consumer redirects the user to Google login page.
5. The user authenticates with Google and then Google asks them to authorize the consumer so that Google can send the user's information to the consumer.
6. When user authorizes then Google redirects them to the consumer redirect URL. During redirect Google also provides a code in the request that is required by the consumer for verifying if the code came through Google.
7. Code that comes in the redirect request is sent by the consumer to Google again to verify the authenticity of that code. This time if the code is verified by Google then Google also sends back data of the user to the consumer.
8. The consumer takes the data and logs the user in.


## Things done by consumer when the user clicks on 'Log in with Google'

This is the time when the Application ID provided by Google comes in handy. This link is actually a redirect set by consumer and that redirect includes the Application ID. This Application ID informs Google of the app with which the user wants to authenticate.

## URL Redirect provided to Google by the consumer

This URL redirect is where Google will direct the user after they authorize consumer.

## Code provided by Google and the Application Secret

This code is very important because anyone can launch a request to the URL where we ask Google to send the users and a code. This is also called man in the middle attack. When Google sends this code, consumer verifies this code with Google by sending its application ID and secret to the Google. After verifying the code, Google also sends user's data back to the consumer.

This code is actually a unique token that identifies the user with Google.

