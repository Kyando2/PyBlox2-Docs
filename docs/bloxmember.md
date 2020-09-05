# `BloxMember`
##### *PyBlox2.BloxMember*
This class is a descendant of [`PyBlox2.BloxUser`](bloxuser.md).

## Construction
*Although it is possible to construct it, there is no reason to do so manually*

instead obtain it via `BloxGroup.get_member()`
## Methods

##### `async BloxMember.set_role(role)`
Where role is a BloxRank.

---
##### `async BloxMember.kick()`
Kicks the user from the group.

---
##### `async BloxMember.fetch()`
Fetches an attribute, attribute must be: `["friends"]`

## Fetchables
BloxMember has the following fetchable attributes: `["friends"]`

## Example

```
import PyBlox2
ROBLOSECURITY = "YOUR_ROBLOSECURITY"


client = PyBlox2.BloxClient(verbose=True)

@client.event
async def ready(ctx):
    group = await client.get_group(5029105)
    member = await group.get_member("fego2015")
    role = await group.get_role("Moderators")
    await member.set_role(role)

client.connect(ROBLOSECURITY)
```