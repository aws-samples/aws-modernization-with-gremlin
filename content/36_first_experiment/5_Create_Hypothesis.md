+++
title = "6.1 Create A Hypothesis"
chapter = true
weight = 10
+++

# Create A Hypothesis

The first experiment we'll run is to verify and fine-tune our cluster's autoscaling behavior. Autoscaling in AWS is easy to accomplish, but hard to master due to it being a means to scale infrastructure relative to traffic demands.

We talked about following the scientific method when doing Chaos Engineering, starting with developing a hypothesis. To help with this, we've provided experiment cards (like the one below) to help design this experiment. 

![Experiment Card](/images/Experiment_Card.jpg)

First, we'll define our hypothesis. Our **hypothesis** is: as demand increases, our systems will automatically scale to meet this increase, resulting in no impact to our systems.

To test this, we'll use a CPU Gremlin to consume 80% CPU across all of our hosts for 360 seconds. Our **blast radius** is the entire cluster, and our **magnitude** is 80% CPU usage. Our **abort conditions** are:

- Any HTTP 500 errors
- Host failure
- Data loss

Here is an example of the filled out experiment card: 
![Experiment Card Example](/images/Experiment_Card_Example.jpg)

Next, we'll define our steady state.