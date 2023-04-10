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

       End user outlets on the ground floor: 40 nodes
       End user outlets on floor one: 50 nodes
       Wi-Fi network: 55 nodes
       DMZ (Servers, administration workstations, and network infrastructure devices): 20 nodes
       VoIP (IP-phones): 25 nodes
        Total Nodes: 190 

       Do enunciado
        Equipa 5:  
            VTP domain name to be used: rc23dbg5
            VLANIDs range to be used: 385 - 415
            IPv4 address space to be used (Block of IPv4 addresses): 10.80.112.0/21
            ISP router IPv4 node address: 121.60.202.50/30

      Do planning:
        Edificio C:
            Assigned IPv4 block: 10.80.117.0/24

    | VLANID | Nome da VLAN | IPv4 Address Block |
    |:------:|:------------:|:------------------:|
    |  396   |    wifi_C    |   10.80.117.0/26   |
    |  397   |   floor1_C    |  10.80.117.64/26   |
    |  398   |   floor0_C    |  10.80.117.128/26  |
    |  399   |    voIP_C    |  10.80.117.224/27  |
    |  400   |    dmz_C     |   10.80.117.192/27   |


    VTP Domain Name: rc23dbg5
    Intervalo de VLANID: 385 - 415
    Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4): 10.80.117.0/24
    Endereço IPv4 do node do ISP router: 121.60.202.50/30
    Endereço IPv4 do node do ISP router(building C): 121.60.202.50/30   10.80.117.0/24 10.80.117.0/24


| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |        IP        |  Primeiro IP  |   Último IP   | Máscara de rede |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|--------------|:----------------:|:-------------:|:-------------:|-----------------|:-------------:|
|  55   |       /26       |   Rede e Wi-Fi   |  396   | wifi_C       |  10.80.117.0/26  |  10.80.117.1  | 10.80.117.62  | 255.255.255.192 | 10.80.117.63  |
|  50   |       /26       | Outlets (Piso 1) |  397   | floor1_C     | 10.80.117.64/26  | 10.80.117.65  | 10.80.117.126 | 255.255.255.192 | 10.80.117.127 |
|  40   |       /26       | Outlets (Piso 0) |  398   | floor0_C     | 10.80.117.128/26 | 10.80.117.129 | 10.80.117.190 | 255.255.255.192 | 10.80.117.191 |
|  25   |       /27       |       VoIP       |  399   | voIP_C       | 10.80.117.224/27 | 10.80.117.225 | 10.80.117.254 | 255.255.255.224 | 10.80.117.255 |
|  20   |       /27       |       DMZ        |  400   | dmz_C        | 10.80.117.192/27 | 10.80.117.193 | 10.80.117.222 | 255.255.255.224 | 10.80.117.223 |

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Cálculo do prefixo de rede ###

O prefixo de rede determina a quantidade de bits usados para identificar a rede e a quantidade de bits usados para identificar os hosts na rede. 
Para calcular o prefixo de rede, é necessário determinar quantas sub-redes são necessárias e quantos hosts serão alocados em cada sub-rede.

No caso do edifício C, temos as seguintes sub-redes:

    Rede e Wi-Fi: 55 nodes
    Outlets (Piso 1): 50 nodes
    Outlets (Piso 0): 40 nodes
    VoIP: 25 nodes
    DMZ: 20 nodes

Temos um total de 190 nodes. 
Conseguimos alocar estes nós com um prefixo de rede /24 (255.255.255.0).
No entanto,iriamos desperdicar muitos enderecos IP, dado que um prefixo /24 permite 254 hosts.

Vamos utilizar a seguinte fórmula, de modo a saber quantos bits são necessários para alocar o número de nodes presente em cada sub-rede:
    
    Número de nós por sub-rede = 2^(número de bits alocados para hosts) - 2
    O valor "2" é subtraído da fórmula de forma a excluir o endereço de rede e o endereço de broadcast, que não podem ser usados como endereços de host.

Usando esta fórmula, podemos determinar o número de bits necessários para alocar o número de nós em cada sub-rede:

    Rede e Wi-Fi: 55 nós -> 6 bits (2^6 - 2 = 62)
    Outlets (Piso 1): 50 nós -> 6 bits (2^6 - 2 = 62)
    Outlets (Piso 0): 40 nós -> 6 bits (2^6 - 2 = 62)
    VoIP: 25 nós -> 5 bits (2^5 - 2 = 30)
    DMZ: 20 nós -> 5 bits (2^5 - 2 = 30)
    Portanto, podemos utilizar um prefixo de rede /26 (255.255.255.192) para alocar a sub-rede Wi-Fi, Floor(0/1) e um prefixo de rede /27 (255.255.255.224) para alocar as sub-redes de VoIP e DMZ.


