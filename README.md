# Sinatra Skeleton

## Purpose

1.  Move students from building static websites to building applications
using Model-View-Controller (MVC) design patterns
2.  Eases transition to the Ruby on Rails framework
3.  Introduction to Object Relational Mapping, demonstrating the relationship
between models to database tables.
4.  Starts building the practice of Test Driven Development (TDD) using Rspec

## Quickstart

Requires: Ruby 1.9.x and above, Postgres

1.  Install packages and dependencies `$ bundle install`
2.  Create a database `$ rake db:create`
    - Run `$ rake -T` to see available other available`rake` tasks for creating
    models and database tables
3.  Explore the database with the Sinatra console `$ tux`

    Similar to Rails Console, Tux is an interface for querying the database
using Ruby instead of SQL. For example:

     - PostgreSQL command for finding all Users with last name beginning with "C"

     ```SQL
     $ psql -d sinatra-skeleton_development
     psql (9.4.0)
     Type "help" for help

     >> SELECT * FROM users
     >>   WHERE last_name
     >>   LIKE 'C%';
     ```

     - Tux command for finding all Users with last name beginning with "C"

     ```
     $ tux
     Loading development environment...
     >> User.where("last_name like 'C%'")
     ```
    (Note: Do not structure queries like this in your app! They'll be vulnerable to <a href="http://guides.rubyonrails.org/security.html#sql-injection">SQL injection attacks</a>.)

### To view your local application in the browser

1.  Launch the application server `$ bundle exec shotgun config.ru`
2.  Open a new browser window and point the address to http://localhost:9393

## Troubleshooting

### PostgreSQL error

`=> ActiveRecord::NoDatabaseError: FATAL:  role "postgres" does not exist`

Run `$ createuser -s -r postgres`

### Shotgun error

```bash
=> == Shotgun/Thin on http://127.0.0.1:9393/
Thin web server (v1.6.2 codename Doc Brown)
Maximum connections set to 1024
Listening on 127.0.0.1:9393, CTRL+C to stop
/Users/Host/.rvm/gems/ruby-1.9.3-p545/gems/eventmachine-1.0.3/lib/eventmachine.rb:526:in `start_tcp_server': no acceptor (port is in use or requires root privileges) (RuntimeError)
```

You may have an instance of the server running in the background.

To terminate it, run `$ kill -9 $(ps aux | awk '/[s]hotgun/ {print $2}')`

## Contributing

You can help make this skeleton more awesome! There are three ways to contribute:

1. Ask for a bug fix or enhancement
2. Submit a pull request for a bug fix or enhancement
3. Code review an open pull request

When you give and receive feedback, remember to A.S.K. (Make it Actionable, Specific, and Kind)
