# Drying Policies

## What Pundit Makers Say
Remember that all of the policy and scope classes are just plain Ruby classes, which means you can use the same mechanisms you always use to DRY things up. 
- Encapsulate a set of permissions into a module and include them in multiple policies. 
- Use alias_method to make some permissions behave the same as others. 
- Inherit from a base set of permissions.
- Use metaprogramming if you really have to.
