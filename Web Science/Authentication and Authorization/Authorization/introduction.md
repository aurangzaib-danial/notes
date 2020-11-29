
## Introduction

Authorization is answering the following question 

> Can the user do what they are trying to do?

To answer this question, we have to define some rules or permissions for our resources. The complex logic of checking the permissions of a resource is alway delegated to model objects because we tend to think of our models as brains of our application. An object should know about its permissions.

## Request/Response Cycle of Authorization
1. User signs in and accesses a resource.
2. Controller finds that resource.
3. Controller asks the resource object i.e. are you accessible by this user?
4. If the objects responds with affirmative then the controller renders the view otherwise it raises an access denied error to the current user.

## Separation of Concerns
Controllers handle the logical flow of our application. We should not teach our controllers the complex logic of verifying the relation of a resource with an user. An object should itself know if its accessible by an user or not.

It is perfectly fine to implement authorization checks in a controller for a simple application but as our app grows our controllers become littered with authorization checks and at that point we should use permission models instead of teaching our controllers about authorization.

## Permissions
We use numbers for permissions in our database because its easier to operate on numbers in terms of Math operations. Each number represents a specific type of permission.

However, in models, instead of just using magic numbers, we should make a dictionary that defines these numbers. We do not care about the numbers stored in the database.

## Building custom Authorization system VS an authorization library
I have built my own authorization system but the problem with my system is that I have taught my models about their permissions. It's much more better to encapsulate all of my permissions in a separate permissions model that is only concerned with the permissions of my resources.

Encapsulating permissions inside a permission model is just what an Authorization library implements. All the logic of checking the permission of a resource based on a user is implemented inside a permission model rather than my own models.

