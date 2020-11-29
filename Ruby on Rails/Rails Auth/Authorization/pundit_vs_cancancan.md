
# Pundit vs CanCanCan
## CanCanCan
### Pros
- Very easy to setup.
- You can have an authorization system right away for a simple app in seconds.
- Good for learning about authorization before moving onto Pundit.

### Cons
- One ability class for every model. We can create ability class for each model like Pundit but it's not worth it.
- Very magical and difficult to understand as to which resource is actually being authorized.
- Not very organized.
- Good for simple apps but can make authorization very difficult for complex apps.
- Cant really test pages that are not attached to an object like admin dashboard, stats etc.

## Pundit
I have personally switched to Pundit from CanCanCan because of its simple architecture. I'm going to use Pundit for all of my projects now for consistency sake because I'm a person who loves organization and Pundit offers a great level of organization in terms of organizing my authorization code.

### Pros
- Modular and organized, every model has its own policy class.
- Less magical and easy to understand whats going on.
- Plain old Ruby for everything
- Headless policies feel like icing on a cake.
- Very easy to test and also provides its own RSpec DSL.

### Cons
No cons because I'm biased in the favour of Pundit.
