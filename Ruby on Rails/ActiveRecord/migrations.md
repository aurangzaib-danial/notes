# Migrations

## Quick methods
```ruby
t.references :user, null: false, foreign_key: true #=> cant omit foreign_key otherwise referential integerity is lost
# There must a good reason as to why we have to provide a foreign_key option

## Manually creating a foreign key columm (postgres)
t.bigint :user_id, null: false
add_foreign_key :posts, :users, on_update: :cascade, on_delete: :cascade 
#=> looks for user_id on posts table
#=> cascade delete, update the children foreign key columns as the parent is deleted and vice verse for cascade update
```
