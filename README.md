# Twitch.Drops.Miner.Windows
This application allows you to AFK mine timed Twitch drops, without having to worry about switching channels when the one you were watching goes offline, claiming the drops, or even receiving the stream data itself. This helps both you and Twitch save on bandwidth and hassle. Everyone wins!
This application allows you to AFK mine timed Twitch drops, without having to worry about switching channels when the one you were watching goes offline, claiming the drops, or even receiving the stream data itself. This helps both you and Twitch save on bandwidth and hassle. Everyone wins!

How It Works:


Every several seconds, the application pretends to watch a particular stream by fetching stream metadata - this is enough to advance the drops. Note that this completely bypasses the need to download any actual stream video and sound. To keep the status (ONLINE or OFFLINE) of the channels up-to-date, there's a websocket connection established that receives events about streams going up or down, or updates regarding the current amount of viewers.

Features:


Stream-less drop mining - save on bandwidth.
Game priority and exclusion lists, allowing you to focus on mining what you want, in the order you want, and ignore what you don't want.
Sharded websocket connection, allowing for tracking up to 8*25-2=199 channels at the same time.
Automatic drop campaigns discovery based on linked accounts (requires you to do account linking yourself though)
Stream tags and drop campaign validation, to ensure you won't end up mining a stream that can't earn you the drop.
Automatic channel stream switching, when the one you were currently watching goes offline, as well as when a channel streaming a higher priority game goes online.
Login session is saved in a cookies file, so you don't need to login every time.
Mining is automatically started as new campaigns appear, and stopped when the last available drops have been mined.



Usage:


Download and unzip the latest release - it's recommended to keep it in the folder it comes in.
Run it and login into your Twitch account using your username and password, and a 2FA key if you have one setup. It's recommended to avoid having to double-take this step, as you can run into CAPTCHA that will prevent you from trying to log in again for the next 12+ hours. You can retry afterwards though.
After a successful login, the app should fetch a list of all available campaigns and games you can mine drops for - you can then select and add games of choice to the Priority List available on the Settings tab, and then press on the Reload button to start processing. It will fetch a list of all applicable streams it can watch, and start mining right away. You can also manually switch to a different channel as needed.
Make sure to link your Twitch account to game accounts on the campaigns page, to enable more games to be mined.
Persistent cookies will be stored in the cookies.jar file, from which the authorization (login) information will be restored on each subsequent run.
