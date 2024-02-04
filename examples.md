# Examples

Example Command:

```py
@client.command()
async def sum(ctx, *args):
    try:
        total = sum(int(arg) for arg in args)
        await ctx.send(total, delete_after=client.server.settings.config.deleteAfter)
    except ValueError:
        await ctx.send("Please provide numbers only.", delete_after=client.server.settings.config.deleteAfter)
```

Example Event:
```py
@client.listen("on_message")
async def log_message(message):
    if message.author.id == client.user.id:
        await client.server.send_log(f"{message.content}") # Logs the message content to the console in the UI
```