CMPT 371 Chapter 1 Notes
[Source](https://www.cs.sfu.ca/CourseCentral/371/qgu/)

- **IP protocol** specifies the format of the information sent and received 
among routers and end systems

- basic service is connectionless, does not guarantee delivery; **stream-oriented** data delivery is based on the basic service and 
guarantees delivery

- **protocols:**  the Internet requires a universal end-system 
identifications scheme (aka addressing scheme)

- **network edge:** end-systems/hosts
- **client-server model** vs **peer-to-peer model**
- **access networks:** links/networks connecting end systems
- **internet core (backbone):** connects access together forming a global 
network

## Network classification
- **broadcast network:* a single communication medium shared by all 
end-systems attached (usuall LAN covering a building, campus etc are broadcast 
networks)
- **point-to-point** (switched) network: end-systems and switches connected 
by point-to-point communication links (usually WAN are such networks)

## Internet Backbone:
-a switched network of interconnected routers

## Circuit Switching:
- dedicated physical path connect source and destination end-systems
Three phases
1. connection set-up
2. first-in-first-out order
3. connection termination
- step 1 may be time consuming, step 2 has little delay, but path may be 
occupied even when there is no data transmission

## Packet switching
- based on store and forward routing:
	- message partitioned into packets of uniform size with header
	- packets transmitted independently
	- **overhead traffic**: ratio of header to data
- performance depends on link capacities, buffer size at routers, traffic 
patterns, packet size (which determines overhead traffic)

## Internet Backbone Structure
- **Tier1** networks: ISPs which provide national and int
ernational coverage; 
	- multiple peer networks connect together at **IXP** (internet 
exchange point)
- **Tier2** networks: regional networks; customers of Tier1 ISPs
- **Tier3** networks are local ISPs; customers of Tier1/2

## Delay
- ** circuit switching** delay = connection set-up time + signal 
propagation time
- **packet switching** delay:
	- delay at one router defined as the time from a packet arriving at 
router to packet arriving at next router is
` d_nodal = d_proc + d_queue + 
d_trans + d_prop `
	- nodal PROCessing: time for checking error in packet and deciding output link
	- QUEUEing: time of packet waiting at queue of output link for 
transmission
		- packet size * average packet arrival rate / link bandwidth
	-TRANSmission: time for transmitting packet from queue to output link	
		-packet size / throughput
	-PROPagation: time for signal propagation from one router to another
		- length of link / propagation speed

## Throughput
- bits per time unit
- **bottle link:** a link with the minimum throughput in a path
- throughput between two hosts = min{R_S, R_C, R/N}
	- R_S: throughput of link from sender to Internet backbone
	- R_C: throughput of link from Internet backbone to receiver
	- R: throughput of Internet backbone
	- N: number of connections sharing the Internet backbone

## Packet Loss
- packet arriving at full queue is discared
- router informs source and may resend packet

## Protocols
- allow us to discuss data communication independent of networkd hardware
- services provided by layer n are realized by protocols of layer n and 
services provided by layer n-1

## TCP/IP layers
- application layer
- transport layer: end-to-end reliable delivery of data (TCP)
- internet layer: data transmission across multiple networks (IP)
- netwokr access layer: data exchange between end device and network
- physical layer: access to physical medium

##Protocal Data Unit (PDU)
- data packet which contains data from the next higher layer, head which 
contains control information

## Network security:
attacks such as 
- malware into host via internet
- denial of service (DoS): make resources unavailable to legitimate 
access with bogus access
- packet sniffing (read packet transmitted)
- IP spoofing ( change IP address in data packets)
