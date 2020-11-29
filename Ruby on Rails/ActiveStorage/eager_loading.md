# Eager loading attachments
The has_one_attached macro underneath sets up a one to one association with ActiveStorage::Attachment and a through relation with ActiveStorage::Blob

```ruby
# has_one_attached adds following macros
class User
  # has_one_attached :avatar 
  has_one :avatar_attachment, class: 'ActiveStorage:Attachment', as: :record, inverse_of: :record
  has_one :avatar_blob, through: :avatar_attachment
end

# We cannot do the following for eager loading the attachments of objects
User.includes(:avatar) #=> avatar is not an association (wrong)

# However, if we keep the one-to-one relation in mind we can do the following
User.includes(avatar_attachment: :blob)
```

[Best blog on this](https://jasoncharnes.com/eager-loading-querying-against-activestorage-attachments/)
