# Script to check the data consumption

```
#!/bin/bash
# Monitor network usage stats
# Usage: ./network_usage.sh

net_device=$(ip route | awk '/via/ {print $5}')
TRANSMITTED=$(ifconfig "$net_device" | awk '/TX packets/ {print $6$7}')
=$(ifconfig "$net_device" | awk '/RX packets/ {print $6$7}')

printf "%s\n" "$(tput bold)📼 TRANSMITTED $(tput sgr0): $TRANSMITTED"
printf "%s\n" "$(tput bold)📡 RECEIVED $(tput sgr0): $RECEIVED"
```

currently working to get the data seperately. working out on the script to catch up. 
