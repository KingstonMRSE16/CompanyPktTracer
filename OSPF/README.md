# Last Updated 8/12/25
Welcome to the third lab in my first repo!
##########################################
Welcome to one of my favorite concepts in networking! Are you tired of manually setting static routes?
Sending traffic to one point, hoping it doesn't go down or else you need to set a new static? Then let me
introduce you to Open Shortest Path First! The greatest way to route traffic with ease and provide redundancy!

OSPF involves creating an OSPF process and area. In simple terms, we start an OSPF process, much like starting
an application process when we open an app on our computer, and give it a process ID. In the packet tracer case, 
it is 100. These are locally significant, so do not worry about matching these across routers. The thing we DO
need to match is the area! All routers must be in the same area to pass information. It is how we segment traffic
within the OSPF protocol. Different areas? No routing, sir!

Anyway, in a nutshell, OSPF is like kiddies in elementary playing "whisper down the lane". The router with the
ID of 4.4.4.4 can not see all the way over to the 192.168.1.0 network, but luckily, the routers between them
whisper down the lane and tell it! It is just easier to have the routers tell each other where to route
traffic rather than manually setting addresses. BUT you can still have a manual as backup (also called a 
floating static route). I am not a teacher (yet) so just 3 paragraphs probably doesn't explain OSPF perfectly,
but do the practice below and see it work!

1. Click on the router with the Router ID of 4.4.4.4 and do
	Router> enable <enter>
	Router# conf t <enter>
2. Ping a computer in the orange network from the router (it should fail!)
	(config)# do ping ip 192.168.1.13
3. Identify the networks it is connected to!
	192.168.0.8
	192.168.0.12
4. Let's create our process with the following
	(config)# router ospf 100
5. And let's add those two networks!
	(config-router)# network 192.168.0.0 0.0.0.3 area 0
	(config-router)# network 192.168.0.0 0.0.0.3 area 0
6. If you are familiar with subnet masks, here we are using the opposite -> wilcard masks!
7. We also usually add the loopback, but make it passive
	(config-router)# network 4.4.4.4 0.0.0.0 area 0
	(config-router)# pass l0
8. Okay now ping the computer network again!



Let me know if you have any questions!
