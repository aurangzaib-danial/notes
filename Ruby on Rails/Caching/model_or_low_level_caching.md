

# Model or low level caching
This is my favorite type of caching. This caching allow us to be in total control of what we want to cache. This method allows us to cache frequent database queries or data fetched from an API.

```ruby
# method provided by Rails for storing cache data
Rails.cache.fetch('name_for_stored_data') { object_to_be_cached }
```
- This is a read/write method
- If an object is present on the storage name then that will be returned.
- If data is not present then the content passed inside the provided will be stored on the storage.

```ruby
#usage in a class
class Category < ApplicationRecord
  after_commit :flush_cache # delete cache when create, update, destroy

  def self.all_cached
    Rails.cache.fetch(:categories) { Category.all }
    # if data is present on the 'categories' key then return that otherwise store the data that is in the block {}
  end

  private
  def flush_cache
    Rails.cache.delete(:categories)
    # delete the categories storage from cache
  end
end
```
