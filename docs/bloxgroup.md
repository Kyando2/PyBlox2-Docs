# `BloxGroup`
##### *PyBlox2.Groups.BloxGroup*

## Construction
*Although it is possible to construct it, there is no reason to do so manually*

instead obtain it via `BloxClient.get_group()`
## Methods

##### `async BloxGroup.get_role(role_set_name)`
Returns a [`BloxRank`](bloxranks.md) object with the selected role_set_name.

---
##### `async BloxGroup.get_role(username)`
Returns a [`BloxMember`](bloxmember.md) object with the selected username.

---
##### `async BloxGroup.fetch()`
Fetches an attribute, attribute must be: `["join_requests", "members", "settings"]`

## Fetchables
BloxGroup has the following fetchable attributes: `["join_requests", "members", "settings"]`

## Example

```
import PyBlox2
ROBLOSECURITY = "YOUR_ROBLOSECURITY"


client = PyBlox2.BloxClient(verbose=True)

@client.event
async def ready(ctx):
    group = await client.get_group(5029105)
    await group.fetch("members")
    print(group.members[0])

client.connect(ROBLOSECURITY)
```