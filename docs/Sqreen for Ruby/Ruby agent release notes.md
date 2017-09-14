# Ruby agent release notes

***

## [1.8.1] - 2017-08-09

### Fixes

* Ensure that rules are correctly reapplied after a process fork

## [1.8.0] - 2017-08-07

### Added

* Smaller login payloads

### Fixes

* make `disable` accept more value as true
* Add version of Sqreen gem in User-Agent

## [1.7.2] - 2017-07-18

### Fixes

* Improve speed of early attack detection
* Correctly disable early attack detection when a request is whitelisted

## [1.7.1] - 2017-07-10

### Fixes

* Fixes some security rules getting lost when applying whitelisting

## [1.7.0] - 2017-06-30

### Added

*  Completely redesigned whitelist/blacklist support

### Fixes

* Better support badly encoded strings in parameters 

## [1.6.5] - 2017-06-09

### Fixes

*  Only escape maliciously injected reflected values
*  Better File parameters handling

## [1.6.4] - 2017-05-29

### Fixes

*  Accept more kind of values in Haml protection

## [1.6.3] - 2017-05-22

### Fixes

*  Improve Haml5 support 

## [1.6.2] - 2017-05-16

### Fixes

* Display custom error page when an attack in cached in the templates

## [1.6.1] - 2017-05-15

### Fixes

* Ensure all protection use the selected protection mode behavior

## [1.6.0] - 2017-05-12

### Added

* More early attack detection rules

### Changes

* Refactor dynamic rules execution

## [1.5.0] - 2017-04-18

### Added

* Use ERB inside sqreen.yml config file                                         
* Disable sqreen through config file

## [1.4.3] - 2017-04-07

### Added

* More support for HAML & Slim templating engines
* Capturing more slightly more detailed traffic metrics 

## [1.4.2] - 2017-03-28

### Fixes

* Parameter inclusion check was too wide

## [1.4.0] - 2017-03-27

### Added

* Initial support for HAML templating engine (reflected XSS)
* Initial support for whitelisting a request path

### Changes
* Change patch numbering system

## [1.3.2] - 2017-03-09

### Changes

* Faster exit when application is in development mode

## [1.3.1] - 2017-03-06

### Changes

* Improve error logs

## [1.3.0] - 2017-02-23

### Changes

* More stable middleware instrumentation

### Fixed

* Fix encoding objects when sending to sqreen

## [1.2.0] - 2017-01-20

### Changes

* Improve error logs

## [1.1.5] - 2016-12-15

### Fixed

* Better metrics collection

## [1.1.4] - 2016-12-15

### Added

* Do not start by default in `cucumber` environment

## [1.1.2] - 2016-12-14

### Fixed

* Improve security APIs statistics collection
* Stop freezing user-agent strings

## [1.1.1] - 2016-12-07

### Changes

* Improve IP address selection heuristic

## [1.1.0] - 2016-12-06

### Added

* Authentication SDK ([documentation](doc:ruby-agent-users-monitoring))

## [1.0.0] - 2016-12-05

### Changes

* Improved agent network communication performance (new agent login)

## [0.8.1] - 2016-06-06 

### Changes

* Improved performance (pre-conditions fix)

## [0.8.0] - 2016-05-30

### Added

* New feature: [Suspicious activities on accounts](doc:protect-your-users)
* New feature: [Content Security Policy management](doc:content-security-policy)

## [0.7.X] - 2016-04-20

* First version published to https://rubygems.org/gems/sqreen