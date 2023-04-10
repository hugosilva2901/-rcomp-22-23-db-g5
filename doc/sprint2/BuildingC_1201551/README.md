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


### 1. Informação inicial do Edifício B###

      - End user outlets on the ground floor: x nodes
      - End user outlets on floor one: x nodes
      - Wi-Fi network: x nodes
      - DMZ (Servers, administration workstations, and network infrastructure devices): x nodes
      - VoIP (IP-phones): x nodes

- VTP Domain Name: rc23dbg5
- Intervalo de VLANID: 385 - 415
- Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4):
- Endereço IPv4 do node do ISP router:


| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |      IP       |  Primeiro IP  |   Último IP   | Máscara de rede |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|--------------|:-------------:|:-------------:|:-------------:|-----------------|:-------------:|
|   x   |        x        |   Rede e Wi-Fi   |  391   | wifi_C       |               |               |               |                 |               |
|   x   |        x        | Outlets (Piso 1) |  392   | floor1_C     |               |               |               |                 |               |
|   x   |        x        | Outlets (Piso 0) |  393   | floor0_C     |               |               |               |                 |               |
|   x   |        x        |       VoIP       |  394   | voIP_C       |               |               |               |                 |               |
|   x   |        x        |       DMZ        |  395   | dmz_C        |               |               |               |                 |               |

------------------------------------------------------------------------------------------------------------------------------------------------------------
