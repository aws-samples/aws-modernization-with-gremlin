+++
title = "Validate Auto-Scaling"
chapter = true
weight = 20
+++

# Unleash Experiment
This first scenario that we’ll run is to help tune autoscaling. Autoscaling in AWS is easy to accomplish, but hard to master due to it being a means to scale infrastructure relative to traffic demands.

We talked about following the scientific method when doing chaos engineering experiemnt, the card below helps you think about it. 

{{% notice tip %}}
TODO: Experiment Card
{{% /notice %}}

You want to write down your Hypothesis and Abort Conditions before moving to the next step. 
Your hypothesis should be based on what you expect to happen to your system as you unleash the chaos, and the abort conditions will cover the conditions that would cause you to halt the experiment. 

We will start off by going to [Gremlin](app.gremlin.com), and configure a CPU attack on all of your hosts.

Click on **"Attacks"** which can be found on the Left Navigation Bar followed by "New Attack". 

{{% notice tip %}}
TODO: Gremlin UI
{{% /notice %}}

Under **"What do you want to attack?"**,  you want to select **Hosts**, followed by your three hosts. 

{{% notice tip %}}
TODO: Gremlin UI
{{% /notice %}}

Under “Choose a Gremlin”, select **"Resource"** followed by **"CPU"** to consume all CPU on your targets:
{{% notice tip %}}
TODO: Gremlin UI
{{% /notice %}}

For the configuration, change **Length** to 360 seconds,for **CPU Capacity** make that 80% and for **Cores**, use the dropdown to choose "All Cores". 

Then, click "Unleash Gremlin"

Congrats, you unleashed your first attack!