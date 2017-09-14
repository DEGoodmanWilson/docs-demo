# Ruby agent compatibility

***

The Ruby agent is compatible with the the most popular web frameworks, operating systems and web servers. Below you can find more details about specific version compatibility.

# Operating systems

The Sqreen Ruby agent is supported on all operating systems, including Linux, Mac OS X, and Windows.

# Ruby versions

The ruby agent is fully compatible and tested against all rubies **starting from Ruby 1.9.3 up to 2.4.x**.

# Rails and Sinatra

The Ruby agent is fully compatible with all version of **Ruby on Rails between 3 and 5 included**. Sqreen provides the most complete protection to all your Rails applications. 

The Sqreen Ruby agent is fully compatible with **Sinatra 1.4.x**.

# Servers compatibility

Sqreen is tested against the following servers:
 - [Puma](http://puma.io/)
 - [Passenger](https://www.phusionpassenger.com)
 - [Thin](http://code.macournoyer.com/thin/)
 - [Unicorn](https://bogomips.org/unicorn/)
 - [WEBrick](http://ruby-doc.org/stdlib-2.0.0/libdoc/webrick/rdoc/WEBrick.html)

Puma may display the following message during your application startup: 
```
"Detected 1 Thread(s) started in app boot".
```

# Automatic User Context in Ruby

Sqreen automatically detects and protects user accounts when your application is based on Devise framework, with `DatabaseAuthenticatable` strategy. More information in section [Ruby SDK for user monitoring](doc:ruby-agent-users-monitoring).

# Database compatibility (NoSQL/SQL injection protection)

Sqreen protects against SQL and NoSQL injections for the most common production databases:
- MySQL
- PostgreSQL
- SQLite

!!! info "Other database?"
    Please, [contact us](mailto:support@sqreen.io) if you are using a different database. We will adjust our roadmap!

# Templating engine compatibility (cross-site scripting protection)

The protection against cross-site scripting attacks (XSS) is available for the ERB, Haml and Slim templating engine.


!!! info "Other templating engine?"
    Please, [contact us](mailto:support@sqreen.io) if you are using a different templating engine. We will adjust our roadmap!