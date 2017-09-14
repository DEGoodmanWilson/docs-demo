# Installation on Heroku

Protect your web applications on Heroku with Sqreen

***

# Sqreen Ruby Agent and Heroku

[Heroku](https://www.heroku.com/) is a PaaS (*Platform as a Service*) hosting web applications.

Sqreen supports Heroku for Rails applications. With Sqreen, you can easily protect your Rails apps running on Heroku.

**See our [Heroku page](https://elements.heroku.com/addons/sqreen) for more information.** 

# Installation for Heroku apps

After deploying your Ruby app on Heroku, you can install the Sqreen agent.

Just add the gem to the file Gemfile:

```gemfile
gem 'sqreen'
```

Then, install the gem **from your application root directory**:

```shell
bundle install
```

From your terminal, **in your application root directory**: commit your changes and push them to Heroku in order to trigger the deploy of your modifications:

```shell
git commit -m 'Add Sqreen to my application' Gemfile Gemfile.lock
git push heroku master
```

Then, simply add a `SQREEN_TOKEN` environment variable to your environment, with the Sqreen token provided from your user interface. 

This process is described by [Heroku here](https://devcenter.heroku.com/articles/config-vars).

!!! info "More info on Heroku"
    Sqreen Heroku Addon: https://elements.heroku.com/addons/sqreen

    Sqreen Heroku Documentation: https://devcenter.heroku.com/articles/sqreen
