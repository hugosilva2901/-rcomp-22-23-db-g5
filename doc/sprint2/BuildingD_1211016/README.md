## RCOMP 2022/2023 - SPRINT 2 EDIFÍCIO D - 1211016 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta a simulação em Cisco Packet Tracer do edifício D

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Informação inicial do Edifício D**
2. **Cálculo de IP's e máscaras de rede**
4. **Cálculo do Broadcast/Endereço IP**
5. **Decisões de design**

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Informação inicial do Edifício D ###

      - End user outlets on the ground floor: 25 nodes
      - End user outlets on floor one: 60 nodes
      - Wi-Fi network: 80 nodes
      - DMZ (Servers, administration workstations, and network infrastructure devices): 10 nodes
      - VoIP (IP-phones): 13 nodes

- VTP Domain Name: rc23dbg5
- Intervalo de VLANID (edifício D): 401 - 405
- Espaço de endereço IPv4 a ser usado (edifício D): 10.80.116.0/24


| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |      IP       |  Primeiro IP  |   Último IP   | Máscara de rede |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|:------------:|:-------------:|:-------------:|:-------------:|:---------------:|:-------------:|
|  80   |       /25       |    Rede Wi-Fi    |  401   |    wifi_D    |  10.80.118.0  |  10.80.118.1  | 10.80.118.126 | 255.255.255.128 | 10.80.118.127 |
|  60   |       /26       | Outlets (Piso 1) |  402   |   piso1_D    | 10.80.118.128 | 10.80.118.129 | 10.80.118.190 | 255.255.255.192 | 10.80.118.191 |
|  25   |       /27       | Outlets (Piso 0) |  403   |   piso0_D    | 10.80.118.192 | 10.80.118.193 | 10.80.118.222 | 255.255.255.224 | 10.80.118.223 |
|  13   |       /28       |       VoIP       |  404   |    voIP_D    | 10.80.118.224 | 10.80.118.225 | 10.80.118.238 | 255.255.255.240 | 10.80.118.239 |
|  10   |       /28       |       DMZ        |  405   |    dmz_D     | 10.80.118.240 | 10.80.118.241 | 10.80.118.254 | 255.255.255.240 | 10.80.118.255 |

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Cálculo de IP's e máscaras de rede ###

As VLAN's no edifício D funcionam como networks diferentes, cada uma com um endereço IP diferente.
A partir do endereço base deste edifício (10.80.118.0/24), foi possível calcular os endereços IP de cada VLAN, utilizando a máscara de rede adequada ao número de nodes que 
cada VLAN tem.

Assim, a primeira VLAN fica com um bloco de 128 IPs, a segunda com 64 IPs, a terceira com 32 IPs, a quarta com 16 IPs e a quinta com 16 IPs.

Isto traduz-se em:
*  10.80.118.0/25 - Rede Wi-Fi
*  10.80.118.128/26 - Outlets (Piso 1)
*  10.80.118.192/27 - Outlets (Piso 0)
*  10.80.118.224/28 - VoIP
*  10.80.118.240/28 - DMZ

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 4. Cálculo do Broadcast/Endereço IP ###

* Endereço IP: O endereço IP é o primeiro IP de cada rede, ou seja, o primeiro IP de cada bloco de IPs que foi atribuído a cada VLAN. Este IP identifica a rede.


     * Primeiro IP utilizável = Endereço IP + 1


* Broadcast IP: O endereço IP de broadcast é o último IP de cada rede, ou seja, o último IP de cada bloco de IPs que foi atribuído a cada VLAN.
* Broadcast IP = Endereço IP + 2^(32 - Número de bits da máscara de rede) - 1


    * Último IP utilizável: Broadcast IP - 1
------------------------------------------------------------------------------------------------------------------------------------------------------------

### 5. Decisões de design ###

 #### 5.1. VTP ####

* Infelizmente, ao usar VTP na simulação, a base de dados de VLANS não se propagou entre os switches, de qualquer forma, a configuração de VTP foi mantida:
    * VTP Domain Name: rc23dbg5
    * VTP Mode: Server no switch do ICC do edifício D
    * VTP Mode: Client nos switches restantes do edifício D
    * Ligações entre switches: Trunk

 #### 5.2. Default Gateways ####

* A default gateway do edifício D é o router do ICC, com o IP: 10.80.118.241