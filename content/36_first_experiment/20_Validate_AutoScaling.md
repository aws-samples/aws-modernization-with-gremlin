+++
title = "Validate Auto-Scaling"
chapter = true
weight = 20
+++

# Unleash Experiment
This first scenario that we’ll run is to help tune autoscaling. Autoscaling in AWS is easy to accomplish, but hard to master due to it being a means to scale infrastructure relative to traffic demands.

We talked about following the scientific method when doing chaos engineering experiemnt, the card below helps you think about it. 

![Experiment Card](/images/Experiment_Card.jpg)

You want to write down your Hypothesis and Abort Conditions before moving to the next step. 
Your hypothesis should be based on what you expect to happen to your system as you unleash the chaos, and the abort conditions will cover the conditions that would cause you to halt the experiment. 

We will start off by going to [Gremlin](https://app.gremlin.com), and configure a CPU attack on all of your hosts.

Click on **"Attacks"** which can be found on the left navigation bar followed by **"New Attack".** 

![Gremlin UI New Attack](/images/gremlin/gremlin_ui_create_new_attack.png)

Under **"What do you want to attack?"**,  you want to select **Hosts**, followed by your three hosts. 

![Gremlin UI Select Hosts](/images/gremlin/gremlin_ui_select_hosts.png)

Under **“Choose a Gremlin”**, select **"Resource"** followed by **"CPU"** to consume all CPU on your targets:


![Gremlin UI CPU Attack](/images/gremlin/gremlin_ui_cpu_attack.png)



Then, click **"Unleash Gremlin"**

Congrats, you unleashed your first attack! In the next page, we will talk about observing our experiments. 