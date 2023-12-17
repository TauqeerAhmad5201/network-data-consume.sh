# Script to check the data consumption

```
#!/bin/bash
# Monitor network usage stats
# Usage: ./network_usage.sh

net_device=$(ip route | awk '/via/ {print $5}')
TRANSMITTED=$(ifconfig "$net_device" | awk '/TX packets/ {print $6$7}')
RECEIVED=$(ifconfig "$net_device" | awk '/RX packets/ {print $6$7}')
