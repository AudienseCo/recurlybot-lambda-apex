# Recurlybot Lambda Packager
Lambda package for [Recurlybot](https://github.com/AudienseCo/recurlybot), a Slack bot to notify new Recurly subscriptions.

![](http://g.recordit.co/MDZuZBIOAe.gif)

## What's this?
An [AWS lambda function](https://aws.amazon.com/lambda/features/?nc1=h_ls) that given a POST request from [Recurly webhooks](https://docs.recurly.com/docs/webhooks) publishes a message in a the configured Slack channel via a [Slack Incomming Webhook](https://api.slack.com/incoming-webhooks)

## How to deploy it?
- Rename `project-dist.json` as `project.json`
- Edit the AWS role and the environment variables
    - `SLACK_CHANNEL`: the Slack channel where you want to puslish the notifications.
    - `SLACK_URL`: Slack incomming webhook url.
    - `PROFILE_URL`: Customer information page in case you want to link the notification to your CRM or to the Recurly account page.
- Setup AWS credentials for Apex, see [http://apex.run/#aws-credentials](http://apex.run/#aws-credentials)
- `npm install` 
- `apex deploy`
- Now visit your AWS Lambda dashboard and connect the Lambda to  [API Gateway](https://aws.amazon.com/api-gateway/?nc1=h_ls)
- Get the API Gateway public endpoint and setup it in the Recurly Webhooks configuration

