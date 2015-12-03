# Storeez API Server
This is a Ruby evaluation test to create an RESTful API server to manage the stories of a project management system.

## Requirements
Storeez is a project management system that works like PivotalTracker.com (except it is a really scaled-down version).

This test is to create an RESTful API server that will manage all the stories of a project and most importantly, the life cycle of a story status.

You will decide the API endpoints and how the API will be used.

You must provide the following APIs:
- Create a story
- View a story
- Update a story (which includes changing the state)
- Delete a story

For easier implementation, there is no need to associate a story with a project ie. no need to track any project in this API.

A story will have the following fields:
- Title
- Points (1,2,3,4,5,6,etc)
- Description
- State

The state of a story is unstarted, started, finished, delivered, rejected or accepted.  
When a story is unstarted, it can only be changed to started.  
When a story is started, it can only be changed to finished.  
When a story is finished, it can only be changed to delivered.  
When a story is delivered, it can only be changed to rejected or accepted.  
When a story is rejected, it can only be changed to started.  
When a story is accepted, the state cannot be changed anymore.  
The API must enforce this state changes (eg. user cannot change a story from unstarted to delivered directly)

Your API should handle errors by giving friendly error messages.

## Technical Tip
ActiveRecord objects include ActiveModel Dirty which are a list of methods exposed to track changes made to your ActiveRecord objects.

```ruby
person = Person.new
person.changed? # => false

person.name = 'Bob'
person.changed?       # => true

person.name_changed?  # => true
person.name_changed?(from: "Uncle Bob", to: "Bob") # => true

person.name_was       # => "Uncle Bob"
person.name_change    # => ["Uncle Bob", "Bob"]

person.name = 'Bill'
person.name_change    # => ["Uncle Bob", "Bill"]
```

For more reading, please refer to http://api.rubyonrails.org/classes/ActiveModel/Dirty.html

## Rules
Please refer to the [rules](https://github.com/futureworkz/playbook/tree/master/protocols/ruby-evaluation-test#rules) in our playbook.

## Submission of Work
Please refer to our [submission of work](https://github.com/futureworkz/playbook/tree/master/protocols/ruby-evaluation-test#submission-of-work) in our playbook.
