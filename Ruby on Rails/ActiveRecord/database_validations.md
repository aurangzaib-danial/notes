
# Database Validations
Adding model validations is not enough in a robust application which is going to have multiple server instances.

## Problem (Unique Email)
Let's say we have a model validation for the email field and we two instances of our server running.

1. Mark registers an email. 
2. The first instance starts processing the request.
3. Joe tries to register the same email as well.
4. The second instances starts processing the request.
5. All of this is happening at the same time.
6. Both instances end up creating same email twice because each instance checked for the email in the database at the same time and did not find one.

Above problem shows us that model validations are not the only solution. We need our database adapter to implement validations as well.

## Adding database validations in migration
```ruby
create_table :users do |t|
  t.string :email, null: false
end

add_index :users, :email, unique: true
```

## Rule of thumbs
- Always setup validations like unique on the both ends i.e. model and database.
- Most common unique constraint for fields like email and has_one association.

[Best post on dealing with this problem](https://thoughtbot.com/blog/the-perils-of-uniqueness-validations)
