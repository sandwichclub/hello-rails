# hello-rails

This is a demo Ruby on Rails app you can deploy to [Skyliner](https://www.skyliner.io). Here's a guide to getting started:

[https://www.skyliner.io/help/quick-start](https://www.skyliner.io/help/quick-start)

If you have any trouble, please drop us a line at [support@skyliner.io](mailto:support@skyliner.io?Subject=Help%20with%20hello-rails).

## Differences from a stock Rails application

* Depends on the `lograge` gem, which converts Rails's weirdly verbose logging
  into production-ready logging using Logstash JSON formatting.
* Depends on Heroku's `rails_12factor` gem, which directs the logs to stdout and
  allows Rails to serve up static assets. (If static asset serving becomes a
  performance hotspot, we recommend setting up CloudFront.)
* Commits `secrets.yaml` to source control. It pulls the production secret base
  from the `SECRET_KEY_BASE` environment variable, which is securely managed by
  Skyliner.
* Adds quotes to the use of `SECRET_KEY_BASE` in `secrets.yaml`, which prevents
  a secret with all digits from being interpreted as a number.
* Depends on `puma-heroku`, which borrows Heroku's recommended Puma
  configuration.
