# Single Table Inheritance (STI)
STI is a feature of ActiveRecord through which related models can store data in a single table.
## Pros
- Only one table for many related models.
- Add functionality unique to models and controllers.
- We do not have to create multiple tables.

## Cons
- We cannot add specific data-fields to models.

## How it works?
Related models inherit from a parent model. The SQL table of parent model has a 'type' field that identifies the model of the rows.

## Usage (Vehicle Example)
### Generate a parent model
```console
rails g model Vehicle name color price:integer
```

### Generate models that inherit from parent model
```console
rails g model Car --parent=Vehicle
rails g model Bike --parent=Vehicle
```

That's about it, now Car and Bike inherit everything from Vehicle and whenever an object is created either it's a car or a bike, it's saved in 'vehicles' table.

```ruby
car = Car.create(name: 'Toyota', color: 'blue', price: 10) # Insert into vehciles where type='Car'...
bike = Bike.create(name: '125', color: 'red', price: 5) # Insert into vehciles where type='Bike'...
```

## When to use STI?
When we have lots of same columns between certain models.

## When not to use?
If the models require lots of different data-attributes then we should make their own database-tables because if we add columns on STI table that are specific to a model then it can confuse us later. It's okay to have 1-2 data-attributes that are specific to a model and might not be used by other models. 
