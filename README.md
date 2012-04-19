DHCPRunner
==========

RoadRunner (think fast) equivalent for DHCP lease acquisition on 802.11
networks.

dhcpd.patch -- patch to dhcpd that is right now hardcoded to the AP I was using
to allow proxy DHCP requests. This patch needs to be fixed to allow for:
	1. Dynamically figuring out the reply address (as opposed to the hard-coded
	hack)
	2. Set the IP of the server dynamically, as well

mac80211.patch -- embeds the DHCP lease request in the 802.11 Information
elements. Also, extracts the response from the IEs and prints out the response

hostapd.patch -- does the actual proxying of DHCP lease, gets the lease, and
sends the reply; other AP software can be easily adapted for the same thing
