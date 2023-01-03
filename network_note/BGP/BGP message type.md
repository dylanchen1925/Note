# Open
Sent after TCP connection is established. Including below parameters:
* **BGP version**: BGP-v4 nowadays.
* **AS number**: Identify the AS number.
* **Hold time**: 3 seconds at least. If it is 0, then BGP will not send Keepalive message. By default Cisco set it 180 sec. It will chose the minimum one if the peer hold time is different.
* **BGP identifier**: Neighbor IP, choose the biggest one from below, configured router id > loopback > up interface IP
* **Optional parameters**: Auth, Multi-Protocol, route refresh etc
# Keepalive
If router accept the parameter in [[#Open]], it will response with a keepalive message. After that, it will send the keepalive in period of 1/3 of [[#^Hold time]]
# Update
Used to advertise or withdraw route.
* **NLRI(Network Layer Reachability Information)**: Advertise one or more IP prefixes, which combined with(length, prefix). ^3a89e2
* **Path Attributes**: The Path Attributes of the NLRI. ^16695c
* **Withdraw Routes**: Like **NLRI**[[#^3a89e2]], but to withdraw the prefix.
***BE AWARE***: One **NLRI**[[#^3a89e2]] may contain multiple prefixes, but each [[#Update]] only contain one BGP route - all the prefixes in one BGP route have the same **Path Attributes**[[#^16695c]]
# Notification
In case there is any error, BGP will send **Notification** to close the BGP connection.