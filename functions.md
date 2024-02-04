# Functions

## send_alert([AlertData](https://github.com/Wis-Selfbot/Wis-Docs/blob/main/models.md#alertdata))
Sends an alert into the UI.

**Example**
```py
client.server.send_alert(pydantic.AlertData(
    summary="Alert Title",
    message="This is an alert.",
    severity="success",
    windows=True
    ))
```

## send_log(message: string)
Sends a message to the console in the UI.

**Example**
```py
client.server.send_log("This message will be in the console.")
```