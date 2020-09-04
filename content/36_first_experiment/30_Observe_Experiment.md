+++
title = "2.4 Observe Experiments"
chapter = true
weight = 30
+++

## Observe Experiment

Now that you kicked off the attack, switch back to [Container Insights](https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#container-insights:performance) to observe the chaos. 

Feel free to zoom in on the time frame we can see the large spike in CPU utilization from the experiment that we just launched. 

##### Is your hypothesis correct? 
##### Did you see a CPU increase? 
##### Did Auto-Scaling kick in? 
##### Did anyone set up an auto-scaling policy?


## Results 

![Container Insights Results](/images/container_insights_exp1_results.png)

We can see on the Container Insights' **CPU Utilization** graph that the CPU spike was seen, but the graph for **Number of Nodes** saw no increase. We are going to make an Action Item to setup Auto-Scaling and verify it. 