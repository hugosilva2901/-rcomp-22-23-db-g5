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

| Nodes | Prefixo de rede |   Dispositivos   | VLANID | Nome da VLAN |     IP      | Primeiro IP | Último IP | Máscara de rede | Broadcast |
|:-----:|:---------------:|:----------------:|:------:|--------------|:-----------:|:-----------:|:---------:|-----------------|:---------:|
|  40   |       /26       | Outlets (Piso 0) |  385   |              | 10.80.112.0 |             |           |                 |           |
|  70   |       /25       | Outlets (Piso 1) |  386   |              |             |             |           |                 |           |
|  100  |       /25       |    Rede Wi-Fi    |  387   |              |             |             |           |                 |           |
|  90   |       /25       |       DMZ        |  388   |              |             |             |           |                 |           |
|  35   |       /26       |       VoIP       |  389   |              |             |             |           |                 |           |
|  100  |       /25       |     Backbone     |  390   |              |             |             |           |                 |           |

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
quantos bits são reservados para a parte de host num endereço IP.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 4. Cálculo dos Broadcast/endereço IP ###

O endereço de broadcast é um endereço IP especial que é usado para enviar pacotes de dados para todos os dispositivos numa rede local (LAN). Para calcular 
o endereço de broadcast numa rede, é necessário conhecer a faixa de endereços IP e a máscara de sub-rede usada.

A fórmula para calcular o endereço de broadcast é a seguinte:

Endereço de broadcast = Endereço de rede OR (NOT Máscara de sub-rede)

Para aplicar aquelas operaçôes binárias com os endereços, é necessário converter os endereços IP para binário.
O endereço broadcast será o resultado, em decimal, da operação feita com os endereços em binário.

===========================================================================