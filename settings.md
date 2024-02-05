# Settings
Settings are predefined using Pydantic models and can be accessed via `client.server.settings`. Note that the settings can change overtime, so if you encounter any inconsistencies let us know.

```py
from typing import Literal, Optional, Any
from pydantic import BaseModel


class Command(BaseModel):
    name: str
    command: str
    slashCommand: bool
    args: Optional[dict]
    botId: str
    delay: int
    channel: str
    timestamp: Optional[int] = None

class Commander(BaseModel):
    enabled: bool
    commands: list[Command]

class Config(BaseModel):
    prefix: str
    token: str
    capmonsterKey: str
    password: str
    autoStartup: bool
    dev: bool
    deleteAfter: int

class SniperSettings(BaseModel):
    enabled: bool

class AdBotSettings(BaseModel):
    enabled: bool
    message: str
    channels: list
    delay: int
    timestamp: Optional[int] = None
    
class Shortcut(BaseModel):
    name: str
    response: str
    deleteCommand: bool

class Shortcuts(BaseModel):
    enabled: bool
    shortcuts: list[Shortcut]

class Party(BaseModel):
    max: int
    current: int

class Button(BaseModel):
    name: Optional[str]
    url: Optional[str]

class CustomRPC(BaseModel):
    enabled: bool
    applicationID: Optional[str]
    type: Literal["PLAYING", "STREAMING", "LISTENING", "WATCHING", "COMPETING"]
    url: Optional[str]
    state: Optional[str]
    name: Optional[str]
    details: Optional[str]
    party: Party
    timestamp: Literal["", "start", "currentTime"]
    assetsLargeImage: Optional[str]
    assetsLargeText: Optional[str]
    assetsSmallImage: Optional[str]
    assetsSmallText: Optional[str]
    buttons: list[Button]

class Mock(BaseModel):
    channelId: str
    userId: str
    
class Settings(BaseModel):
    mock: list[Mock]
    config: Config
    sniper: SniperSettings
    adbot: AdBotSettings
    shortcuts: Shortcuts
    rpc: CustomRPC
    commander: Commander
```