# `social.presence` message (server)

A message sent by a Ribbon to the client to indicate that a friend has changed their presence.

## Format

* (object):
    * (integer) `id`: [The id of this message.](../Ribbon.md#id-messages)
    * (string) `command`: Always `"social.presence"`.
    * (object) `data`:  
        * (string) `user`: The id of the user whose presence was changed.
        * (string ([Detail](#detail))) `detail`: What that user is currently doing.
        * (boolean) `invitable`: Whether the user can be invited to a lobby.
        * (string ([Status](#status))) `status`: The social status of the user.

## Detail

The valid values of `data.detail` are any of the following:

* `"menus"`: User is in the menus.
* `"tl"`: User is in a Tetra League match.
* `"zen"`: User is playing Zen.
* `"blitz"`: User is playing Blitz.
* `"40l"`: User is doing a 40-line sprint.
* `"lobby_ig:ABCD"`: User is in a public lobby, where `ABCD` is the room code.
* `"lobby:X-PRIV"`: User is in a private lobby, or the client is not included in the user's visibility settings.
* `"lobby:X-QP"`: User is in the Quick Play lobby.
* `""` (empty): User has disabled presence broadcasting.

## Status

The valid values of `data.status` are any of the following:

* `"away"`: User is idle.
* `"busy"`: User has turned on Do Not Disturb and/or is in a Tetra League match.
* `"online"`: User is online.
* `"offline"`: User is offline.
