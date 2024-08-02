
2024-07-30 | 11:54

##### Tags: [[Cloud Computing]] [[Azure Cloud]] [[Cloud]]

---

#### 1. Public Cloud

Public Cloud means **EVERYTHING** is built on the Cloud Provider, also known as "Cloud-Native". Everything is running in Azure.

#### 2. Private Cloud

Everything built on company's data centers, also known as On-Premise. The cloud could be [**OpenStack**](https://www.openstack.org/). It can mimic what Azure would do, but it is (or can be) available only for the company that owns it.

#### 3. Hybrid

Using both On-Premise and a Cloud Service Provider, which is basically a connection of two previous solutions. To connect both solutions we can use Express Route for example.



|               | Cost                                                                    | Security                                                                                            | Level of Configuration                                            | Tech Knowledge                                                                                            |
| ------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Public Cloud  | + Most cost-effective                                                   | + Security Controls by default<br>- Might not meet security requirements                            | - Limited based on what the Cloud Service Provider exposes to you | + No need of in-depth knowledge of underlying infrastructure                                              |
| Private Cloud | - Most expensive                                                        | - No guarantee its secure <br>+ can meet any security compliance requirement if you put in the work | + You can configure the infrastructure however you like           | - You need to know in-depth how to configure all levels of your infrastructure                            |
| Hybrid        | + - Could be more cost-effective based on what you offload to the cloud | - You now have to secure your connection to the cloud<br>+ can meet all security requirements       | + You get the best of both worlds                                 | - You need to know in-depth how to configure all levels of your infrastructure and know the CSPs services |


