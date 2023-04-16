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


### 1. Informação inicial do Edifício C ###

    End user outlets on the ground floor: 40 nodes
    End user outlets on floor one: 50 nodes
    Wi-Fi network: 55 nodes
    DMZ (Servers, administration workstations, and network infrastructure devices): 20 nodes
    VoIP (IP-phones): 25 nodes
    Total Nodes: 190 

Informação retirada do enunciado:
    
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
    |  399   |    voIP_C    |  10.80.117.192/27  |
    |  400   |    dmz_C     |   10.80.117.224/27   |



   * VTP Domain Name: rc23dbg5
   * Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4): 10.80.117.0/24


| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |        IP        |  Primeiro IP  |   Último IP   | Máscara de rede |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|--------------|:----------------:|:-------------:|:-------------:|-----------------|:-------------:|
|  55   |       /26       |   Rede e Wi-Fi   |  396   | wifi_C       |  10.80.117.0/26  |  10.80.117.1  | 10.80.117.62  | 255.255.255.192 | 10.80.117.63  |
|  50   |       /26       | Outlets (Piso 1) |  397   | floor1_C     | 10.80.117.64/26  | 10.80.117.65  | 10.80.117.126 | 255.255.255.192 | 10.80.117.127 |
|  40   |       /26       | Outlets (Piso 0) |  398   | floor0_C     | 10.80.117.128/26 | 10.80.117.129 | 10.80.117.190 | 255.255.255.192 | 10.80.117.191 |
|  25   |       /27       |       VoIP       |  399   | voIP_C       | 10.80.117.192/27 | 10.80.117.193 | 10.80.117.222 | 255.255.255.224 | 10.80.117.223 |
|  20   |       /27       |       DMZ        |  400   | dmz_C        | 10.80.117.224/27 | 10.80.117.225 | 10.80.117.254 | 255.255.255.224 | 10.80.117.255 |

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

Um valor de "/26" representa uma máscara de rede com 26 bits "1" consecutivos à esquerda, o que corresponde a 64 endereços IP únicos. 
Já um valor de "/27" representa uma máscara de rede com 27 bits "1" consecutivos à esquerda, o que corresponde a 32 endereços IP únicos
Com isto, para as sub-redes wifi_C, floor1_C e floor0_C, é necessário um prefixo de rede de "/26" uma vez que possui 62 endereços IP usáveis. 
Para as sub-redes voIP_C e dmz_C, utilizamos um prefixo de rede de "/27" visto que possui 30 endereços IP usáveis.
Apesar de possuirem 64 e 32 endereços de ip únicos, respectivamente, dois endereços são reservados para o identificador da rede e o endereço de broadcast.


| VLAN ID |   Nome   | Nodes | IPv4 Address Block | Usable IP Addresses | 
|:-------:|:--------:|:-----:|:------------------:|:-------------------:|
|   396   |  wifi_C  |  55   |   10.80.117.0/26   |         62          | 
|   397   | floor1_C |  50   |  10.80.117.64/26   |         62          | 
|   398   | floor0_C |  40   |  10.80.117.128/26  |         62          | 
|   399   |  voIP_C  |  25   |  10.80.117.192/27  |         30          | 
|   400   |  dmz_C   |  20   |  10.80.117.224/27  |         30          | 


------------------------------------------------------------------------------------------------------------------------------------------------------------
### 3. Cálculo das máscaras de rede ###

As máscaras de rede são calculadas a partir do prefixo de rede definido para cada VLAN. 
Neste caso, todos os prefixos de rede têm um comprimento de 26 bits, exceto as VLANs de VoIP e DMZ, que têm um comprimento de 27 bits.
A máscara de rede é uma sequência de bits que define o tamanho da sub-rede. 
Esta é usada para separar o endereço IP em duas partes: a parte da rede e a parte do host. 
A parte da rede é formada pelos primeiros bits do endereço IP, enquanto a parte do host é formada pelos últimos bits.

Para calcular a máscara de rede, é necessário converter o comprimento do prefixo de rede em binário e preencher com zeros os bits restantes até 32 bits. 
Em seguida, basta converter essa sequência de bits em decimal e obter a máscara de rede correspondente.

| VLAN ID |   Nome   | IPv4 Address Block |           Prefixo de Rede           | Comprimento do Prefixo | Máscara de Rede | 
|:-------:|:--------:|:------------------:|:-----------------------------------:|:----------------------:|:---------------:|
|   396   |  wifi_C  |   10.80.117.0/26   | 11111111.11111111.11111111.11000000 |           26           | 255.255.255.192 |
|   397   | floor1_C |  10.80.117.64/26   | 11111111.11111111.11111111.11000000 |           26           | 255.255.255.192 |
|   398   | floor0_C |  10.80.117.128/26  | 11111111.11111111.11111111.11000000 |           26           | 255.255.255.192 |
|   399   |  voIP_C  |  10.80.117.192/27  | 11111111.11111111.11111111.11100000 |           27           | 255.255.255.224 |
|   400   |  dmz_C   |  10.80.117.224/27  | 11111111.11111111.11111111.11100000 |           27           | 255.255.255.224 |


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
|  voIP_C  | 10.80.117.192 | 255.255.255.224 |       27       | 10.80.117.223 | 10.80.117.192 + (2^27 - 1) = 10.80.117.223 |
|  dmz_C   | 10.80.117.224 | 255.255.255.224 |       27       | 10.80.117.255 | 10.80.117.224 + (2^27 - 1) = 10.80.117.255 |


Os dados acima referidos podem ser obtidos/confirmados com recurso a : https://www.todoespacoonline.com/w/tuts/2014/11/calc_ipv4/

------------------------------------------------------------------------------------------------------------------------------------------------------------
### 5. Tabelas de roteamento ###

Uma tabela de roteamento é uma lista de destinos de rede e os próximos saltos associados a cada destino. Cada entrada na tabela de roteamento contém
informações sobre a rede de destino (geralmente representada como um prefixo de rede ou um endereço de rede), a interface de saída (ou interface de rede) e,
em alguns casos, a métrica ou custo associado a essa rota.

* Tabela de roteamento do router C_F0_HCC:

| Network       | Máscara de rede | Next-Hop      |
|---------------|-----------------|---------------|
| 10.80.112.0   | 255.255.255.0   | 10.80.112.4   |
| 10.80.116.0   | 255.255.255.0   | 10.80.112.2   |
| 10.80.118.0   | 255.255.255.0   | 10.80.112.1   |
| 0.0.0.0       | 0.0.0.0         | 121.60.202.50 |

* O router do edifício C contém na ‘interface’ Fa0/0 o endereço IP de todas as VLANS através de encapsulamento de subinterfaces, podendo assim enviar tráfego para todas as VLANS dentro do edifício C.





