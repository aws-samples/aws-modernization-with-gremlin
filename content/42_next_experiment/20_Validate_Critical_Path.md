+++
title = "7.3 Perform the Experiment"
chapter = true
weight = 20
+++

# Perform the Experiment

Now let's run the experiment. Open the [Gremlin web app](https://app.gremlin.com). Click on **Attacks** in the left navigation bar, then click **New Attack**.

![Gremlin UI New Attack](/images/gremlin_ui_create_new__blackhole_attack.png)

Under **What do you want to attack?**, select **Infrastructure**, then **Containers**. Note that we selected Containers instead of Hosts this time. We'll also use the search box to search for specific containers. Click on **Exact** on the right-hand side, then click on the search box and enter `catalogue`. You should see the following screen:
![Gremlin UI - Search Tags ](/images/gremlin_ui_select_container_tags.png)

Click on `name:"catalogue"` to select the container. Repeat this process for the `catalogue-db` container. Once you've selected both services, your screen should look like this:
![Gremlin UI Selected Tags](/images/gremlin_ui_selected_catalogue.png)

You can see that the blast radius for this experiment is small: just two containers. However, looks can be deceiving. If these containers are critical, then this small set of containers are holding up our entire application.

Under **Choose a Gremlin**, select **Network** followed by **Blackhole**. 
![Gremlin UI Blackhole Attack](/images/gremlin_ui_network_blackhole.png) 

For the configuration, change **Length** to `360` seconds and leave everything as it is. This will drop all traffic across all network interfaces and ports in both directions.

![Gremlin UI Blackhole Attack](/images/gremlin_ui_blackhole_attack.png)

Next, click **Unleash Gremlin** to start the experiment.