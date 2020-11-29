# Basic usage
```ruby
class User < ApplicationRecord
  has_one_attached :avatar
  # avatar is not a simple string that contains a URL to an image
  # has_one_attached makes the attribute passed to it, as an object
  # this object handles the file objects that we receive from ActionParams 
end
```
ActiveStorage objects have a very pure API. 
We can easily ask the object all the questions regarding the uploaded file.

## api
```ruby
user.avatar #=> returns ActiveStorage attachment object

user.avatar=(file_object) #=> ActionDispatch object from params
user.avatar.attach(io: file_from_internet, file_name: 'kitty') #=> can also accept a file from disk
#both above methods delete files from disk when we overrite their values

user.avatar.attached? #=> is a file present?
user.avatar.purge #=> remove the file blob from database and also from disk
user.avatar.purge_later #=> remove the file later, using ActiveJob
```

## image variants
```ruby
# For generating different type of sizes for images
# brew install imagemagick (For image conversion) (preinstalled in heroku)
# include gem
gem 'image_processing' # gem that talks to imagemagick
image_tag user.avatar.variant(resize_to_limit: [100, 100])
```

## View helpers
```ruby
url_for(user.avatar) #=> generates a url for the attachment
image_tag(user.avatar) #=> image_tag can also takes an attachment object and auto generate URL for image

# Download
link_to 'Download', rails_blob_path(user.avatar, disposition: 'attachment')
```

## Replacing image if attachment not present
```ruby
if user.avatar.attached?
  image_tag user.avatar
else
  # render a font awesome icon instead of image
  content_tag :i, nil, class: 'fas fa-user'
end
```

[Creating attachments without a model](https://medium.com/weareevermore/manual-uploads-using-activestorage-47808dab1b65)
