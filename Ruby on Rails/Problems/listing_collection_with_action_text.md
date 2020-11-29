# Listing collection with action test
When a collection is rendered and we can use the with_rich_text_**attribute** method for loading all the rich_text fields for avoiding N+1 queries.

However if we want to load just an excerpt of a rich\_text field, using something like topic.description.to_plain_text will still load the ActiveStorage::Blobs if the field contains any images. This can result in poor performance as blobs will be loaded for all topics even when we do not need them.

My solution for this is, when a topic is created or updated, we should store an excerpt of rich_text content on the model. So this way, we do not have to load the blobs of rich_text content.
