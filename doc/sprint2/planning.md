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

* Packet Tracer version : 8.2.1
* VTP Domain name : rc23dbg5
* VLANID Range : 385 - 415
* IPV4 Address Block : 10.80.112.0/21
* ISP router IPv4 node address : 121.60.202.50/30

* Devices nomenclature : <building\>\_<floor\>\_<device-type\>


| VLANID | Nome da VLAN | IPv4 Address Block |
|:------:|:------------:|:------------------:|
|  385   |   backbone   |   10.80.112.0/25   |
|  386   |    wifi_A    |  10.80.112.128/25  |
|  387   |    dmz_A     |   10.80.113.0/25   |
|  388   |   piso1_A    |  10.80.113.128/25  |
|  389   |   piso0_A    |   10.80.114.0/26   |
|  390   |    voIP_A    |  10.80.114.64/26   |
|  391   |    wifi_B    |                    |
|  392   |    dmz_B     |                    |
|  393   |   piso1_B    |                    |
|  394   |   piso0_B    |                    |
|  395   |    voIP_B    |                    |
|  396   |    wifi_C    |                    |
|  397   |    dmz_C     |                    |
|  398   |   piso1_C    |                    |
|  399   |   piso0_C    |                    |
|  400   |    voIP_C    |                    |
|  401   |    wifi_D    |                    |
|  402   |    dmz_D     |                    |
|  403   |   piso1_D    |                    |
|  404   |   piso0_D    |                    |
|  405   |    voIP_D    |                    |



# 3. Subtasks assignment #

* 1211148 - T.2.1
* 1221693 - T.2.2
* 1201551 - T.2.3
* 1211016 - T.2.4