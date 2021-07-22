---
title: "1.1 What is Chaos Engineering?"
chapter: true
weight: 10
---

# Introduction to Chaos Engineering

First, let's explain what Chaos Engineering is. Chaos Engineering is:

{{% notice info %}}
"The practice of performing intentional experimentation on a system by injecting precise and measured amounts of harm for the purpose of improving its resilience."
{{% /notice %}}

Let's break this down.

The ultimate goal of Chaos Engineering is to improve the reliability of a system. To do this, we perform carefully planned experiments designed to test our systems for weaknesses and potential failure modes. When we identify a weakness, we deploy a fix, then repeat the experiment to validate that our fix works as intended. We then scale up our experiment or run a different experiment and repeat this process in an ongoing fashion.

Chaos Engineering isn't meant to create chaos, but to find and mitigate chaos. We inject a small amount of harm in order to uncover problems that could cause much more harm if left unresolved. Using Gremlin, we can also revert this harm at any time and completely undo an experiment, making it safe and predictable.

You can learn more about the history and principles of Chaos Engineering by [clicking here](https://www.gremlin.com/community/tutorials/chaos-engineering-the-history-principles-and-practice/).

## How to do Chaos Engineering

A chaos experiment is an intentional, planned process through which we inject harm into a system to learn how it responds and ultimately, to find and fix problems before they happen in a way that impacts customers. Before starting any attacks on your systems, you should fully think out and develop the experiments you want to run. We recommend following the scientific method:

1. Develop a **hypothesis** (how will my systems behave under certain conditions, like low computing resources or poor network conditions?)
2. Define your **blast radius**. This is the number of systems impacted by the experiment. If you're new to Chaos Engineering, start with a small blast radius and scale up as you learn more about your systems.
	- Also define your **magnitude**, or the intensity of the experiment. For example, an experiment that increases CPU usage by 5% has a much lower magnitude than one that increases usage by 50%.
3. Observe your systems and baseline your metrics. This will help you get a clear understanding of the impact of the experiment.
4. Run the experiment. Make sure to set **abort conditions** beforehand, which are the conditions where you should stop the test to avoid unintentional harm.
5. Analyze the results and form a conclusion. Does it confirm or refute your hypothesis?
6. Expand the scope of your experiment and repeat it.
7. Share your results with other teams.


 **Blast Radius** is the number of hosts, containers or resources that are targeted in an experiment. This is also known as the subset of a system that can be impacted by an attack; the worst case impact of a failed experiment. This is usually measured in terms of customer impact (i.e. 10% of customers could be impacted), but may be expressed in hosts, services, or containers. 

 **Magnitude** is how the intensity of the attack you’re running is defined, and can also be defined as the impact that an experiment has. For example, a CPU attack would have a different magnitude if it targeted 10% of CPU versus 20% of CPU.

 **Abort Conditions** are the conditions that would cause to you to press the halt button. They are system conditions that indicate when we should stop a chaos experiment in order to avoid accidental damage

{{% notice tip %}}
One should always define Abort Conditions. Examples of abort conditions include SLAs, Error Rates, Availability, Latency, Traffic, and any other KPI that matters to your organization.  
{{% /notice %}}

When running chaos experiments, it is recommended to start with a small blast radius and magnitude. As you run more experiments and build more confidence, you can increase the blast radius and magnitude. 
