+++
title = "Automate Experiments"
chapter = true
weight = 50
+++

# Automate Experiments

Running ad-hoc experiments are a great way of getting started with Chaos Engineering and testing for unknown conditions. However, much like quality assurance testing, the best way to ensure your applications and systems are reliable is by automating your experiments. Automation is the practice of performing chaos experiments in a **continuous** way to prevent **regression into past failures.**

## Why Automate?

Automating experiments helps ensure that your applications don’t become vulnerable to failure modes over time. Performing a chaos experiment validates reliability at a single point in time, but applications change. A fix implemented in an earlier version of an application might no longer work as expected in a later version. By automating chaos experiments, we can continuously check for these regressions and protect ourselves against failures. It’s also a forcing function for application developers, since any changes they make will be validated against these failure modes. It encourages developers to build applications with reliability in mind, which in turn makes failures less likely.

Ideally you should automate experiments in production, since production is a unique environment and any failures will directly affect customers. But when starting out, automate your experiments in pre-production. Once you’re comfortable automating experiments, gradually move them into production.

Gremlin lets you automate experiments in various ways, which we’ll cover in the next sections:

{{% children showhidden="false" %}}
