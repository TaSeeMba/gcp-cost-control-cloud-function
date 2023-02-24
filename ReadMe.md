# GCP cost control cloud function

This code is used in a cloud function that can be used as a utility to cap costs and stop usage for a GCP project by disabling Cloud Billing. This automation process is dependent on receiving budget notifications.

Disabling billing on a project will cause all Google Cloud services in the project to terminate. You might cap costs because you have a hard limit on how much money you can spend on Google Cloud. 

## How it works

The general workflow for disabling billing is described [here](https://cloud.google.com/billing/docs/how-to/notify#functions_billing_slack-python). The process is broken down into the following steps:
1. Create a budget in your billing account.
2. Create a pubsup topic that will receive billing notifications.
3. Configure the pubsub topic as the notification endpoint for the budget.
4. Create a cloud function using the code in this repo. The function should be configured to listen to the pubsub topic. 

The above process is automated using terraform in a separate project.


