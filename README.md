
# Getting started with Cider-CI for Ruby on Rails Projects

## Automatic Parallelized Testing

To get started with automatic testing on Cider-CI:

1.  Have an instance of Cider-CI ready, see the [Cider-CI Installation Documentation][].
2.  Import the desired project into your instance of Cider-CI.
3.  Copy the provided Cider-CI configuration file `cider-ci.yml` from this repository
    to the root of you project.
4.  Commit and push.

You are done! Watch the job "Tests" pass or fail in your instance of Cider-CI.


## Static Code Analysis

The provided Cider-CI configuration file also includes a job for static code
analytics called `Code-Checks`. You will need to add the following to your
`Gemfile` to and run `bundle` make it work:

    gem 'cider_ci-support', group: [:development, :test]
    gem 'rubocop', require: false, group: [:development, :test]

## Advanced Topics and Customization

### Database Configuration

The databases PostgreSQL, MySQL, and sqlite3 are supported. The configuration
will look for `db/database_cider-ci.yml`, then `db/database.yml` for a base
database configuration. If neither is found sqlite3 will be used.

### Testing Frameworks

Cider-CI supports all of the three common testing frameworks
[minitest](http://docs.seattlerb.org/minitest/), [RSpec](http://rspec.info/)
and [cucumber](https://cucumber.io/).

### Executor Traits - Rubies, Browsers

An executor with the default traits installed provides a reasonable up to date
version of [MRI Ruby](https://www.ruby-lang.org/) (default) and
[JRuby](http://jruby.org/) via (rbenv)[https://github.com/sstephenson/rbenv].

For integration tests the browsers Firfox ESR, Google Chrome and the headless
Phantomjs are available.

  [Cider-CI Installation Documentation]: http://docs.cider-ci.info/installation/

### Customization

The provided Cider-CI configuration file works for vanilla rails projects. It
is also a basis for customization.

We recommend to have a look at the following two projects for customization
examples. The [leihs] loan system uses a custom strategy for bundling features
into Cider-CI tasks. The [Madek] media archive system performs matrix testing.
It combines the Cider-CI task generator with custom properties on a task basis.
[Madek] moreover chains Cider-CI jobs with dependencies to the end of a fully
continuous integration implementation including automatic deployments.

  [Madek]: http://github.com/Madek
  [leihs]: http://github.com/zhdk/leihs

