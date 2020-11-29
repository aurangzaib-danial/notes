
## has_secure_password.md

For encrypting passwords of our users, ActiveRecord works in conjunction with Bcrypt.

```ruby
  class User < ApplicationRecord
    has_secure_password
    # requires a column of password_digest
    # requires bcrypt gem
  end
```

## has_secure_password is a class macro that

- adds methods for handling passwords for a model.
- adds virtual attributes of password, password_confirmation
- when an object that a has password is saved to the database, its password is encrypted using **Bcrypt** and then the encrypted password is saved in the password_digest column. 
- as password is a virtual attribute, when the reference to the object is lost then there is no way of knowing the password of the object. Only, the actual password can decrypt the password_digest saved in the database.

## Validations added by has_secure_password

- object must have a password
- if password\_confirmation is not nil then password_confirmation must match the password attribute.

## Authenticate a password against password_digest

```ruby
  user = User.first

  user.authenticate(params[:password])
  # if the password matches then user instance is returned that is a truthy value.
  # if the password is wrong then false is returned
```

## How password encryption works?

- ActiveRecord under the hood uses Bcrypt for encrypting passwords.
- Bcrypt converts the password into a hash built with numbers and letters. Also, adds random salt or string to the hash.
- ActiveRecord saves the password encrpyed by bcrypt into the password_digest column.

## How decryption works?

We pass the password that we want to run against the password_digest to the authenticate method and then the authenticate method delegates the decryption to bcrypt gem. 








