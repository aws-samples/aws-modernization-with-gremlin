+++
title = "8.4 Using Status Checks"
chapter = true
weight = 24
+++

# Using Status Checks

A Status Check is an automated check that evaluates the health of your environment, and if it detects unhealthy conditions, will immediately halt the active experiment. It sends an HTTP request to an endpoint, evaluates the response status code and JSON body, and will pass or fail based on your defined criteria. The endpoint can be an application URL, a 3rd party monitoring tool, or even CloudWatch.

{{% notice tip %}}
Status Checks are only available when using [Scenarios](https://www.gremlin.com/docs/scenarios/overview/).
{{% /notice %}}

## One-time vs. Continuous Status Checks

Status Checks can be performed as a one-time step in a Scenario, or they can be performed continuously during the Scenario's runtime. One-time Status Checks are useful for ensuring your systems are stable before introducing an experiment/ For example, you might not want to run a CPU attack when you're already experiencing heavy load, or if you're currently experiencing an incident.

Continuous Status Checks automatically repeat every 10 seconds for the entire runtime of the Scenario. This is useful for automatically detecting any problems that might occur during the experiment, and to automatically halt the Scenario to prevent these problems from becoming incidents.

## Benefits

Status Checks provide an easy, safe, automated way of halting an experiment if your systems no longer meet your expected conditions. This makes them ideal for running automated experiments, and to provide another layer of confidence when increasing the scale of your Chaos Engineeirng practice.

To learn more, see our [Status Checks documentation](https://www.gremlin.com/docs/scenarios/status-checks/).