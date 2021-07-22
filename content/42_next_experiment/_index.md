+++
title = "Experiment #2: Verify Critical Dependencies"
chapter = true
weight = 42
+++

# Experiment #2: Verify Critical Dependencies

Let's get started on your next experiment! This experiment will focus on critical and non critical dependencies. A dependency is any service that another service requires in order to function. What happens to our application when it can't contact a critical dependency, such as a payment or checkout service?

For this experiment we have to think about our critical path. The **critical path** of an application is the set of components and workflows in an application that is required for the application to serve its core function. Think of it as ["what your business needs in order to make money"](https://www.gremlin.com/blog/understanding-your-applications-critical-path/)

First, let's take another look at the Sock Shop architecture:
![sockshop-topology](/images/sockshop-topology.png)

What are the **critical applications** in this diagram? 

What are the **non-critical applications** in this diagram?

We'll use Gremlin to answer both of these questions and gain a better understanding of the possible failure modes.

{{% children showhidden="false" %}}
