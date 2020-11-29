






# Intro
Caching is all about storing something in memory after its evaluation so we do not have to evaluate it over and over again.

## Caching with Rails
Rails provides out of the box solutions for caching certain aspects for our application. It is robost and makes our applications super fast.

**Caching is enabled by default in _production_ mode. We have to enable it for _development_ for testing purposes. It is disabled in development because this way we always get fresh data for testing.**

```shell
# enable cache for development
# use same command for turning off
rails dev:cache
```

**All cache is cleared when the server restarts**

### Rails methods for caching
1. Page caching (full page)
2. Action caching (full page but allow controller filters)
3. Fragment caching (cache fragments of data)
  - Russion doll caching (nested fragments of data)
4. Model caching or low level caching (best for SQL or API queries)
5. HTTP caching (full page cache for dynamic screens like a Post show page)

[Best blog on caching](https://www.sitepoint.com/speed-things-up-by-learning-about-caching-in-rails/)

