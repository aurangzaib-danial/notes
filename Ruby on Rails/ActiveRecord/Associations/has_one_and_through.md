
# has_one and has\_one through relation

## has_one (One-one)
This association means that an object can have only one object of another class and no more. The parent object has the has_one asscociation while the the children asscociation must have a belongs\_to macro.

```ruby
class Address
  belongs_to :person
end

class Person
  has_one :address
end

person.address
person.build_address
person.create_address
```

## Common Options
```ruby
class Person
  has_one :address, foreign_key: :user_id
  # class_name
  # dependent delete_all or destroy
end
```

# Gotchas
- has_one does not provide any referential integrity on the belongs\_to table. We must implement foriegn key contraint on the belongs\_to table.
- Choosing between which class should get the has_one and or the belongs\_to is not very complicated. It should just make sense in real life.

## has_one through
This kind of relationship is rare but very handy when in the need of hour.  
An object has_one of another class's object through an intermediate object.

```ruby
class User
  has_one :purse
  has_one :payment_history, through: :purse
  # source option can be used if the assc
end

class Purse
  belongs_to :user
  has_one :payment_history
end

class PaymentHistory
  belongs_to :purse
  # delegate user to purse
end

user.payment_history
```

## Common options
```ruby
class User
  has_one :my_history, through: :purse, source: :payment_history
  # source can we be used if the source cannot be inferred from the association name
end
```

**We cannot create payment history through a user object. The payment history must be created by the purse object.**
