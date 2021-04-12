# Pagination
Pagination is all about dividing database records into pages so we do not need to display all the records on one single page.

## How does it work? (Theoretically)
Pagination is really simple and beneath it, it's just simple numerical formulas.

1. First of all, we decide how many records we need on a single page. In this case, 10 records.
2. We keep track of page numbers using query parameters.
3. We use **offset** function of SQL for starting from a specific number of record and use the **limit** function to limit the number of records returned by SQL.
4. For calculating the **offset** we multiple the number of current page with the number of records that we want on a page.

```ruby
MAX_NUMBER_OF_RECORDS = 10
page_number = 3
the_offset = 3 * 10 #=> 30
```
5. Now we can create next and previous buttons and link them to the page numbers by introspecting on the **params[:page]**. For next button we plus one in the 'page' variable and for previous button we minus one.

**Above is the most basic form of pagination, it does not handle disabling of next and previous buttons and also does not display number of pages**

## API in Ruby
```ruby
# Normally, we create scope method called paginate and pass it the page number
# This scope will fetch records according to the page number
Post.all.paginate(params[:page])
```

## Page numbers and disabling next and previous buttons
1. First, we caculate the total number of pages based on all the records in database.
  1. To do that we have to divide the count of records with MAX_NUMBER_OF_RECORDS.
  2. Convert the result into float.
  3. Round of the decimal number to the highest number using ceil function.

```ruby
# Inside post class
def total_pages
  (count/MAX_NUMBER_OF_RECORDS.to_f).ceil
end
```
2. Now that we have the total_pages, we can compare current page number with total_pages and disable next and previous buttons accordingly.

