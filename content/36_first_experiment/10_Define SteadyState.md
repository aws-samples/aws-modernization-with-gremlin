+++
title = "Define Steady State"
chapter = true
weight = 10
+++

# Defining Steady State

Before we begin creating failures, a starting point would be to understand the steady state of your application. This includes validating the user experience and revising your dashboard and metrics to understand your systems are operating under normal conditions. 

### User Experience 
Go explore your Sock Shop application. 

### Baseline Metrics
{{% notice tip %}}
TODO: Should we make them build a dashboard? can we load this into EventEngine? Do we only show Insights?
{{% /notice %}}

Head to your [CloudWatch Dashboard](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#dashboards:) and take a look at the graphs.

You can also take a look under [Container Insights](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#container-insights:infrastructure/map), to see all the container/services running on your EKS cluster. 

{{% notice tip %}}
TODO: screenshot of Container Insights
{{% /notice %}}

As we go through this workshop you want to always compare your experiment results to the this steady state of your application. 