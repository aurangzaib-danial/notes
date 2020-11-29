# Queries problem

```ruby
has_one_attached :avatar #=> class_name: ActiveStorage::Attachment
has_rich_text :content #=> class_name: ActionText::RichText
```
Above methods create accessors that return objects of another model.
It's important to note that above are not stored on the model table itself.

> We cannot add validations for these fields on the model because the validations we would load these objects from their tables. Thus, validations would run even for these fields even when we do not make changes to objects that would result in queries that we do not even require.

The best way would be to add validations on these objects classes.

```ruby
# something like this
ActionText::RichText.validate_presence_of :body
```


**On a side note, I think its ok to let these useless queries run, these do not have an performance impact**
