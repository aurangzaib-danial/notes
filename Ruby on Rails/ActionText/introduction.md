# ActionText
- It is a Rails framework for easily allowing users to create RichText from browsers.
- It uses the Trix web editor for creating rich text areas. We can also drop images in trix editor and create galleries.
- When data is passed from trix rich text area over to model and assigned to ActionText field, then ActionText painlessly stores all of the data in a separate ActionText::RichText table and also handles stores all attachments using ActiveStorage 

> It's important to note that developers for ActionText found that instead of storing large 'Text' fields on the main model, we should move these fields to another table and retrieve them when necessary.

**ActionText::RichText is a polymorphic table and sets up a has\_many\_attached macro for images**

## Setup
**We have to enable ActiveStorage for ActionText, i.e. enable 'image_processing' gem for image previews in rich\_text\_area**

```bash
$ rails action_text:install
```
Above command does the following
1. Generates active_storage migrations if they are not already migrated
2. actiontext migration for ActionText::RichText for storing all the rich texts.
3. actiontext styles for editing Trix editor.
4. adds Trix node module

## Usage
```ruby
class Post < ApplicationRecord
  # we can have as many rich text fields as we want
  has_rich_text :content
  # has_one :content, -> { where name: 'content'}, class_name: 'ActionText:RichText', as: 'record'
  has_rich_text :body
end
# Thats about it

# Methods
post = Post.new
post.content = 'This is some content'
post.content #=> ActionText::RichText
puts post.content #=> prints the content instead of returning the object
post.to_plain_text #=> only the text is returned, HTML is removed`

Post.with_rich_text_content # Preload the body without attachments.
Post.all.with_rich_text_content_and_embeds # Preload both body and attachments.

Post.all.with_rich_text_body
```
## Best use cases for action_text
1. Mini messages to others
2. Content for ads
