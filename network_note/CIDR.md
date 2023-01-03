# CIDR(Classless InterDomain Routing)[RFC1519](https://www.rfc-editor.org/rfc/rfc1519.html)
## The extension problem of Internet
* In 1990s there are 3 extension problem of Internet
	* Internet route table scale issue.
		* [Solution:] [[Aggregation]], [[CIDR]], NAT
	* Class B IP address is going to be exhausted.
		* [Solution:] [[CIDR]], NAT
	* All IP address will be ran out.
		* [Solution:] IPv6
## CIDR
* It's a feature for Routing Protocol:
	* RIPv2, EIGRP, OSPF, IS-IS, BGP
* Its a feature for Routers:
	* If Router is enabled with CIDR, it will find the longest matched prefix in routing table for the IP packet.
	* If Router use Class method, it will first find the matched main class network(A class/8; B class/16; C class/24) and then find the match subnet under the main class network.
## How CIDR solve the problem
 1. Internet route table scale issue: In abstract, the internet topology is a hybrid hub-and-spoke. The CIDR provide a finer granularity of subnets, thus ISPs can summarize([[Aggregation]]) the route in a proper way.
 2. Class B IP address is going to be exhausted: In Class network, while C class provide 254 host IPs, B class provide 65534 IPs which could be a sharp curve and will leave a lot of wasted IPs. The CIDR provide a finer granularity.
## Shortcoming of CIDR
* The shorcoming of CIDR is more relay on IP schema and [[Aggregation]].
	1.  It separate the bundle network of ISP address space
	2.  Most ISP wont advertise prefix greater than /19 to upstream