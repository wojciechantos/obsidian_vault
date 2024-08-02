
2024-08-02 | 10:26

##### Tags: [[Cloud]] [[Azure Cloud]]

---

High Availability means the ability for a service to remain available by ensuring there is no single point of failure and/or ensure a certain level of performance.

![[HighAvailabilityDiagram.png]]

The idea behind this is that if you have a server which runs a web app location. If you're to run redundant versions of server and if anything happens to a single server, traffic can always be routed to those other servers and that way your service would remain available. Going even further it is even better to have multiple servers in multiple data centers, because if something happens to a certain data center, the traffic can be routed to a different one.

Running your workloads across multiple Availability Zones ensures that if one or two data centers become unavailable your service/apps remains available. 


##### Azure examples: 
Routing traffic in Azure: [[Azure Load Balancer]]