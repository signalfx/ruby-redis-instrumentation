# Redis::Instrumentation

This gem provides OpenTracing auto-instrumentation for commands send through the Redis client.


# :warning:This repository and its published libraries are archived

The ruby-redis-instrumentation reached End of Support on March 1, 2025.

Splunk has adopted OpenTelemetry. Please visit official documentation page: [Instrument Ruby applications for Splunk Observability Cloud](https://docs.splunk.com/observability/en/gdi/get-data-in/application/ruby/get-started-ruby.html#get-started-ruby). Use [OpenTelemetry Ruby Instrumentation distribution](https://github.com/open-telemetry/opentelemetry-ruby) to send telemetry data to Splunk Observability Cloud. 
Do not integrate `ruby-redis-instrumentation` into new services.


## Supported Versions

- MRI 2.0 and newer
- Redis 4.0.1 and newer

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'signalfx-redis-instrumentation'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install signalfx-redis-instrumentation

## Usage

```ruby
require 'redis/instrumentation'

Redis::Instrumentation.instrument
```

`instrument` takes two optional arguments:
* `tracer`, to set a custom OpenTracing tracer. It will default to `OpenTracing.global_tracer`.
* `db_statement_length`, to set a maximum value length for the `db.statement` tag.  It will not truncate by default.

## Development

After checking out the repo, run `bin/setup` to install dependencies. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/signalfx/ruby-redis-instrumentation.

## License

The gem is available as open source under the terms of the [Apache 2.0 License](https://opensource.org/licenses/Apache-2.0).
