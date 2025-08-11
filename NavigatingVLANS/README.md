# Last Updated 8/11/25
Welcome to the first lab in my first repo!
##########################################
In this packet tracer file, you can see how VLANS 10, 20, and 30 are able to communicate between two switches by using a router connected to a switch! 
We get the nickname "router on a stick" because, well, that is exactly what it looks like. We connect a stick to a switch and place a router on top.
The switch we place the router upon does not matter as networks broadcast any unknown address out of all ports. Bang! This means all traffic will reach
the router. Inside the router, we use subinterfaces for each VLAN. When we take incoming traffic into Gi0/0, each traffic is encapsulated then routed on 
Layer 3! For example, we can create int gi0/0.10 (.10 for VLAN 10), set its encapsulation to something vendor neutral like dot1q, then assign it an IP address. This IP 
address will be the same as the Default Gateway for the computers in VLAN 10!

So here is the process,

1. Any computer pings another computer. ARP takes place to get the computer's MAC address 
2. The switches do not know where the computer is! Blast it out all ports (including the port to the router)! 
3. The router sees the VLAN tag of the source computer and 
intakes it into the proper subinterface. The default gateway!
4. The router...routes! Sending it out to the destination IP address, the default gateway/ip address of the other subinterfaces!
5. The switch knows exactly where to send it and the destination computer replies. 
6. Ping is successful

Let me know if you have any questions!
