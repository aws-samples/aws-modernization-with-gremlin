+++
title = "8.1 Scheduling Experiments"
chapter = true
weight = 10
+++

# Scheduling Experiments

The easiest way to run automated experiments is by using Gremlin's built-in scheduler. Gremlin allows you to schedule attacks to execute on certain days and within a specified time window. You can also set the maximum number of attacks a schedule can execute.

As an example, we're going to run an automated shutdown attack every two days. We'll start by going back to [Gremlin](https://app.gremlin.com) and creating a new attack. Click on **Attacks** in the left navigation bar, followed by **New Attack**.
![Gremlin UI New Attack](/images/gremlin_ui_create_new__blackhole_attack.png)

Under **"What do you want to attack?"**, select **Infrastructure**, then **Containers**. Keep **Tags** selected as shown below.

![Gremlin UI - Containers - Tags](/images/gremlin_ui_containers_tags.png)

Toggle **Target all containers**. Under the Blast Radius graph, change the **Number of targets to impact** to `1`. This will randomly target one container out of the entire deployment.

![Gremlin UI - Containers - 1](/images/gremlin_ui_containers_tags_target_1.png)

Under **“Choose a Gremlin”**, select **"State"** followed by **"Shutdown"**. Change **Delay** to **`0`** and turn off **Reboot**. This will instantly shut down the container when the attack runs without restarting it.

![Gremlin UI shutdown Attack](/images/gremlin_ui_shutdown_config.png) 

Now we can schedule the attack. Toggle **Schedule for later**, select **Randomly within a time frame**, then select Monday, Wednesday and Friday. For **Runs per day**, set it to **3**. This will run the attack three times during the window. We'll set our run window to run from `09:00` and `15:00` (working hours) in case something goes wrong.

Lastly, click **Unleash Gremlin** button to create the schedule.

![Gremlin UI schedule attack](/images/gremlin_ui_schedule_attack.png) 

To see this and all other schedules, click **"Schedules"** on the left navigation menu.
![Gremlin UI scheduled attacks](/images/gremlin_ui_schedules.png) 
