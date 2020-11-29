# Operating files
- When to close a program, we lose all the data and objects.
- We store important data as text and later when we open reopen the program, we can covert the text into objects. 
- We use YAML to store data in hierarchy.

```ruby
require 'yaml'
students = [
  ['Ali', 'Sunny', 'Biden'],
  ['George', 'Trump', 'Junaid']
]

filename = 'dummy_students.yml'
File.open filename, 'w' do |f|
  # 'w' is for write permission, we have to open the file to write it
  f.write students.to_yaml # convert the array into YAML formatted string
end # the end also closes the file for us

students_from_file = YAML::load(File.read filename) # covert the string into ruby object
puts students_from_file # array of students, same as line 6
```
