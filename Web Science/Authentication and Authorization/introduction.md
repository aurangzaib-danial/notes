
# Authentication and Authorization

The most common problem that we have in web apps is **'who gets to see what?'**
We need to have a mechanism, to find out who can access our app and who can make changes to certain resources in our app.

The problem of **'who gets to see what?'** can be broken into four parts.

1. Identification
2. Authentication
3. Access policy
4. Authorization

## Identification

This is the process of identifying the user who is trying to communicate with our app. We find out who the user is, using the identify they provide for example their **email** or **phone number**.

## Authentication

After getting the identify of the user, we have to find out if the user is who they claim to be. 
This is normally achieved by asking the user for a **secret** that is known by only the user and then matching the secret with the secret that is saved with the application. This secret is created by the user when they sign up with the application.

## Access Policy

Every user in an application's domain have certain privileges. After the user is authenticated, the application also loads the access policy or the roles that are associated with the user.

Mostly, every part of an application has some sort of access policy that determines who can access them. Whenever a user access any part of an application, the application checks to see if the user's role is under the access policy of the underlying portion of application.

## Authorization

If a user's role is found to be eligible for carrying out a certain operation based on the application's access policy then the application authorizes the request of the user and fulfills the requirement of the user.



## Difference between Authentication and Authorization

The two main problems of web apps i.e.

1. Authentication (Is the user who they claim to be?)
2. Authorization (Can the User do what they are trying to do)

Understanding the difference between these two is important because often people conflate these.




