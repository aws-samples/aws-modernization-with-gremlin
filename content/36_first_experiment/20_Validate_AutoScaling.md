+++
title = "Validate Auto-Scaling"
chapter = true
weight = 10
+++

# Unleash Experiment
This first scenario that we’ll run is to help tune autoscaling. Autoscaling in AWS is easy to accomplish, but hard to master due to it being a means to scale infrastructure relative to traffic demands.
<TOO: Experiment Card>
TODO: Talk about Hypothesis and Abort Conditions. 

We will start off by going to Gremlin, and configure a CPU attack on all of your hosts.

Click  on the left "Attacks" on the Left Navivgation Bar followed by "New Attack". 
<image of UI>
Flip "Target all hosts" to on. 

Configure your attack under “Choose a Gremlin” to consume all CPU on your targets:

Click "Unleash Gremlin"
