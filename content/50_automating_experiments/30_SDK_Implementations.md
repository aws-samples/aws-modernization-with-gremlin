+++
title = "8.3 Using the Gremlin SDK"
chapter = true
weight = 20
+++

# Using the Gremlin SDK

Gremlin provides an open source [Python SDK](https://github.com/gremlin/gremlin-python). This allows you to easily interact with the Gremlin API from a Python application. For details, see our [GitHub repository](https://github.com/gremlin/gremlin-python).

The easiest way to get started is to install the SDK using `pip`:

```
pip3 install gremlinapi
```

To authenticate, you can use the Bearer Token retrieved in the previous section (Using the Gremlin API). You can also use another authentication method such as an API key or login using your username and password.

```
from gremlinapi.config import GremlinAPIConfig as config
config.team_id = '<your team ID>'
config.bearer_token = '<your bearer token>'
```

For example, let's run our CPU attack against a single container that contains the tag `app:catalogue`:

```
body = {
  'target': {
    'type': 'Random',
    'containers': {
      'multiSelectLabels': [
        'app': [
          'catalogue'
        ]
      ]
    },
    'percent': '100'
  },
  'command': {
    'type': 'cpu',
    'commandType': 'CPU',
    'args': [
      '-l',
      '60',
      '-a',
      '-p',
      '80'
    ]
  }
}
attack_guid = attacks.create_attack(body=body, teamId=config.team_id)
```

To learn more about the Python SDK, see the [GitHub repository](https://github.com/gremlin/gremlin-python).