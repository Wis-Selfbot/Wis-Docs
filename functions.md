# UI Functions

## send_alert([AlertData](https://github.com/Wis-Selfbot/Wis-Docs/blob/main/models.md#alertdata))
Sends an alert into the UI.

**Example**
```py
await client.server.send_alert(models.AlertData(
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
await client.server.send_log("This message will be in the console.")
```

## copy_to_clipboard([ClipboardData](https://github.com/Wis-Selfbot/Wis-Docs/blob/main/models.md#clipboarddata))
Copies text to clipboard.

**Example**
```py
await client.server.copy_to_clipboard(models.ClipboardData(
    info="Username",
    text="MrStretch"
))
```

## update_settings(settings: dict)
Updates the provided setting in the config file

**Example**
```py
await client.server.update_settings({ "sniper": {"enabled": new_state}})
```
**Example usage**
```py
@client.command()
async def sniper(ctx):
    #Turns sniper either on or off
    
    settings = client.server.settings

    new_state = not settings.sniper.enabled

    await client.server.update_settings({ "sniper": {"enabled": new_state}})
```
