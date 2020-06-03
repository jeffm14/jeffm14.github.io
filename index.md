# Using the PerformanceTestingBot app
The PerformanceTestingBot app performs throughput and stress tests on a specified endpoint. Just specify a verified endpoint and a branch and the performanceBotTest will report statistics on every pull request.

## Recommended usage
You should run this on one instance of your application to understand your scaling thresholds in production. You can also use the stress test feature to get an understanding of your scaling implementation for your production cluster. 

### Types of tests
#### Stress Test:
Will test the limits of your deployed application, currently will max out at 700 Transactions/Queries per second.

#### Threshold test:
Will hit your endpoint at a specified threshold for a given amount of time (up to 15 minutes). 

## How it runs

#### Run Conditions
You can specify a test to run 
1) If a merge and base branch is specified (i.e. develop -> master)
2) Every PR if no merged / base branch is specified

#### Run Trigger/Events
1) On a created pull request the PerformanceTestingBot will run the specified tests and comment the result back in the open pull request
2) If commented `@performancetestingbot` in a pull request that matches a run condition
![Example screenshot](https://github.com/jeffm14/performanceTestExampleRepo/blob/master/screenshot3.png?raw=true)

#### Example output:
[PullRequest](https://github.com/jeffm14/performanceTestExampleRepo/pull/56)

## Installation
1) Tests are configured by a `.performanceTestingBot` file at the root of the repository. 
2) You will also need to verify that you own the domain / endpoint. To do this you must create an endpoint that accepts a GET request that responds with a verification_id. I will reach out with the verification_id after installation.

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
