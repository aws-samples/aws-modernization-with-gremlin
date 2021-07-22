+++
title = "Adopt Gremlin Into Your Organization"
chapter = true
weight = 60
+++

# Adopt Gremlin Into Your Organization

Now that you've seen the value of Gremlin and Chaos Engineering first-hand, how do you get buy-in from your teammates and leadership?

When presenting Chaos Engineering to your organization, start by framing it in terms of how it will help meet organizational goals. Think about the technical goals your organization is trying to achieve, such as:

- Meeting Service Level Agreements (SLAs) and their corresponding Service Level Objectives (SLOs).
- Reducing the frequency of high-severity incidents.
- Reducing the number of customer complaints due to downtime.
- Lowering your mean time to resolution (MTTR).

For the business side of the organization (i.e. leadership), demonstrate how these goals contribute to higher-level business objectives, such as:

- Streamlining engineering processes.
- Meeting requirements for regulatory compliance.
- Improving the customer experience.
- Successfully launching new products and services with minimal downtime.

If you can create a clear link between Chaos Engineering and business objectives, you’re much more likely to sell leadership on the value of Gremlin. To learn more about demonstrating this value, check out our Playbook on [How to Convince Your Organization to Adopt Chaos Engineering](https://www.gremlin.com/champion-playbook/).

## Chaos Engineering Maturity

Once you've gotten comfortable running ad-hoc chaos experiments on your own services and among your own team, try introducing other teams within your organization to the practice. Remember to start small, then gradually scale up:

+ Introduce Chaos Engineering into one service/team at a time.
+ Start with low-magnitude experiments and safe (i.e. non-production) environments.
+ Reproduce a production outage.
+ Run recurring [GameDays](https://www.gremlin.com/community/tutorials/how-to-run-a-gameday/) and [FireDrills](https://www.gremlin.com/blog/prepare-your-team-to-handle-incidents-remotely/) to practice real-world incident management scenarios.
+ Automate attacks using the scheduler or API.
+ Run experiments in production.

This isn't a strictly linear route, either. You may run a CPU experiment on a single service in production, but then run a low-magnitude CPU experiment on another service in testing or staging. Remember not to rush: Chaos Engineering is a way of learning more about your systems and building resilience over time. Run experiments, record your observations, and share your thoughts not just among your own team, but with the entire engineering organization. If an experiment goes wrong, just hit the big red halt button to stop the attack and record your thoughts. There's no wrong way to run an experiment using Gremlin.