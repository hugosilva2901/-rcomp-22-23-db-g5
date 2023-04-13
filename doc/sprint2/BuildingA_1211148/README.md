## RCOMP 2022/2023 - SPRINT 2 EDIFÍCIO A - 1211148 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta a simulaçôes do edifício A, do campus backbone e da
junção de todas as simulações no Packet Tracer.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Informação inicial do Edifício A e Backbone**
2. **Cálculo do prefixo de rede**
3. **Cálculo das máscaras de rede**
4. **Cálculo dos Broadcast/endereço IP**
5. **Tabelas de roteamento**

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Informação inicial do Edifício A e Backbone ###

      - End user outlets on the ground floor: 40 nodes
      - End user outlets on floor one: 70 nodes
      - Wi-Fi network: 100 nodes
      - DMZ (Servers, administration workstations, and network infrastructure devices): 90 nodes
      - VoIP (IP-phones): 35 nodes
      - Backbone: 100 nodes

- VTP Domain Name: rc23dbg5
- Intervalo de VLANID: 385 - 415
- Espaço de endereço IPv4 a ser usado (Bloco de endereços IPv4): 10.80.112.0/21
- Endereço IPv4 do node do ISP router: 121.60.202.50/30

| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |      IP       |  Primeiro IP  |   Último IP   | Máscara de rede |   Broadcast   |
|:-----:|:---------------:|:----------------:|:------:|:------------:|:-------------:|:-------------:|:-------------:|-----------------|:-------------:|
|  100  |       /25       |     Backbone     |  385   |   backbone   |  10.80.112.0  |  10.80.112.1  | 10.80.112.126 | 255.255.255.128 | 10.80.112.127 |
|  100  |       /25       |    Rede Wi-Fi    |  386   |    wife_A    | 10.80.112.128 | 10.80.112.129 | 10.80.112.254 | 255.255.255.128 | 10.80.112.255 |
|  90   |       /25       |       DMZ        |  387   |    dmz_A     |  10.80.113.0  |  10.80.113.1  | 10.80.113.126 | 255.255.255.128 | 10.80.113.127 |
|  70   |       /25       | Outlets (Piso 1) |  388   |   piso1_A    | 10.80.113.128 | 10.80.113.129 | 10.80.113.254 | 255.255.255.128 | 10.80.113.255 |
|  40   |       /26       | Outlets (Piso 0) |  389   |   piso0_A    |  10.80.114.0  |  10.80.114.1  | 10.80.114.63  | 255.255.255.192 | 10.80.114.63  |
|  35   |       /26       |       VoIP       |  390   |    voIP_A    | 10.80.114.64  | 10.80.114.65  | 10.80.114.126 | 255.255.255.192 | 10.80.114.127 |

* Endereço IPv4 do node do ISP router:

IP: 121.60.202.48
Primeiro IP: 121.60.202.49
Endereço Broadcast (último endereço): 121.60.202.51
Máscara de rede: 255.255.255.252

(/30 corresponde a 2 endereços IP disponíveis)

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Cálculo do prefixo de rede ###

Por exemplo, um valor de "/25" representa uma máscara de rede com 25 bits "1" consecutivos à esquerda, o que corresponde a 128 endereços IP únicos. Um valor
de "/26" representa uma máscara de rede com 26 bits "1" consecutivos à esquerda, o que corresponde a 64 endereços IP únicos. Dado que para os IP-phones e
para os outlets do piso 0 são necessários 35 e 40 endereços IP (nodes), respetivamente, o prefixo de rede será 26 bits. Para os restantes dispositivos 
(outlets do piso 1, rede Wi-Fi, DMZ e backbone) o prefixo de rede será 25 bits.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 3. Cálculo das máscaras de rede ###

A máscara de rede, também conhecida como máscara de sub-rede, é um valor numérico usado para determinar a porção de rede de um endereço IP. Ela é usada em
conjunto com um endereço IP para dividir uma rede em sub-redes menores. A máscara de sub-rede determina quantos bits são reservados para a parte de rede e
quantos bits são reservados para a parte de host num endereço IP. A máscara de rede é geralmente fornecida pelo administrador de rede ou pode ser especificada 
em configurações ou dispositivos de rede, como routers ou switches. 

A máscara de rede foi obtida utilizando o seguinte site: https://www.todoespacoonline.com/w/tuts/2014/11/calc_ipv4/

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 4. Cálculo do Broadcast/Endereço IP ###

O endereço de broadcast é um endereço IP especial usado para enviar pacotes de dados para todos os dispositivos numa rede local (LAN). Para calcular o 
endereço de broadcast numa rede, é necessário conhecer a faixa de endereços IP e a máscara de sub-rede usada.

A fórmula para calcular o endereço de broadcast é a seguinte:

Endereço de broadcast = Endereço de rede OR (NOT Máscara de sub-rede)

Para aplicar aquelas operaçôes binárias com os endereços, é necessário converter os endereços IP para binário. O endereço broadcast será o resultado, 
em decimal, da operação feita com os endereços em binário.

Segue-se um exemplo:

Endereço IP: 10.80.112.0
Máscara de sub-rede: 255.255.255.128

Passo 1: Converter para binário

Endereço IP: 00001010.01010000.01110000.00000000
Máscara de sub-rede: 11111111.11111111.11111111.10000000

Passo 2: Aplicar a operação de "OU" bit a bit

00001010.01010000.01110000.00000000 (Endereço IP)
11111111.11111111.11111111.10000000 (Negação da Máscara de Sub-rede)
00001010.01010000.01110000.10000000 (Resultado)

Passo 3: Converter de volta para notação decimal com pontos

O resultado obtido em binário é 00001010.01010000.01110000.10000000. Convertendo esse resultado de volta para notação decimal com pontos, temos:

Endereço de Broadcast: 10.80.112.127

===========================================================================