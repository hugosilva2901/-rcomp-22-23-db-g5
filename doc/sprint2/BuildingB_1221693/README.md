## RCOMP 2022/2023 - SPRINT 2 EDIFÍCIO B - 1221639 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta a simulaçôes do edifício B.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Informação inicial do Edifício B**
2. **Cálculo do prefixo de rede**
3. **Cálculo das máscaras de rede**
4. **Cálculo dos Broadcast/endereço IP**


### 1. Informação inicial do Edifício B###

      - End user outlets on the ground floor: 25 nodes
      - End user outlets on floor one: 60 nodes
      - Wi-Fi network: 110 nodes
      - DMZ (Servers, administration workstations, and network infrastructure devices): 10 nodes
      - VoIP (IP-phones): 13 nodes

- VTP Domain Name: rc23dbg5
- Intervalo de VLANID: 385 - 415
- Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4):
- Endereço IPv4 do node do ISP router:


| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |      IP       |  Primeiro IP  |   Último IP   | Máscara de rede |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|--------------|:-------------:|:-------------:|:-------------:|-----------------|:-------------:|
|  110  |       /25       |    Red e Wi-Fi   |  391   | wife_B       |               |               |               |                 |               |
|  60   |       /25       | Outlets (Piso 1) |  392   | piso1_A      |               |               |               |                 |               |
|  25   |       /26       | Outlets (Piso 0) |  393   | piso0_A      |               |               |               |                 |               |
|  13   |       /26       |       VoIP       |  394   | voIP_A       |               |               |               |                 |               |
|  10   |       /25       |       DMZ        |  395   | dmz_B        |               |               |               |                 |               |

------------------------------------------------------------------------------------------------------------------------------------------------------------
