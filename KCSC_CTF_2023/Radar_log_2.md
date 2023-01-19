# CTF Write-Up - Radar Log 2

## Description

The challenge is to refer to the same pcap-file as in Radar Log 1 and determine which area of interest the aircraft passed over. The goal is to wrap the area in the KCSC{}-tag and replace spaces with "_", e.g. KCSC{Oslo_Sentralstasjon}.

## Techniques Used

- Wireshark
- Network protocol analysis
- GPS coordinates
- Google Maps

## Solution

To solve this challenge, I first used Wireshark to analyze the pcap-file from Radar Log 1, again the Asterix protocol was used. I then looked for the GPS position from the first and last package sent by the aircraft.

I took these coordinates and plugged them into Google Maps. By drawing a line between the two coordinates, I was able to see that the aircraft passed over Kongsberg Teknologipark.

This was indeed the flag: **`KCSC{Kongsberg_Teknologipark}`** 

## Conclusion

This challenge required an understanding of network protocols and the ability to use Wireshark to extract GPS coordinates. By using Google Maps and drawing a line between the first and last GPS coordinates, I was able to determine the area of interest that the aircraft passed over and successfully complete the challenge.
