+++
title = "Action Items"
chapter = true
weight = 40
+++

# Experiment Action Items
Did you have any action items come out of your chaos engineering experiment? 
If one of them is to implement auto scaling policies, follow these steps:

### Remediation: Set up auto scaling

1. Go to the [AWS Console](https://console.aws.amazon.com/) and select EC2 from Services.

2. On the left navigation bar, select **Auto Scaling Groups.**

3. Each Cluster gets its own Auto Scaling Group. Select the one you need, and then at the lower navigation, select [Scaling Policies.](https://console.aws.amazon.com/ec2autoscaling)

4. Select Automatic scaling, followed by  Add Policy, then select **Add policy.**

{{% notice tip %}}
TODO: Screenshots how to do this 
{{% /notice %}}


{{% notice warning %}}
TODO: Update with Simple Scaling Steps 
{{% /notice %}}
5. We will be creating two of these, one to scale up and one to set back to the usual 3.
Give the Policy a name, we will call it “Cluster-ScaleUp” and select Create New Alarm. Create the alarm to go off when CPU utilization is greater than or equal to 13% for at least 1 minute, and name it “Cluster-ScaleUp.”

Press Create Alarm. Now you will be taken back to finish editing the policy.

Edit the values to add “1” instance and then wait 120 seconds before the next activity. Press Create when finished.

We want to follow the same steps as above, but instead the policy will be called “Cluster-ScaleDown,” we will be creating a new alarm. This Alarm will be for when CPU utilization is less than or equal to (<=) 13% within 15 minutes.


{{% notice tip %}}
TODO: Screenshots how to do this 
{{% /notice %}}
