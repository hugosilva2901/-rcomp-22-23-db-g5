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
- Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4): 10.80.116.0/24

| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |      IP       |  Primeiro IP  |   Último IP   |  Máscara de rede  |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|:------------:|:-------------:|:-------------:|:-------------:|:-----------------:|:-------------:|
|  110  |       /25       |    Rede Wi-Fi    |  391   |    wifi_B    |  10.80.116.0  |  10.80.116.1  | 10.80.116.126 |  255.255.255.128  | 10.80.116.127 |
|  60   |       /26       | Outlets (Piso 1) |  392   |   piso1_B    | 10.80.116.128 | 10.80.116.130 | 10.80.116.190 |  255.255.255.192  | 10.80.116.191 |
|  25   |       /27       | Outlets (Piso 0) |  393   |   piso0_B    | 10.80.116.192 | 10.80.116.194 | 10.80.116.222 |  255.255.255.224  | 10.80.116.223 |
|  13   |       /28       |       VoIP       |  394   |    voIP_B    | 10.80.116.224 | 10.80.116.225 | 10.80.116.236 |  255.255.255.240  | 10.80.116.237 |
|  10   |       /28       |       DMZ        |  395   |    dmz_B     | 10.80.116.240 | 10.80.116.241 | 10.80.116.254 |  255.255.255.240  | 10.80.116.255 |

------------------------------------------------------------------------------------------------------------------------------------------------------------
### 2. Cálculo do prefixo de rede ###

Para calcular o prefixo de rede, é necessário saber o endereço IP da rede e a máscara de sub-rede. A máscara de sub-rede é um número que determina o número de bits usados ​​para identificar a rede e o número de bits usados ​​para identificar os hosts em uma rede.
O prefixo de rede é encontrado combinando o endereço IP da rede com a máscara de sub-rede. 
Converta o endereço IP da rede e a máscara de sub-rede em formato binário. 
Combine o endereço IP da rede com a máscara de sub-rede usando o operador "e" (AND) bit a bit. Isso produzirá o endereço de rede. 
Converta o endereço de rede resultante de volta para decimal, se necessário.

### 3. Cálculo das máscaras de rede ###

A máscara de rede foi obtida utilizando o seguinte site: https://www.todoespacoonline.com/w/tuts/2014/11/calc_ipv4/

### 4. Cálculo do Broadcast/Endereço IP ###

Para calcular o endereço de broadcast e o endereço IP final de uma rede, é necessário saber o endereço IP da rede e a máscara de sub-rede. O endereço de broadcast é o endereço de rede para o qual todos os dispositivos na rede enviam mensagens de broadcast. O endereço IP final é o último endereço IP disponível na rede.

Para fazer o cálculo, siga estes passos:
1-Determine o número de bits na máscara de sub-rede.
2-Calcule o número de hosts disponíveis na rede, subtraindo 2 do total de endereços possíveis. Isso ocorre porque o primeiro endereço é reservado para a rede e o último endereço é reservado para o endereço de broadcast. Por exemplo, se houver 24 bits na máscara de sub-rede, há 2^8 (256) endereços possíveis para cada octeto, menos 2 endereços reservados, o que significa que há 254 hosts disponíveis.
3-Encontre o endereço de broadcast somando a negação da máscara de sub-rede ao endereço IP da rede. 
4-Encontre o endereço IP final subtraindo 1 do endereço de broadcast.
