+++
title = "2.5 Validate Action Items"
chapter = true
weight = 50
+++

You've made your application more resilient by setting up auto-scaling. Let's verify it's doing what you expected. As we did earlier,  You want to write down your Hypothesis and Abort Conditions before moving to the next step. 

Head to[Gremlin](app.gremlin.com), and configure a CPU attack on all of your hosts.

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

# Observe

Are your results different on CloudWatch and Container Insights than the first time you ran the CPU Experiment?
