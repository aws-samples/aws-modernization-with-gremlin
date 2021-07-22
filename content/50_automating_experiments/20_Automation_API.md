+++
title = "8.2 Using the Gremlin REST API"
chapter = true
weight = 20
+++

# Using the Gremlin REST API

Gremlin provides a REST API that lets you programmatically perform actions, including running attacks and Scenarios. The easiest way to generate a REST API command is to create and configure an attack using the web app, scrolling to the bottom, and clicking on **Gremlin API Examples** in the bottom-right corner. The popup window contains everything you need to run your attack using the API. 

![Gremlin UI - Gremlin API Examples ](/images/gremlin_ui_api_examples.png) 

This generates a curl command that you can enter into a terminal, API tool, CI/CD solution, performance testing suite, or any other application that can make HTTP requests. You can choose which Authorization method to use, including Bearer Tokens or any API keys you've created.

![Gremlin UI - Gremlin API Examples ](/images/gremlin_ui_api_examples2.png) 

For now, copy and paste the contents of the **CURL example** text box into your terminal. Here's an example for a CPU attack::

```
curl -i -X POST 'https://api.gremlin.com/v1/attacks/new?teamId=ed09d800-018a-591a-b591-75cb717a3eb5' -H 'Content-Type: application/json;charset=utf-8' -H 'Authorization: Bearer Yy1kNWJhMWMyNy05OGVlLTU2ZWUtOWUwZS00OTY5NzA1ZGUyOWI6YW5hKzEyQG******************' -d '{"target":{"hosts":{"ids":["ip-10-0-48-196.ec2.internal"]},"type":"Exact"},"command":{"type":"shutdown","commandType":"Shutdown","args":["-d","0"]}}'
```
![AWS EC2 Console - Run Attack ](/images/gremlin_ui_api_aws_console.png) 

After sending the request to the API, we can watch the attack start in the Gremlin web app:

![Gremlin UI - Gremlin API - Attack Pending](/images/gremlin_ui_api_attack_unleashed.png) 
You can learn more about Gremlin's API via our [docs](https://www.gremlin.com/docs/api-reference/overview/), and you can click through our [interactive Swagger documentation](https://app.gremlin.com/api) to see the full set of capabilities. 