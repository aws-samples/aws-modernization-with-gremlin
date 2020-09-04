+++
title = "2.5.4 AutoScaling Down Setup"
chapter = true
weight = 04
+++


## Set up Auto Scaling: 

We want to follow the same steps as earlier, but instead the policy will be called “ScaleDown,” and we we will be creating a new alarm. This Alarm will be for when CPU utilization is less than or equal to (<=) 30% within a 1 minute.

Under "Take the Action" Choose to **"Set to" "3" "capacity unit"**. Lastly, for "seconds before allowing another scaling activity", make it `600`. We want our Auto Scaling Policy to be triggered when the alarm we just created goes off and we want AWS to wait 10 minutes (600 seconds) before the auto scaling policy gets applied again. 

![AWS Create scaling policy](/images/aws_create_scaling_policy_down.png)

