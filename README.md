# Sinatra Skeleton

### Purpose

1. Demonstrates a reasonable set of practices around building Sinatra applications
2. Sandbox for building practice in MVC and RESTful routes
3. Eases the transition from building websites to building with Rails
4. Gives a barebones RSpec skeleton to start building the practice of TDD

### Quickstart

1.  `$ bundle install`
2.  `$ bundle exec shotgun config.ru`

### Troubleshooting
Postgres Error

`ActiveRecord::NoDatabaseError: FATAL:  role "postgres" does not exist`

Resolve by running

`$ createuser -s -r postgres`

### Contributing

We would love for you to help make the skeleton more awesome, There are three ways to contribute:

1. Ask for a bug fix or enhancement
2. Submit a pull request for a bug fix or enhancement
3. Code review an open pull request

Be prepared to give and receive specific, actionable, and kind feedback!