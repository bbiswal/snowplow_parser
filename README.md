# snowplow_parser

Snowplow enables marketers the ability to track in detail how users are engaging with a shopping cart, website or application. Learn more on the [Snowplow Github Page](https://github.com/snowplow).

This Ruby program does the following:
1. Reads Snowplow Cloudfront log files stored in a S3 bucket
2. Parses the log lines based on the event type
3. Stores the parsed data into a separate S3 bucket
4. Loads the parsed data into a Redshift cluster

## Getting Started

To start, follow the instructions for setting up the Javascript web tracker and Snowplow Cloudfront collector found on the [Snowplow GitHub page](https://github.com/snowplow/snowplow/wiki/Setting-up-SnowPlow).

Once you've setup the S3 bucket for cloudfront logs, also setup a S3 bucket for holding cloudfront logs that have been parsed already.  You'll want to specify both buckets these under "BUCKET_CLOUDFRONT_LOGS" and "BUCKET_PARSED_LOGS"

### Installing

To install the appropriate gems:

```
bundle install
```

### Running

Before running make sure the REDSHIFT_URL, AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY variables are set.  Be sure to also set the constant variables explained at the top of the program.

```
ruby snowplow_parser.rb
```

### Tests

If there's interest in developing this further, I will morph this into a class with automated tests.

## Authors

* Bobby Biswal
