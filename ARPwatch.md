Question: Detect ARP spoofing on your network.

Answer:

1. Use ARPwatch to monitor ARP requests.
2. Look for duplicate IPs with different MAC addresses.

Beispiel

1. Start ARPwatch:  
    `sudo arpwatch -i <interface>`
    Replace <interface> with the network interface you want to monitor (e.g., eth0).  
2. Monitor ARPwatch Logs: ARPwatch logs can be found in /var/log/syslog or /var/log/messages depending on your system configuration. You can use grep to filter for ARPwatch entries:\
   `sudo grep arpwatch /var/log/syslog`\
3. Look for Duplicate IPs: Check the logs for entries indicating duplicate IPs with different MAC addresses. These entries typically contain messages like "flip flop" or "changed ethernet address". 
