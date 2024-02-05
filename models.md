# Models
All predefind models use this format: models.ModelName

## AlertData(summary, message, severity?, windows?)
| Name | Type | Optional | Description |
|-----------|-------------|----------|-------------|
| summary   | string | No | Title of the alert |
| message   | string | No | Message of the alert |
| severity  | [Severity](ttps://github.com/Wis-Selfbot/Wis-Docs/blob/main/literals.md#severity)? | Yes | Severity level of the alert |
| windows   | boolean? | Yes | Boolean for Windows alert |

## ClipboardData(info, text)
| Name | Type | Optional | Description |
|-----------|-------------|----------|-------------|
| info   | string | No | Info about the text |
| text   | string | No | Text to copy to clipboard |