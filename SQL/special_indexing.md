# Special Indexing
There are many ways to index a field that is used for full-text searchs.

Fuzzy finding on a field in postgress, disables indexing.
We have to enable pg_trigram extension to create a special trigram indexing on the field.

There are many to make our search queries faster and I have just scratched the sufrace.

[Syntax](https://scoutapm.com/blog/how-to-make-text-searches-in-postgresql-faster-with-trigram-similarity)
