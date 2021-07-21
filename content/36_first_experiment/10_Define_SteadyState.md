+++
title = "6.2 Gather Baseline Observations"
chapter = true
weight = 10
+++

# Gather Baseline Observations

Before running our experiment, we should get a baseline understanding of how our application operates under normal conditions. This includes validating the user experience, as well as collecting metrics and creating dashboards that will help us track the user experience.

Let's take another look at the architecture of our Sock Shop application.

## Shop Sock Architecture

The architecture of the demo microservices application was intentionally designed to provide as many microservices as possible. Please don't use the Sock Shop application as a model for a well architected micro-services application, it was built for demonstration purposes. If you are just beginning to architect your own micro-services based cloud native application, [Weaveworks](https://www.weave.works/contact/) would be happy to help recommend the correct architecture for your use case.

We can see on the architecture diagram how all these services talk to each other: 
![sockshop-topology](/images/sockshop-topology.png)

Now that we know the architecture, what are some things we should consider when gathering baseline observations?

## User Experience 
Let’s get a baseline measurement of our Sock Shop application by using it like a normal user. Some things to try:

+ Register and log in using the below credentials:
    - **Username:** `user`	
    - **Password:** `password`
+ Browsing products by clicking on them.
+ Adding and removing items from cart.
+ Checking out and completing purchases.

While running through these tasks, we want to note:

+ How long it takes to complete each task.
+ How responsive the website feels.
+ Whether we see any error messages.

This is our application’s baseline. We’ll compare our application’s behaviors while running experiments to this baseline to determine the impact of the experiment. Next, we’ll gather baseline metrics to quantify these behaviors so we can monitor for changes during the experiments.

## Baseline Metrics

As we go through this workshop you want to always compare your experiment results to the steady state of your application. 

Let's navigate to [Container Insights](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#container-insights:performance) browser tab to view the metrics we've generated.

From here you can choose a number of different views. We’re going to narrow down our timelines to a custom time range of just 30 minute so we can zoom into our recently collected insights.

To do so go to the Time Range option at the top right of The CloudWatch Container Insights windows and selecting 30 minutes.

![Metric Time](/images/metrictime.png)

![alt text](/images/metriceksservice.png "Metric Service")
You can also view some different metrics based on the Dropdown menu options. Let's take a quick look at some of those items.

![alt text](/images/switches.gif "Switching Metrics")
