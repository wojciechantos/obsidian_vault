
2024-08-02 | 11:05

##### Tags: [[Cloud]] [[Azure Cloud]]

---
Fault Tolerance term stands for the ability for your service to ensure there is no single point of failure. **Preventing** the chance of failure.

To handle failures we use the concepts of **Fail-overs**:


![[FaultToleranceDiagram.png]]

**Fail-overs** is when you have a plan to shift traffic to a redundant system in case the primary system fails. A common example is having a copy (secondary) of your database where all ongoing changes are synced. The secondary system is not in use until a fail over occurs and it becomes the primary database.

##### Azure examples: 
We can use [[Azure Traffic Manager]] 