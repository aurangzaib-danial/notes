# Nested Resources

- Nested resources are required to reveal more information about a particular resource. It also allows us to filter data according to the parent resource.
- Before nested resources, we used query parameters for getting the information about the parent resource, so we can filter resources according to the parent resource.
- RESTFUL architecture changed that and now we have simple URLs that clearly reveal information about the parent and nested resources.

## Example

```ruby
  /authors/1 #=> show me the first author

  /authors/1/posts #=> show me the posts for author number 1
```

## Generating resources for posts

```ruby
  resources :posts
```
- Generates resources for posts
- Generates 7 RESTFUL actions.

## Generating nested resources

```ruby
  resources :authors do
    resources :posts, only: [:index, :show]
  end

  #=> /authors/:author_id/posts #=> author_posts_path(1)
  #=> /authors/:author_id/posts/:id #=> author_post_path(:author_id, :id)


  resources :posts #=> also generate singular resources like /posts, /posts/1 etc.
```

- Generates resources nested under the parent resource.
- Rails will generate 7 RESTFUL resources by default for posts nested under authors.
- The nested routes will be prefixed by Rails accordingly.

### We can nest more than one level but that is generally a bad idea.

**For example**

```ruby
  resources :authors do
    resources :posts do
        resources :comments
    end
  end
```

- This creates immensely complex routes difficult to main.
- Also, we have to keep Separation of Concerns in mind.
  Comments of a post are not the concerns of an author. So, we do not need to reference the author.

## Shallow routes (Shallow => Little Depth)

Just creates minimal amount of nested routes. The routes only identify the parent resource uniquely and only generate collection routes for the nested resources.

```ruby
  resources :authors do
    resources :posts, shallow: true #=> index, create, new
  end

  #=> GET /authors/:author_id/posts
  #=> POST /authors/:author_id/posts
  #=> GET /authors/:author_id/posts/new
```

## Handling nested resources and Separation of Concerns

We never create more controllers or actions to handle nested resources. We make our actions that work for singular resources, also handle nested resources.

### Taking the example of authors and their nested posts

We generate nested resources for posts under author.

### We visit /authors/1/posts

- This route means that we want to show all the posts of an author.
- Clearly, we just want to index all the posts but scope them by an author. 
- We can easily do this by upgrading the PostsController index action to check if the route also contains an **_author_id_** and if does load posts for that author then rest will remain the same as it was before for all posts.

### Separation of Concerns
- It is not the job of the AuthorsController to render anything related to posts.
- It is the responsibility of PostsController to render posts either by an author or just posts in general.

## Protecting Routes
- We have to guard our routes for potential bugs. Also, if a specific resource does not exist in the database then we should redirect the user and show some sort of error.
- We should also check if the nested resource that we rendering, actually belongs to the parent resource?
- While creating or editing a nested resource, we need to properly setup the nested resource with the correct parent resource.
- There are soo many caveats but we should approach each problem with modesty and one by one.
- Instead of thinking different conditions that could break our routes, we should channel that thinking into writing tests.
