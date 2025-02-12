Perform MITM Attack

Question: Use Ettercap to perform a man-in-the-middle (MITM) attack on a local network.

Answer:

    Enable IP forwarding: echo 1 > /proc/sys/net/ipv4/ip_forward.
    Launch Ettercap and select "Sniff > Unified Sniffing."
    Perform ARP poisoning to intercept traffic.

https://medium.com/@redfanatic7/guide-to-mitm-attacks-with-ettercap-6f4d8dc04532
