+++
title = "7.1 Create a Hypothesis"
chapter = true
weight = 10
+++

# Create a Hypothesis

For this experiment, we want to ask **what happens when the critical path has problems?**

Just like the first experiment, we'll define our hypothesis. Our hypothesis is that if a component along our critical path fails, then our application will fail.

To test this, we'll use a Blackhole Gremlin to drop all network traffic between the `catalogue` and `catalogue-db` services. This will significantly impact the product catalog, which is an essential part of any e-commerce shop. Our **blast radius** is the entire cluster, and our **magnitude** is all network traffic between these two services.

Even though we expect a failure, we should make "application failure" an **abort condition** in order to minimize the potential downtime.