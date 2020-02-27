# discord-issue-linux

Im using a script+crontab on linux to solve this traceback


### Tracebacks








### Script

```
#!/bin/bash
PID=ps -aux | grep discord | awk 'NR==1{print "{\"pid\":" $2 "}" }'
echo "Killing discord PID..."
kill -9 $PID
echo "Restarting discord..."
discord ;
```
