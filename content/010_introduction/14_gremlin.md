---
title: "1.3 What is Gremlin?"
chapter: true
weight: 14
---

# What is Gremlin?

Gremlin is a hosted SaaS platform that enables engineers to build more reliable software with Chaos Engineering. Gremlin provides an easy to use, safe and secure enterprise service to test the reliability of cloud infrastructure and applications. With Gremlin, you can run Chaos Engineering experiments against hosts, containers, or Kubernetes resources in order to identify and address weaknesses before they cause problems for your customers.

We offer 11 different attack types, or "Gremlins:"

#### Resource Gremlins
Resource attacks let you generate load across computing resources including CPU, memory, and storage. This lets you prepare for sudden changes in load, validate autoscaling rules, test monitoring and alerting configurations, and make sure your systems are stable even under high demand.

|Gremlin  | Impact                                                        |
|--------|----------------------------------------------------------------|
| CPU    |  Generates high load for one or more CPU cores.                |
| Memory |  Allocates a specific amount of RAM.                           |
| IO     |  Puts read/write pressure on I/O devices such as hard disks    |
| Disk   |  Writes files to disk to fill it to a specific percentage.     |

#### State Gremlins

State attacks allow you to change the state of your environment by terminating processes, shutting down or restarting servers, and changing the system clock. This lets you prepare your systems for unexpected changes in your environment such as a node failure or application crash.

|Gremlin         | Impact                                                         |
|----------------|----------------------------------------------------------------|
| Shutdown       |  Performs a shutdown (and an optional reboot) on the host operating system to test how your system behaves when losing one or more cluster machines.                                              |
| Time Travel    | Changes the host’s system time, which can be used to simulate adjusting to daylight saving time and other time-related events.                                                              |
| Process Killer |  Kills the specified process, which can be used to simulate application or dependency crashes. (Note: does not work for PID 1, consider a Shutdown attack instead)                                    |

#### Network Gremlins

Network attacks let you simulate unhealthy network conditions including dropped connections, high latency, packet loss, and DNS outages. This lets you build applications that are resilient to unreliable network conditions.

|Gremlin      | Impact                                                        |
|-------------|---------------------------------------------------------------|
| Blackhole   |  Drops all matching network traffic.                          |
| Latency     |  Injects latency into all matching egress network traffic     |
| Packet Loss |  Induces packet loss into all matching egress network traffic.|
| DNS         |  Blocks access to DNS servers.                                |

More information on what Gremlin is all about can be found on the official [Gremlin documentation page](https://www.gremlin.com/docs/infrastructure-layer/attacks/).