# `BloxUser`
##### *PyBlox2.BloxUser*

## Construction
*Although it is possible to construct it, there is no reason to do so manually*

Obtain it via `BloxClient.get_user()`
## Methods

##### `async BloxUser.accept_friend_request()`
Accept the user's friend request if there is one.

---
##### `async BloxUser.decline_friend_request()`
Decline the user's friend request if there is one.

---
##### `async BloxUser.request_friendship()`
Sends the user a friend request.

---
##### `async BloxUser.unfriend()`
Unfriends the user.

---
##### `async BloxUser.follow()`
Follows the user.

---
##### `async BloxUser.unfollow()`
Unfollows the user.

---
##### `async BloxUser.block()`
Blocks the user.

---
##### `async BloxUser.unblock()`
Unblocks the user.

---
##### `async BloxUser.fetch()`
Fetches an attribute, attribute must be: `["friends"]`

## Attributes
BloxUser has the following fetchable attributes: `["friends"]`

## Example

```
import PyBlox2
ROBLOSECURITY = "YOUR_ROBLOSECURITY"


client = PyBlox2.BloxClient(verbose=True)

@client.event
async def ready(ctx):
	user = client.get_user("Roblox")
	await user.fetch("friends")
	print(user.friends)


client.connect(ROBLOSECURITY)
```

