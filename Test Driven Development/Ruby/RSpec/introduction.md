
# Introduction
RSpec is a full-fledge solution for testing applications built in Ruby. Either its a command line app or a web app, RSpec can work for all types of applications.

## Features
- Tests written using RSpec are very expressive and easy to understand.
- RSpec makes testing fun.
- Modular by nature.
- Easily customizable and extendable.

## Setting up RSpec in a project
1. Create a spec folder on the root level of project.
2. By convention, we create a `spec_helper.rb` file in this directory, where we can customize our experience with rspec.
3. Create spec files and write your test code in them. All the tests in files of spec folder, suffixed with _spec.rb will be run. It's best to modularize spec files by creating entity specific folders.

## What is a spec file?
Spec is short for specification. A spec file contains tests for a specific entity. For example, a spec for a **Person** Class is named as `person_spec.rb` and **\_spec** denotates that this file contains test specifications for the **Person** Class.

## Typical RSpec File
```ruby
# person_spec.rb
describe Person do
  it 'has a name' do
    subject.name = 'Sunny'
    expect(subject.name).to eq('Sunny')
  end
end
```
## Anatomy of a RSpec test suite
```ruby
describe Person do
  # This is called a test suite or a group.
  # We define all of our tests for a specific Class or Entity inside its describe block
  # describe accepts a String or the Class itself for setting the group name

  it 'has a name' do
    # Here we write the code that we want to test
    # Its best to test only one aspect of a test group subject inside an 'it' block.
    subject.name = 'Sunny'
    expect(subject.name).to eq('Sunny')
    # Expect method is what actually tests our code result against our desired result.
    # If an expectation fails inside a 'it' block then the test is marked failed and reported in the test log.
    # We can write multiple expectations inside an 'it' block but only one is the convention and it makes sense.
  end
end
```
