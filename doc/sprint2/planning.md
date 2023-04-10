RCOMP 2022-2023 Project - Sprint 2 planning
===========================================
### Sprint master: 1211148 ###

# 1. Sprint's backlog #

* T.2.1 - Development of a layer two and layer three Packet Tracer
  simulation for building A, encompassing the campus backbone.
  Integration of every member’s Packet Tracer simulation into
  a single simulation.


* T.2.2 - Development of a layer two and layer three Packet Tracer
  simulation for building B, encompassing the campus backbone.

* T.2.3 - Development of a layer two and layer three Packet Tracer
  simulation for building C, encompassing the campus backbone.


* T.2.4 - Development of a layer two and layer three Packet Tracer
  simulation for building D, encompassing the campus backbone.


# 2. Technical decisions and coordination #

The following were the design decisions made for the project, and are to be followed by all members of the project:

* Packet Tracer version : **8.2.1**
* VTP Domain name : **rc23dbg5**
* VLANID Range : **385 - 415**
* IPV4 Address Block : **10.80.112.0/21**
* ISP router IPv4 node address : **121.60.202.50/30**

* Devices nomenclature : **<building\>\_<floor\>\_<device-type\>**

### Block of addresses per building ###

| Building | Total Nodes | Assigned IPv4 block |
|:--------:|:-----------:|:-------------------:|
|    A     |     435     |   10.80.112.0/22    |
|    B     |     218     |   10.80.116.0/24    |
|    C     |     190     |   10.80.117.0/24    |
|    D     |     188     |   10.80.118.0/24    |


### VLAN database + SubNet associated ###

| VLANID | Nome da VLAN | IPv4 Address Block |
|:------:|:------------:|:------------------:|
|  385   |   backbone   |   10.80.112.0/25   |
|  386   |    wifi_A    |  10.80.112.128/25  |
|  387   |    dmz_A     |   10.80.113.0/25   |
|  388   |   piso1_A    |  10.80.113.128/25  |
|  389   |   piso0_A    |   10.80.114.0/26   |
|  390   |    voIP_A    |  10.80.114.64/26   |
|  391   |    wifi_B    |   10.80.114.0/25   |
|  392   |   piso1_B    |  10.80.114.129/26  |
|  393   |   piso0_B    |  10.80.114.193\27  |
|  394   |    voIP_B    |  10.80.114.224/28  |
|  395   |    dmz_B     |   10.80.115.0/28   |
|  396   |    wifi_C    |   10.80.117.0/26   |
|  397   |   piso1_C    |  10.80.117.64/26   |
|  398   |   piso0_C    |  10.80.117.128/26  |
|  399   |    voIP_C    |  10.80.117.224/27  |
|  400   |    dmz_C     |  10.80.117.192/27  |
|  401   |    wifi_D    |   10.80.118.0/25   |
|  402   |   piso1_D    |  10.80.118.128/26  |
|  403   |   piso0_D    |  10.80.118.192/27  |
|  404   |    voIP_D    |  10.80.118.224/28  |
|  405   |    dmz_D     |  10.80.118.240/28  |



# 3. Subtasks assignment #

* 1211148 - T.2.1
* 1221693 - T.2.2
* 1201551 - T.2.3
* 1211016 - T.2.4