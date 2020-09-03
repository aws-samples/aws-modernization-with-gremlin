+++
title = "3.2 Validate Critical Path"
chapter = true
weight = 20
+++

# Unleash Experiment
This second scenario that we’ll run is around us asking ourselves **What happens to your application when a critical application has issues?**


You want to write down your Hypothesis and Abort Conditions before moving to the next step. 
Your hypothesis should be based on what you expect to happen to your system as you unleash the chaos, and the abort conditions will cover the conditions that would cause you to halt the experiment. 

Head back to[Gremlin](app.gremlin.com), and configure a Blackhole attack on all of your hosts.

Click on **"Attacks"** which can be found on the Left Navigation Bar followed by "New Attack". 

{{% notice tip %}}
TODO: Gremlin UI
{{% /notice %}}

Under **"What do you want to attack?"**, you want to select **Containers**, followed by searching for `orders-db`. 

{{% notice tip %}}
TODO: Gremlin UI
{{% /notice %}}

Under “Choose a Gremlin”, select **"Network"** followed by **"Blackhole"**. 
{{% notice tip %}}
TODO: Gremlin UI
{{% /notice %}}

For the configuration, change **Length** to 360 seconds,and leave the rest as it is. 

Then, click "Unleash Gremlin"