| VLAN ID |   Nome   | Nodes | IPv4 Address Block | Usable IP Addresses | 
|:-------:|:--------:|:-----:|:------------------:|:-------------------:|
|   396   |  wifi_C  |  55   |   10.80.117.0/26   |         62          | 
|   397   | floor1_C |  50   |  10.80.117.64/26   |         64          | 
|   398   | floor0_C |  40   |  10.80.117.128/26  |         64          | 
|   399   |  voIP_C  |  25   |  10.80.117.224/27  |         30          | 
|   400   |  dmz_C   |  20   |  10.80.117.192/27  |         30          | 


------------------------------------------------------------------------------------------------------------------------------------------------------------
### 3. Cálculo das máscaras de rede ###

As máscaras de rede são calculadas a partir do prefixo de rede definido para cada VLAN. 
Neste caso, todos os prefixos de rede têm um comprimento de 26 bits, exceto as VLANs de VoIP e DMZ, que têm um comprimento de 27 bits.
A máscara de rede é uma sequência de bits que define o tamanho da sub-rede. 
Esta é usada para separar o endereço IP em duas partes: a parte da rede e a parte do host. 
A parte da rede é formada pelos primeiros bits do endereço IP, enquanto a parte do host é formada pelos últimos bits.

Para calcular a máscara de rede, é necessário converter o comprimento do prefixo de rede em binário e preencher com zeros os bits restantes até 32 bits. Em seguida, basta converter essa sequência de bits em decimal e obter a máscara de rede correspondente.

| VLAN ID |   Nome   | IPv4 Address Block |           Prefixo de Rede           | Comprimento do Prefixo | Máscara de Rede | 
|:-------:|:--------:|:------------------:|:-----------------------------------:|:----------------------:|:---------------:|
|   396   |  wifi_C  |   10.80.117.0/26   | 11111111.11111111.11111111.11000000 |           26           | 255.255.255.192 |
|   397   | floor1_C |  10.80.117.64/26   | 11111111.11111111.11111111.11000000 |           26           | 255.255.255.192 |
|   398   | floor0_C |  10.80.117.128/26  | 11111111.11111111.11111111.11000000 |           26           | 255.255.255.192 |
|   399   |  voIP_C  |  10.80.117.224/27  | 11111111.11111111.11111111.11100000 |           27           | 255.255.255.224 |
|   400   |  dmz_C   |  10.80.117.192/27  | 11111111.11111111.11111111.11100000 |           27           | 255.255.255.224 |


------------------------------------------------------------------------------------------------------------------------------------------------------------
### 4. Cálculo do Broadcast/Endereço IP ###

O Broadcast é um endereço especial que permite que um pacote seja enviado para todos os dispositivos numa rede. 
Para calcular o endereço de Broadcast em cada sub-rede, podemos usar duas fórmulas diferentes.

A primeira fórmula é a seguinte: 
    Broadcast = Endereço IP + (2^n - 1), 
    onde n é o número de bits da rede determinado pela máscara de sub-rede.

A segunda fórmula usa operações lógicas com o endereço IP e a máscara de sub-rede: 
    Broadcast = (Endereço IP) OR (NOT Máscara de Sub-Rede). 


|  VlanID  |  Endereço IP  |     Máscara     | Número de bits |   Broadcast   |            Calculo (1a formula)            | 
|:--------:|:-------------:|:---------------:|:--------------:|:-------------:|:------------------------------------------:|
|  wifi_C  |  10.80.117.0  | 255.255.255.192 |       26       | 10.80.117.63  |  10.80.117.0 + (2^26 - 1) = 10.80.117.63   |
| floor1_C | 10.80.117.64  | 255.255.255.192 |       26       | 10.80.117.127 | 10.80.117.64 + (2^26 - 1) = 10.80.117.127  |
| floor0_C | 10.80.117.128 | 255.255.255.192 |       26       | 10.80.117.191 | 10.80.117.128 + (2^26 - 1) = 10.80.117.191 |
|  voIP_C  | 10.80.117.224 | 255.255.255.224 |       27       | 10.80.117.255 | 10.80.117.224 + (2^27 - 1) = 10.80.117.255 |
|  dmz_C   | 10.80.117.192 | 255.255.255.224 |       27       | 10.80.117.223 | 10.80.117.192 + (2^27 - 1) = 10.80.117.223 |


Os dados acima referidos podem ser obtidos/confirmados com recurso a : https://www.todoespacoonline.com/w/tuts/2014/11/calc_ipv4/
