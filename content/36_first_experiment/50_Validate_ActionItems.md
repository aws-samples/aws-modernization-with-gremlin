+++
title = "6.5 Validate Action Items"
chapter = true
weight = 60
+++

# Validate Action Items

You've made your application more resilient by setting up auto scaling. It should look something like this:
![AWS Scaling policies](/images/aws_scaling_policies.png)


Let's verify it's doing what you expected by repeating our experiment. As we did earlier, we'll create an experiment card:

![Experiment Card](/images/Experiment_Card.jpg)

We'll fill it out with the same parameters as before:

![Experiment Card Example](/images/Experiment_Card_Example.jpg)

Let's head back to [Gremlin](app.gremlin.com), and configure a CPU attack on all of your hosts. Click on **Attacks** which can be found on the left navigation bar followed by **New Attack**.

![Gremlin UI New Attack](/images/gremlin/gremlin_ui_create_new_attack.png)

Under **What do you want to attack?**, select **Infrastructure**, then **Hosts**. Select your three hosts, or select **Target all hosts** to automatically target the cluster.

![Gremlin UI Select Hosts](/images/gremlin/gremlin_ui_select_hosts.png)

Under **Choose a Gremlin**, select **Resource**, then **CPU**. Set the **Length** to `360` seconds, change **CPU Capacity** to `80`, and select **All Cores** from the dropdown. 


![Gremlin UI CPU Attack](/images/gremlin/gremlin_ui_cpu_attack.png)

Then, click **Unleash Gremlin**.

While the experiment is running, keep an eye on CloudWatch Container Insights. Are the metrics different than the first time you ran the experiment? Did CloudWatch detect the high usage and provision a new node? If so, did you get an email notification? If so, congratulations! you've successfully ran an experiment, used your observations to implement a fix, then verified that fix! In a later section, we'll show you how to automate experiments to ensure that your fix works continuously.