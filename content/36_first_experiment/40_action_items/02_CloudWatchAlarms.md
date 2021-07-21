+++
title = "6.5.2 Create a CloudWatch Alarm"
chapter = true
weight = 02
+++

# Create a CloudWatch Alarm

We'll use a CloudWatch Alarm to trigger our Auto Scaling Group. First, we need to determine which metric we want to monitor. Since we want to scale on node CPU usage, we'll use the `node_cpu_utilization` metric.

Select **Select Metric**, **Container Insights**, followed by **ClusterName, InstanceId, NodeName**.  Locate `node_cpu_utilization` on any of the EC2 instances and press **Select Metric.**  

![Container Insights Results](/images/aws_select_cpu_utilization.png)

 Now we get to specify metrics and conditions. Under the first section, change the period to **1 minute.**

![Container Insights Results](/images/aws_period_1min.png)

Let's move to **Conditions**:

1. Leave **Static** selected.
2. Choose **Greater** 
3. In the threshold value text box, type `50`.
4. Click **Next**.

![Threshold 50](/images/aws_conditions_50.png)

When CPU is greater than 50, the alarm will be triggered. We now need to configure the actions that happen when the alarm gets triggered. 

For **Alarm state trigger** leave it as **In alarm**. Under that, we want to select **Create new Topic**. Let's give the topic a name, I am going to use `CPU_Increase`. Enter your email address to receive a notification when the alarm is triggered, then click **Create topic**.

 Lastly, leave everything else as it is and press **"Next"**.

![Configure Alarm](/images/aws_configure_alarm_actions.png)

We are going to receive an email titled `AWS Notification - Subscription Confirmation`. Open your inbox, locate it, and click the **Confirm subscription** link. 

![AWS Notification - Subscription Confirmation](/images/aws_notification_subscription_confirmation.png)

You will then see a confimation like this:
![AWS Notification - confirmed](/images/aws_subscription_confirmed.png)

Lastly, back in the CloudWatch "Configure actions" page, enter a name for the alarm. Let's keep it simple and name it `ScaleUp-Alarm`, then press **"Next"**. Go ahead and review the configuration, and don't forget to press **Create alarm**. 