
# Indexing and Unqiue Constraint

## Indexing
SQL indices speeds up our queries million times faster than average queries.

### Analogy
When want to read a specific concept in a book, we find that concept pages quickly using the index of the book. This is just how SQL indices work.

### How indexing works?
SQL indices contains references for specific columns of a table.

Normally, if we want to to find rows based a specific column using ‘where’ clause, the SQL adapter has to perform a full table search i.e. check all the rows in a table. If our table is extremely large then the computer will take immense amount of time for answering our query.

We can ask SQL to create indices for specific columns so that whenever those columns are used in ‘where’ clauses then SQL knows where to look for the rows quickly without performing a full table search.

### How independent indices are created?
```sql
CREATE INDEX "index_posts_on_author_id" ON posts (author_id);
```
Now whenever a post is inserted then an index entry for the author_id will be created by the SQL. This index entry is actually a pointer for the memory space where the newly generated row lives.

This way whenever we want to find posts of an author, we will be able to find them quickly without performing full table search.

**NOTE: Indices do not work well with NULL values. Do not allow nulls for columns that you set up for indexing.**

### When to index?
* Always use on foreign key columns.
* Use on columns that are mostly used for finding data.
* It is okay to independently index foreign keys of a join table when you think you do not need a composite index or both keys hold equal importance.

### When not to index?
Do not use on columns that will never be used for "where" clauses.

### Side effects
- Indexing is hard on database. 
- It makes the INSERT and UPDATE statements slow.
- It takes additional space in our database.

### How composite indexing works?
This is another form of indexing in which we index multiple columns together. This can work even faster then independent indexing if done the right way.
### Example
Two fields post\_id and tag\_id in a post_tags join table. When we create a composite index for these two the order matters.

```sql
CREATE INDEX "index_post_tags_on_post_id_and_tag_id" ON post_tag (post_id, tag_id);
# post_id is the first field if tag_id was passed as first argument then it would have been first field. Rememeber order matters.
# first field can work as an independent index as well but the second field cannot
```

#### When to use composite indexing?
- Its mostly useful for join tables.
- When you are going to find data based on two columns that are related.
- When we want to make a column unique based on a scope of another column.

#### Composite indexing in a join table
It can difficult to find out the first field for the join table. We should choose that column as the first field which would be mostly used for directing finding i.e a where clause.

The second field can benefit from the join query.

## Adding a unique index
Its very common to index columns that are going to have unique values in them. To add a unique constraint to a column we have index it uniquely.

```sql
CREATE UNIQUE INDEX "index_users_on_email" ON users (email);
# This adds a database check so only a unique email can exist in the users table
```

