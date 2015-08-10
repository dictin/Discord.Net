# Discord.Net v0.2
A .Net API Wrapper for the Discord client (http://discordapp.com).

## This is an alpha!
The Discord API is still in active development, meaning this library may break at any time without notice.
Discord.Net is also in early development so several functions may be unstable or not work at all.

# Features
- Login/Logout (with credentials or anonymous)
- Accepting/Creating/Deleting Invites (standard or human readable)
- Receiving/Sending Messages
- Creating/Destroying Servers
- Creating/Destroying Channels
- Kick/Ban/Unban/Mute/Unmute/Deafen/Undeafen Users
- Several Discord Events

# Upcoming
- Modifying User/Channel/Server Settings
- Sending Private Messages (Replies are supported, starting a new private chat currently is not)

# Example (Echo Client)
```
var client = new DiscordClient();
client.MessageCreated += (s, e) =>
{
	client.SendMessage(e.Message.ChannelId, e.Message.Text);
};
await client.Connect("discordtest@email.com", "Password123");
await client.AcceptInvite("channel-invite-code");
```

# Known Issues

- Due to current Discord restrictions, private messages are blocked unless both the sender and recipient are members of the same server.
- Caches do not currently clean up when their entries are no longer referenced, and there is no cap to the message cache. For now, connecting and disconnecting will clear all caches.