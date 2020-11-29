# Fragment Caching
This is most useful when we want to cache specific chunks of HTML data. For example, when we render multiple partials, we are actually compiling every partial one by one. This compilation is heavy on server.

Fragment caching allows us to cache data so do not have to compile it over and over again. This is mostly useful when we render a collection of partials.

**Note: In this method, we do not cache actually ActiveRecord objects but the partial that is created from the object is cached**

# Russion doll caching
This is a technique used on top of fragment caching for caching data that is nested inside a fragement caching block.
