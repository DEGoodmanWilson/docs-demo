# Installing the Ruby agent

***

# TL;DR

Installing the Sqreen Ruby agent enables you to monitor the security of your application and block attacks in real-time. Installing Sqreen in your Rails application takes less than a minute:

- [Sign up to Sqreen](https://my.sqreen.io/signup) to create your account
- Pick up your first application name and language. The name of the application can be the name of the repository, or anything that will help you identify the app in your Sqreen dashboard
- Follow the procedure detailed below

# Standard Rails Application

The installation of the Ruby agent only requires 3 lines of code.

First, **in your application root directory**, add Sqreen gem in your `Gemfile`:

```gemfile
# Install Sqreen gem in your Gemfile
gem 'sqreen'
```

Then, in a terminal, type the following commands **from your application root directory** (the Sqreen token will be provided on [Sqreen user interface](https://my.sqreen.io/signup)):

```shell
# Install the Sqreen gem from your application directory
bundle install 

# Set the Sqreen token provided from your dashboard from your application directory
echo "token: mysecrettoken" > config/sqreen.yml 
```

# Install the agent outside production environment

Typically you will install the Sqreen Ruby agent in your production environment, but you can create several applications using your Sqreen dashboard, and specifying the environment (development, staging, production). A unique Sqreen token will be provided for each of your applications.

# Basic configuration

After installing the agent, your configuration will be stored in the configuration file `sqreen.yml`. It basically contains your Sqreen token.

Instead of using the Sqreen configuration file `sqreen.yml`, you can also use `SQREEN_TOKEN` environment variable to set up your token:

```shell
export SQREEN_TOKEN=mysecrettoken
```

Sqreen Ruby agent provides flexible configuration settings. Refer to [Configuration of the Ruby agent](doc:configuration) for more detailed information.

# Uninstall the agent

To uninstall the Sqreen agent, simply remove the gem `sqreen` from your Gemfile.

# Notes

The Sqreen Ruby agent's gem is available on [rubygems repository](https://rubygems.org/gems/sqreen).

!!! note "Use different Sqreen Applications for different environments"
    We recommend you to use different Sqreen applications on your different environments: Production, Staging and Development.

# Bundler app (Sinatra)

For bundler app (Sinatra), proceed to the standard [installation of the Ruby agent](doc:installation) and just require the Sqreen gem from your application code after Sinatra.

In your application root directory, add Sqreen gem into your `Gemfile`:

```gemfile
require 'sinatra'
require 'sqreen'
```
