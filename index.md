# Using the PerformanceTestingBot app
The PerformanceTestingBot app performs throughput and stress tests on a specified endpoint. Just specify a verified endpoint and a branch and the performanceBotTest will report statistics on every pull request.

## Recommended usage
You should run this on one instance of your application to understand your scaling thresholds in production. You can also use the stress test feature to get an understanding of your scaling implementation for your production cluster. Use throughput tests to make sure that your apps performance remains consistent.

## Installation
In order to prevent malicious attacks against other sites, you will need to verify ownership of your domain. It's a simple process that involves exposing a temporary GET endpoint.
1) Upon installation to a repository, a github issue will be created in the repository with a unique id.
2) Create a GET endpoint with that responds 200 with that unique id as the response
3) Add the endpoint to your `.performanceTestingBot` file in the `verification_url` field
   [Example](https://raw.githubusercontent.com/jeffm14/performanceTestExampleRepo/master/.performanceTestingBot)

### Types of tests
#### Stress Test:
Will test the limits of your deployed application, (up to 700 Transactions/Queries per second).

#### Threshold test:
Will hit your endpoint at a specified threshold for a given amount of time (up to 15 minutes).

## How it runs

#### Run Conditions
You can specify a test to run \
1) If a merge and base branch is specified (i.e. develop -> master) \
2) Every PR if no merged / base branch is specified \

#### Run Trigger/Events
1) On a created pull request the PerformanceTestingBot will run the specified tests and comment the result back in the open pull request \
2) If commented `@performancetestingbot` in a pull request that matches a run condition \
   ![Example screenshot](https://github.com/jeffm14/performanceTestExampleRepo/blob/master/screenshot3.png?raw=true)

#### Example output:
[PullRequest](https://github.com/jeffm14/performanceTestExampleRepo/pull/56)

## Configuration
The Schema for your `.performanceTestingBot` needs to conform the following schema linked below.

[Schema](https://github.com/jeffm14/performanceTestExampleRepo/blob/master/schema.json)

[Example](https://github.com/jeffm14/performanceTestExampleRepo/blob/master/.performanceTestingBot)

![Example configuration](https://github.com/jeffm14/performanceTestExampleRepo/blob/master/screenshot2.png?raw=true)

## Future Features
JMeter

Endurance testing

Acceptance Criteria

Variable inputs

## Support / Feature requests
### Community
Join us on slack!

[![slack_logo](https://raw.githubusercontent.com/jeffm14/performanceTestExampleRepo/master/Slack_logo_new_mini.png)](https://join.slack.com/t/performancetestingbot/shared_invite/zt-eufjei5s-DwcFjc9hmtUOyxemYygUXA)

### Contact Paid Support
* Product support
* General questions
