#      `BloxClient`
##### *PyBlox2.BloxClient*

## Construction
There are no required arguments to constructing a BloxClient.

You can pass `verbose=True` to print additional information on the requests.

## Methods
Methods not listed below are considered `private`
##### `BloxClient.connect(ROBLOSECURITY)`
ROBLOSECURITY must be your bot account's ROBLOSECURITY cookie. Puts the BloxClient in a connected state.

---
##### `async BloxClient.get_user(username)`
Where username is the name of the user. returns a BloxUser object.

*requires BloxClient to be in a connected state*

---
##### `async BloxClient.get_group(id)`
Where id is the group's id. returns a BloxGroup object.

*requires BloxClient to be in a connected state*

---
##### `async BloxClient.fetch()`
Fetches an attribute, attribute must be: `["friend_requests"]`

*requires BloxClient to be in a connected state*

---
## Decorator
### `BloxClient.event`
Adds a coroutine as a listener for a callback event

Possible callback events: ["ready", "request"] (**Those must be the name of the functions**)

#### `"ready"`
Called when the BloxClient.connect function has finished connecting
#### `"request"`
Called each time a request is made to the Roblox API

## Fetchables
BloxClient has the following fetchable attributes: `["friend_requests"]`


## Example

```
import PyBlox2
ROBLOSECURITY = "YOUR_ROBLOSECURITY"


client = PyBlox2.BloxClient(verbose=True)

@client.event
async def ready(ctx):
	# do stuff
	pass


client.connect(ROBLOSECURITY)
```