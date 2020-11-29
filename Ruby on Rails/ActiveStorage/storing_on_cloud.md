

# Storing on cloud
- Cloud is only place where to store files, images created on our application.
- This is the right to do and everyone use clouds instead of regular web server.
- We store data on cloud because providers like Amazon are cheap.
- Also, the file download quality is better than our webserver.

ActiveStorage provides complete solution for saving and retrieving files from cloud storages. All we have to do is configure what kind of storage service we want to use i.e. amazon, google, azure etc. We have to provide relevant API keys for the cloud provider. That's about it, now we can stop worrying about how to save or retrieve stuff from cloud, that's all on ActiveStorage. We can keep on attaching files to our objects with the ususal API provided by ActiveStorage like has_one_attached and object.attach etc. 

```ruby
# we have to configure environment to use cloud
# production.rb
config.active_storage.service = :amazon
# development.rb 
config.active_storage.service = :local #=> local web server, not useful for heroku
# test.rb
config.active_storage.service = :test #=> temp/storage on server

# also configure storage.yml for clouds with API keys and secrets
amazon:
  aws_key_id: 12345
  aws_secret_key: 

```


[Setting up Amazaon cloud with Active Storage](https://medium.com/alturasoluciones/setting-up-rails-5-active-storage-with-amazon-s3-3d158cf021ff)
