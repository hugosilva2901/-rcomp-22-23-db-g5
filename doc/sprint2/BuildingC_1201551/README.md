## RCOMP 2022/2023 - SPRINT 2 EDIFÍCIO C - 1201551 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta a simulaçôes do edifício C.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Informação inicial do Edifício C**
2. **Cálculo do prefixo de rede**
3. **Cálculo das máscaras de rede**
4. **Cálculo dos Broadcast/endereço IP**


### 1. Informação inicial do Edifício C###

      - End user outlets on the ground floor: 40 nodes
      - End user outlets on floor one: 50 nodes
      - Wi-Fi network: 55 nodes
      - DMZ (Servers, administration workstations, and network infrastructure devices): 20 nodes
      - VoIP (IP-phones): 25 nodes
        -Total Nodes: 190 

      - Do enunciado
        -Equipa 5:  
            VTP domain name to be used: rc23dbg5
            VLANIDs range to be used: 385 - 415
            IPv4 address space to be used (Block of IPv4 addresses): 10.80.112.0/21
            ISP router IPv4 node address: 121.60.202.50/30

      - Do planning:
        - Edificio C:
            Assigned IPv4 block: 10.80.117.0/24

    -| VLANID | Nome da VLAN | IPv4 Address Block |
    -|:------:|:------------:|:------------------:|
    -|  396   |    wifi_C    |   10.80.117.0/26   |
    -|  397   |   floor1_C    |  10.80.117.64/26   |
    -|  398   |   floor0_C    |  10.80.117.128/26  |
    -|  399   |    voIP_C    |  10.80.117.224/27  |
    -|  400   |    dmz_C     |   10.80.117.192/27   |


- VTP Domain Name: rc23dbg5
- Intervalo de VLANID: 385 - 415
- Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4): 10.80.117.0/24
- Endereço IPv4 do node do ISP router: 121.60.202.50/30
- Endereço IPv4 do node do ISP router(building C): 121.60.202.50/30   10.80.117.0/24 10.80.117.0/24


| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |       IP       | Primeiro IP |  Último IP   | Máscara de rede |  Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|--------------|:--------------:|:-----------:|:------------:|-----------------|:------------:|
|  55   |       /26       |   Rede e Wi-Fi   |  396   | wifi_C       | 10.80.117.1/26 | 10.80.117.1 | 10.80.117.62 | 255.255.255.192 | 10.80.117.63 |
|  50   |       /26       | Outlets (Piso 1) |  397   | floor1_C     |                |             |              |                 |              |
|  40   |       /26       | Outlets (Piso 0) |  398   | floor0_C     |                |             |              |                 |              |
|  25   |       /27       |       VoIP       |  399   | voIP_C       |                |             |              |                 |              |
|  20   |       /27       |       DMZ        |  400   | dmz_C        |                |             |              |                 |              |

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Cálculo do prefixo de rede ###

- End user outlets on the ground floor: 40 nodes
    - VLAN ID: 398 (floor0_C)
    - IPv4 Address Block: 10.80.117.128/26 (64 usable IP addresses)
- End user outlets on floor one: 50 nodes
    - VLAN ID: 397 (floor1_C)
    - IPv4 Address Block: 10.80.117.64/26 (64 usable IP addresses)
- Wi-Fi network: 55 nodes
    - VLAN ID: 396 (wifi_C)
    - IPv4 Address Block: 10.80.117.0/26 (62 usable IP addresses)
- DMZ (Servers, administration workstations, and network infrastructure devices): 20 nodes
    - VLAN ID: 400 (dmz_C)
    - IPv4 Address Block: 10.80.117.192/27 (30 usable IP addresses)
- VoIP (IP-phones): 25 nodes
    - VLAN ID: 399 (voIP_C)
    - IPv4 Address Block: 10.80.117.224/27 (30 usable IP addresses)

------------------------------------------------------------------------------------------------------------------------------------------------------------
