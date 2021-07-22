+++
title = "6.5.1 Create Auto Scaling Rules"
chapter = true
weight = 01
+++

# Create Auto Scaling Rules

We saw that our clusters didn't scale even when we were using 80% CPU across all three nodes. To addres this, we'll configure an Auto Scaling Group (ASG) for our cluster.

Go to the [AWS Console](https://console.aws.amazon.com/ec2/v2/home?region=us-west-2#Home:) and select EC2 from Services.

![AWS Auto Scaling groups](/images/aws_auto_scaling.png)

On the left navigation bar, select **Auto Scaling Groups.**

![AWS Auto Scaling groups](/images/aws_automatic_scaling.png) 

Each Cluster gets its own Auto Scaling Group. Go ahead and check off the one you need. In the next section, select **Automatic scaling**, followed by **Add Policy.**

For **"Policy type"** select **"Simple scaling"**

Enter a name for the policy, for example, `ScaleUp`.

![AWS Auto Scaling groups](/images/aws_create_scaling_policy_prework.png) 

This policy must be triggered by a CloudWatch alarm, which we'll set up in the next section. For now, click **Create a CloudWatch alarm**.
