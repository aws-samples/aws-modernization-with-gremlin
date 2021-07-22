+++
title = "6.4 Observe the Impact"
chapter = true
weight = 30
+++

# Observe the Impact

While the attack is running, switch back to [Container Insights](https://console.aws.amazon.com/cloudwatch/home?region=us-west-2#container-insights:performance). If you don't see a CPU spike after a short time, try reducing the time period of the chart. While viewing the metrics, ask yourself:

* Was your hypothesis correct? 
* Did you see a CPU increase?
* Did autoscaling kick in? Do you see a new host?
* If autoscaling didn't kick in, why not? Is your policy misconfigured? Do you have a policy set up in the first place?


## Results 

We can see on the Container Insights' **CPU Utilization** graph that the CPU spike was seen, but the graph for **Number of Nodes** saw no increase.

![Container Insights Results](/images/container_insights_exp1_results.png)

![Container Insights Results](/images/container_insights_exp1_results2.png) 

Does this mean our experiment failed? Not at all! **By running this experiment, we found a potential failure mode before it had a chance to impact customers**. We now have an action item to reconfigure our autoscaling rules. We can then verify them by repeating this experiment.