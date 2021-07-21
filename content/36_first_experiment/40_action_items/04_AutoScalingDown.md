+++
title = "6.5.4 Set Up Auto Scaling Down"
chapter = true
weight = 04
+++

# Set Up Auto Scaling Down

Our Auto Scaling Policy automatically increases capacity, but we want to make sure we can scale down too. Otherwise, our cluster could continue to scale, resulting in wasted capacity.

We want to follow the same steps as earlier, but instead add a new policy that will be called `ScaleDown`, and we we will be creating a new alarm for it. Instead of triggering when CPU capacity exceeds a certain amount, this alarm will trigger when CPU utilization drops to 30% or below within one minute.

From our Auto Scaling groups page, click **Add policy** to start creating the new policy.
![Container Insights Results](/images/aws_create_down_policy.png)

In the next page Select **Automatic scaling**, followed by **Add Policy**. For **Policy type** select **Simple scaling**. Enter a name for the policy, such as **ScaleDown**. Then, click **Create a CloudWatch alarm**.

## Configure Cloudwatch

We'll use the same `node_cpu_utilization metric` as before. Select **"Select Metric"**, **"Container Insights"**, followed by **"ClusterName, InstanceId, NodeName"**.  Locate `node_cpu_utilization` and press **"Select Metric".**  

![Container Insights Results](/images/aws_select_cpu_utilization.png)

 Now we get to specify metrics and conditions. Under the first section, just change the period to be **"1 minute".**

![Container Insights Results](/images/aws_period_1min.png)

Let's move to **"Conditions"**:

1. Leave **Static** selected.
2. Choose **"Lower/Equal"** 
3. For the box of threshold value, type `30`.
4. Press **"Next"**.

When CPU is less than or equal to 30%, the alarm will be triggered.


![Threshold 30](/images/aws_conditions_30.png)

We now need to configure the actions that happen when the alarm gets triggered. 

For **Alarm state trigger** leave it as **In alarm**. Under that, we want to go ahead and select **Select an existing SNS topic**. and choose the **CPU_Increase** we created earlier and press **Next**.  Now need to give it our alarm a name, let's keep it simple and name it `ScaleDown-Alarm` and press **Next**. Go ahead and review the steps and don't forget to press **Create alarm**. 

Like before, we want to wait 600 seconds (10) minutes before we allow CloudWatch to apply the policy again. Switch back to the "Create scaling policy" tab we were in earlier, and press the refresh icon to locate the `ScaleDown-Alarm` CloudWatch alarm we just created. Under "Take the Action" Choose to **Set to 3 capacity units**. Lastly, for **seconds before allowing another scaling activity**, make it `600` and press **Create**. This policy will reset our cluster size to 3 if CPU usage is low.

![AWS Create scaling policy](/images/aws_create_scaling_policy_down.png)

{{% notice tip %}}
Instead of resetting the cluster size to 3, you could also choose to decrease the number of units by 1.
{{% /notice %}}