# Last Updated 8/12/25
Welcome to the second lab in my first repo!
##########################################
Here we have a simple implementation of Etherchannel between two switches. Each switch is connected via 4 ports. We can 
aggregate these ports to essentially mimic one big port. One logical connection! This increases bandwidth and provides AMAZING 
redundancy without any complex changes to the network.


1. Connect two switches with a minimum of two connections (4 ports total). In our example, we used 4 connections (8 total)
2. On the switch, choose your range of interfaces with "int ran"
3. Apply a channel-group (n) and set its mode! Active/Passive (LACP), Auto/Desirable (PaGP), or on
4. Enter the newly create etherchannel with "port-channel (n)" and use it like any other interface! Usually this means
making it a trunk for intervlan traffic, but can also be access if a node needs extra throughput!
5. Profit!


Let me know if you have any questions!
