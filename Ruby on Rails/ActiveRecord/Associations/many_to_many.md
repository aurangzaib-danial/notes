
# Many to many relations
This a complex association in which 

1. class 'A' objects can have many objects of class 'B'
2. class 'B' objects can have many objects of class 'A'

We solve this problem by introducing an intermediate table called **Join table**.

This table stores the relations between class 'A' and class 'B' objects.

**We have two methods to implement this association in Rails.**

## has\_and\_belongs\_to\_many
This is a very simple way for building a many-many association between classes.

```ruby
class Post
  has_and_belongs_to_many :tags
end

class Tag
  has_and_belongs_to_many :posts
end

post.tags
post.tags.create
```
- We still have to create a join table named posts_tags manually. The word that has the higher precedence in alphabets comes first i.e. posts > tags (p is before t in alphabets)
- This association does not provide an intermediate model for individually adding information to each post and tag relation.
- Should be used for very simple purposes, when we do not require an intermediate model.

### Common options
```ruby
  has_and_belongs_to_many :tags, join_table: :posts_and_their_tags
```

## has_many through
This is the preferred method for building many-to-many relations. This method requires an intermediate model for setting up associations.

```ruby
class Recipe
  has_many :recipe_ingredients
  has_many :ingredients, through: :recipe_ingredients
end

class Ingredients
  has_many :recipe_ingredients
  has_many :recipes, through: :recipe_ingredients
end

class RecipeIngredient
  belongs_to :recipe
  belongs_to :ingredient
end
```
Through this approach, we can track extra information on each recipe and ingredient relation. For example we can track the quantity of an ingredient for a recipe.

### Common options
```ruby
class Recipe
  has_many :recipe_ingredients
  has_many :awesome_ingredients, through: :recipe_ingredients, source: 'ingredient'
  # source can we used if the source cannot be inferred from the association name
end
```
