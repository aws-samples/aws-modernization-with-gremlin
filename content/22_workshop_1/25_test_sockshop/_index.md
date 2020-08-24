+++
title = "Test your sock shop"
chapter = true
weight = 02
+++

# Test Your Sock Shop

In order to test that our sock-shop has been deployed, we are going to grab the load balancer IP and test it in our own browser. 

If you are running this workshop on your own, run the following command in your cloud9 terminal in order to grab the load balancer IP:

```
kubectl get svc -o wide -n sock-shop | grep LoadBalancer
```


If you are running this in an AWS event, log in to your bastion host EC2 instance:


![Bastion-Connect](/images/bastion-connect.png)

Select EC2 Instance Connect (browser-based SSH connection) and click connect.

![Bastion-ec2](/images/bastion-ec2.png)

Run the following command in your browser window to grab the load balancer IP:

```
kubectl get svc -o wide -n sock-shop | grep LoadBalancer
```

Copy the load balancer IP from the terminal and copy it. 

![Bastion-lb](/images/LB-IP.png)

Paste it into your web browser, and you should be good to go.

![Bastion-sock](/images/Browser-Sock.png)

