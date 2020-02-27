# discord-issue-linux

Im using a script+crontab on linux to solve this traceback


### Tracebacks


```
[ntz@ntz-qa]~: discord
Discord 0.0.10
Starting app.
Starting updater.
[Modules] Modules initializing
[Modules] Distribution: remote
[Modules] Host updates: enabled
[Modules] Module updates: enabled
[Modules] Module install path: /home/ntz/.config/discord/0.0.10/modules
[Modules] Module installed file path: /home/ntz/.config/discord/0.0.10/modules/installed.json
[Modules] Module download path: /home/ntz/.config/discord/0.0.10/modules/pending
[Modules] No updates to install
[Modules] Checking for host updates.
[Modules] Host is up to date.
[Modules] Checking for module updates at https://discordapp.com/api/modules/stable/versions.json
[Modules] No module updates available.
(electron) 'isAccessibilitySupportEnabled function' is deprecated and will be removed. Please use 'accessibilitySupportEnabled property' instead.
(electron) 'setBadgeCount function' is deprecated and will be removed. Please use 'badgeCount property' instead.
Failed to get crash dump id.
Report Id: 
Violación de segmento (`core' generado)
```





### Script

```
#!/bin/bash
PID=ps -aux | grep discord | awk 'NR==1{print "{\"pid\":" $2 "}" }'
echo "Killing discord PID..."
kill -9 $PID
echo "Restarting discord..."
discord ;
```
