# Advanced configuration in Ruby

***

# Ruby agent configuration

You can configure the Sqreen Ruby agent with settings in a configuration file, or with environment variables. This page describes the configuration options available for the Ruby agent.

# Configuration methods and precedence

The default method to configure the Sqreen Ruby agent is through the configuration file `sqreen.yml` in the config directory. 

You can also configure most options with environment variables. Here are the order of precedence for configuration:

1. Environment variables
2. Configuration file `sqreen.yml`
3. Default configuration options

Environment variables override the settings in the `sqreen.yml` configuration file. The configuration file settings override the agent default options.

# Edit configuration file options

The Ruby agent configuration file `sqreen.yml` uses a standard [yaml format](https://en.wikipedia.org/wiki/YAML). As in Ruby on Rails, you can use [ERB](http://guides.rubyonrails.org/configuring.html#configuring-a-database) inside `sqreen.yml`

The most important configuration option is the Sqreen token, used to identify the application on Sqreen. Options are listed below.

!!! warning "YAML indentation"
    When you edit the config file, be sure to indent only with two spaces. If you do not indent correctly, the Sqreen agent will throw an error at Startup (`Unable to parse configuration file`)

!!! info "Deploying Sqreen configuration"
    Configuration file should be deployed on the servers running Sqreen

Sqreen settings can be optionally adjusted according to your needs. This section lists the possible configuration options you have with Sqreen Ruby agent.

# Setting up the path of the configuration file

You can use a specific path for the configuration file using `SQREEN_CONFIG_FILE` environment variable:

```shell
export SQREEN_CONFIG_FILE=/custom/path/sqreen.yml
```

# Configuration variables

The Sqreen agent can be configured using environment variables or a YAML file. Here are the settings that can be changed:


Variable name | Role | YAML key name | Default value
--------------|------|---------------|--------------
SQREEN_TOKEN | The Sqreen token. This identifies the agent to Sqreen backend servers | token | Empty
SQREEN_CONFIG_FILE | Custom location for the YAML based config | Empty
SQREEN_LOG_LOCATION | Specify a custom file to write Sqreen logs | log_location | log/sqreen.log
SQREEN_LOG_LEVEL | Sqreen logging level | log_level | WARN
SQREEN_REPORT_PERF_NR | Report Sqreen overhead to as NewRelic custom metrics | report_perf_newrelic | `false` (disabled) |
SQREEN_DISABLE| Prevent the Sqreen agent from starting. Any value in this environment variable will disable Sqreen.| disable| `false` (Sqreen is enabled)

# Multiple Rails environments

The Sqreen token is the only required setting. The YAML configuration also supports using a different section per Rails environment:

```yaml
      token: mysecrettoken #general configuration

      production:
          token:  mysecretproductiontoken # override general configuration
```