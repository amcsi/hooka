# Slack

* You can test Slack webhooks with [ngrok](https://ngrok.com/) locally
* See [Slack: Outgoing Webhooks](https://api.slack.com/outgoing-webhooks)

```json
[
    {
        "method": "POST",
        "path": "/slack",
        "command": "echo New message from $USER: $MESSAGE",
        "validate": [
            {
                "source": "jsonBody",
                "find": "payload.token",
                "match": "exactly",
                "value": "W062f8ewla1QPPayTpYc3aqp"
            }
        ],
        "parseJson": [
            {
                "query": "payload.user_name",
                "variable": "USER"
            },
            {
                "query": "payload.text",
                "variable": "MESSAGE"
            }
        ]
    }
]
```
