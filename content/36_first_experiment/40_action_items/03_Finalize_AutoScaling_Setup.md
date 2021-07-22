+++
title = "6.5.3 Finalize Your Auto Scaling Configuration"
chapter = true
weight = 03
+++

# Finalize Your Auto Scaling Configuration

Switch back to the "Create scaling policy" tab we were in before creating the alarm, and select the CloudWatch alarm we just created. You might need to refresh the page if it doesn't appear automatically. Under "Take the Action", configure the drop-down lists and text boxes to **Add 1 capacity units**. 
Lastly, for **seconds before allowing another scaling activity**, make it `600`. 
![AWS Create scaling policy](/images/aws_create_scaling_policy.png)

This sets our Auto Scaling Policy to trigger when the alarm goes off, while also requiring 600 seconds (10 minutes) to pass before the policy can be applied again.



