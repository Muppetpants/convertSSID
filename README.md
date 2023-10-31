# convertSSID

Bash script to print MAC address and Beacon Probe Request SSIDs from Tshark output.

This script will takes a .txt argument. The .txt should can be created with the following:

Beacons:
``` tshark -r <pcap> -Y wlan.fc.type_subtype==8 -T fields -e wlan.bssid -e wlan.ssid | sort | uniq > <beacons.txt>```

Probe Requests:
``` tshark -r <pcap> -Y wlan.fc.type_subtype==4 -T fields -e wlan.sa -e wlan.ssid  | sort | uniq > <probes.txt>```

Create a local copy of the script.

```wget https://raw.githubusercontent.com/Muppetpants/convertSSID/main/convertSSID.sh```

Make the script executable

```sudo chmod +x convertSSID.sh```

Run the script

```sudo ./convertSSID.sh <probes.txt>```
# Example Output

![image](https://github.com/Muppetpants/convertSSID/assets/103676092/837d7021-6473-4fa1-a555-8ee8ca3b66c6)


