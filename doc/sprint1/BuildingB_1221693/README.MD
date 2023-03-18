+## RCOMP 2022/2023 - SPRINT 1 EDIFÍCIO B - 1221693 ##

===========================================================================
### Introdução: ###tlttlt
Este ficheiro documenta o planeamento e estruturação do Edifício B, que se está dividido em dois pisos.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Regras de cabeamento e visão geral da estruturação do Edifício B**
2. **Medidas e dimensões das divisões**
------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Regras de cabeamento e estruturação geral do Edifício B ###

_1.1 Informação geral_

As especificações que são fornecidas no enunciado deste projeto para o edifício B são as seguintes :

* As dimensões horizontais são de 40 x 20 metros.

__Piso 0__
    *O piso térreo possui uma  vala técnica subterrânea canaleta de cabos sob o piso conectada à vala técnica externa.
    *Acesso a canaleta de cabos sob o piso está disponível em pontos marcados na planta (representados em azul) 
    *A altua do teto neste andar é de 4 metros 
    *As salas B.0.6 e B.0.7 têm um uso especial e as únicas saídas de rede necessárias são ao longo do subsolo canaleta de cabo, cinco saídas em cada sala.
    *A sala B.0.11 é uma área de armazenamento e pode ser usada para abrigar um cross-connect, não são necessárias tomadas de rede.
    *Corredores, casas de banho e átrios não requerem tomadas de rede.
__Piso 1__
    
    *Neste andar não há canaletas de cabos sob o piso
    *A altura deste teto é de 3 metros, no entanto existe um tecto rebaixado amovível, colocado a 2,5 metros do chão, cobrindo todo o andar.O espaço sobre o teto rebaixado é perfeito para instalar pistas de cabos
    *A sala B.1.12 é  é uma área de armazenamento e pode ser usada para abrigar um cross-connect, não são necessárias tomadas de rede, e o mesmo vale para banheiros, salões e corredores.

_1.2 Cabeamento
    *A capacidade de transporte de informação das interligações nos vários níveis deve ser crescente no sentido ascendente. Este requisito deriva directamente da lógica de transacções preferencialmente em sentido ascendente que origina uma concentração de fluxos nos níveis mais elevados por serem usados por um maior número de nós. O aumento da capacidade não significa necessariamente a utilização de um tipo de cabo diferente (fibra óptica), a montagem de cabos em paralelo, passíveis de serem agregadas ("trunking"), produz o mesmo efeito.

    *Por cada 1000 m2 de área bruta deve existir pelo menos um distribuidor de piso (ISO/IEC 11801)

    *O raio de ação do distribuidor de piso ou de zona não deve ultrapassar 80 metros

    *Para cabos de fibra óptica não deve exceder 90 metros na cablagem horizontal (piso e zona), nas interligação de pisos (backbone de edifício) não pode exceder 500 metros e na interligação de edifícios (backbone de campus) não pode exceder 1500 metros.

    
_1.3 Cross-conection

    *No predio B será necessário 1 Intermediate cross-connect (IC), e 2 Horizontal cross-connect (HC).

    *Os distribuidores(IC) é preferível instala-los em zonas técnicas exclusivas para o efeito. Estas zonas são designadas de sala de equipamento (ER - Equipment Room) e compartimento de telecomunicações (TC - Telecommunication Closets), os primeiros de maior dimensão (>15 m2) devem existir no rácio de um por edifício e destinam-se a acomodar o distribuidor de edifício. Os compartimentos de telecomunicações são de menor dimensão (cerca de 5 m2) devendo existir um em cada piso para acomodar o respectivo distribuidor de piso(HC).

_1.4 Número de outlests 
    *Por cada 10 m2 de área devem existir duas tomadas de rede (ISO/IEC 11801). No entanto este número pode alterar dependendo das informações do enunciado.

_1.5 Consolidation Points

    Os Consolidation Points são usados de modo a que novas conexões sejam adicionadas ou reorganizadas com facilidade, sem ter que alterar o cabo  principal (é conectado ao cabo de rede principal, que por sua vez é conectado a um switch ou router).
_1.6 Access points

    Access points (APs) são dispositivos de rede sem fio que permitem que os dispositivos clientes se conectem a uma rede sem fio
    access points não podem ter overlap em dentro do mesmo canal e para podermos ter overlap mos acesse points eles têm de estar ligados a canais diferentes (no predio B vamos ter dois access points o do piso ser no canal 1 e do piso 1 no canal 2). 

_1.7 Link Aggregation
    O LACP é definido pelo 802.3ad, no entanto, estará sujeito a revisões adicionais. Esse é, no entanto, o padrão mais aceito globalmente para links automatizados agregação.
    Cada agregação de link LACP pode ter até oito portas, balanceamento de carga e falha de cabo são suportados. Cada porta LACP deve ser configurada de duas maneiras:
    ATIVO – quando o link é ativado, a porta é usada para enviar LACPDUs para a contraparte, convidando-a a utilizar o LACP e fazer parte da agregação.
    PASSIVO – ativa o LACP somente se um convite for recebido, nenhum convite enviado.
    Para habilitar o LACP por meio de um cabo, uma porta ativa deve ser conectada a um porta passiva ou ativa. Após a negociação inicial, o LACP cria uma agregação de link usando até 8 portas habilitadas para LACP conectadas diretamente entre os dois dispositivos.
_1.8 channels

## 2. Medidas e dimensões das divisões ##

__Piso 0__
| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|
|   B.0.1 |      3.33   |       5,74      |   19.11   |       4       |
|   B.0.2 |      3.33   |       5,74      |   19.11   |       4       |
|   B.0.3 |      3.33   |       5,74      |   19.11   |       4       |
|   B.0.4 |      3.33   |       5,74      |   19.11   |       4       |
|   B.0.5 |      4.81   |       8.52      |    41     |       8       |
|   B.0.6 |      9.63   |       10.93     |   105.26  |       5       |
|   B.0.7 |      9.63   |       10.93     |   105.26  |       5       |
|   B.0.8 |      3.33   |       8.52      |   28.37   |       5       |
|   B.0.9 |      3.33   |       8.52      |   28.37   |       5       |
|   B.0.10|      3.33   |       4.63      |   15.42   |       3       |

__Piso 1__
| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|
|   B.1.1 |    3.89     |       8.89      |   34.58   |       6       |
|   B.1.2 |    3.70     |       8.89      |   32.89   |       6       |
|   B.1.3 |    3.70     |       8.89      |   32.89   |       6       |
|   B.1.4 |    3.70     |       8.89      |   32.89   |       6       |
|   B.1.5 |    3.70     |       8.89      |   32.89   |       6       |
|   B.1.6 |    7.04     |       4.44      |   31.26   |       6       |
|   B.1.7 |    7.04     |       4.44      |   31.26   |       6       |
|   B.1.8 |    7.04     |       4.44      |   31.26   |       6       |
|   B.1.9 |    7.04     |       4.44      |   31.26   |       6       |
|   B.1.10|    7.04     |       4.44      |   31.26   |       6       |
|   B.1.11|    7.04     |       4.26      |   30.00   |       6       |
|   B.1.13|    7.04     |       4.44      |   31.26   |       6       |
|   B.1.14|    7.04     |       4.44      |   31.26   |       6       |
|   B.1.15|    7.04     |       4.44      |   31.26   |       6       |

Nº de outlets no piso 0: 47 + 1 reservado para o Access Point

Nº de outlets no piso 1: 84 + 1 reservado para o Access Point

### 4. Materiais necessários e inventário ###
_4.1 Número de outlets (tomadas de rede)

Nº de outlets no piso 0: 47 + 1 reservado para o Access Point

Nº de outlets no piso 1: 84 + 1 reservado para o Access Point

Total: 131 +  2 reservado para o Access Point

_4.2 Comprimemto dos cabos e outros materiais úteis

__Piso 0__

    Os outlets localizados nas salas B.01 B.02 B.03 B.04 e 4 outlets da sala B.05 stão ligados ao cp localizado na dala B.03 o que significa que estão a ser usados 20 portas de entrada no patch panel localizado nesse cp mais 4 cabos para ligar do cp ao hc de moda a fazer uma link aggregation o que dá um total de 24 cabos de modo a dar espeço para caso escalonamento decidi  deixar 50% livre e por isso precisamos de um patch panel de 48.

    Os outlets localizados nas salas B.05 (restantes 4) B.06 B.07 e 3 outltes localizados na sala B.08 estão ligados ao cp localizado na dala B.06 o que significa que estão a ser usados 18 portas de entrada no patch panel localizado nesse cp mais 4 cabos para ligar do cp ao hc de moda a fazer uma link aggregation o que dá um total de 21 cabos de modo a dar espeço para caso escalonamento decidi  deixar 50% livre e por isso precisamos de um patch panel de 48.
    
    Os outlets localizados nas salas B.10 B.08 (restantes 2) B.09 estão ligadas ao HC o que significa que estão a ser usados 10 portas de entrada no patch panel localizado nesse
    HC. Mais 1 porta para o access point e mais 8 entradas para as 2 link aggreagation dos cps desse piso. o que dá um total de 21.  

* Fio de cobre Cat6a

Para calcular o comprimento de fio de cobre necessário para os outlets, foi utilizada a seguinte fórmula:

    comprimento total = nº de outlets x comprimento médio + margem de segurança

Para calcular o comprimento de fio de cobre necessário para o access point, foi utilizada a seguinte fórmula:

    comprimento total = altura + comprimento + margem de segurança

    | Divisão | Nº de outlets | Comprimento total aproximado (m) |
    |--------:|:-------------:|:--------------------------------:|                                                                       
    |   B.0.1 |       4       |       4 * 8.15 * 1.05 = 34.23    |
    |   B.0.2 |       4       |       4 * 3.52 * 1.05 = 14.78    |
    |   B.0.3 |       4       |       4 * 2.73 * 1.05 = 11.42    |
    |   B.0.4 |       4       |       4 * 6.30 * 1.05 = 26.46    |
    |   B.0.5 |       8       |4*9.44*1.05+4*7.30*1.05=33.9+30.66|
    |   B.0.6 |       5       |       5 * 6.03 * 1.05 = 31.66    |
    |   B.0.7 |       5       |      5 * 11.23 * 1.05 = 58.96    |
    |   B.0.8 |       5 + 1   |3*26.4*1.05+2*8.59*1.05=65.2+18.04|
    |   B.0.9 |       5       |       5 * 5.19 * 1.05 = 27.25    |
    |   B.0.10|       3       |       3 * 6.72 * 1.05 = 21.17    |

    Total: 373.73

    1 Access Point:   
    -> 15.2 m

    2 Consolidation Points:   
    -> 4 * 35 = 140 m (uso de 4 cabos para link Aggregation)
    -> 4 * 66.85 = 267.4 m    
__Piso 1__

* Fio de cobre Cat6a

Para calcular o comprimento de fio de cobre necessário para os outlets, foi utilizada a seguinte fórmula:

    comprimento total = nº de outlets x comprimento médio + margem de segurança

Para calcular o comprimento de fio de cobre necessário para o access point, foi utilizada a seguinte fórmula:

    comprimento total = altura + comprimento + margem de segurança

    | Divisão | Nº de outlets | Comprimento total aproximado (m) |
    |--------:|:-------------:|:--------------------------------:|
    |   B.1.1 |       6       |                                  |
    |   B.1.2 |       6       |                                  |
    |   B.1.3 |       6       |                                  |
    |   B.1.4 |       6       |                                  |
    |   B.1.5 |       6       |                                  |
    |   B.1.6 |       6 + 1   |                                  |
    |   B.1.7 |       6       |                                  |
    |   B.1.8 |       6       |                                  |
    |   B.1.9 |       6       |                                  |
    |   B.1.10|       6       |                                  |
    |   B.1.11|       6       |                                  |
    |   B.1.13|       6       |                                  |
    |   B.1.14|       6       |                                  |
    |   B.1.15|       6       |                                  |

    Total:

     1 Access Point:   
    -> 35 m

    2 Consolidation Points:   
    -> 4 *    (uso de 4 cabos para link Aggregation)
    -> 4 * 
* Fibra ótica de modo único

Ligações entre o IC e os HC's (2):   
-> 4 * 1 = 4 m   
-> 4 * 5 = 20 m (para o piso superior)



    4.3 Inventário 
|            | Fio de cobre Cat6a (m) | Fio de fibra ótica modo único (m) | Outlets | Access Points | Patch Panels |
|------------|:----------------------:|:---------------------------------:|:-------:|:-------------:|:------------:|
| **Piso 0** |         781.13         |               x               |   48    |       1       |      8       |
| **Piso 1** |         882.17         |              297.57               |   66    |       1       |      6       |
| **Total**  |        1627.92         |              652.37               |   133   |       2       |      14      |  

**No caso dos patch pannels...**
* O IC tem patch panel de 48 portas.
* Os HC's têm patch panels de 48 portas.
* Os CP's têm patch panels de 48 portas.

**No caso das estruturas de suporte (armários)**
* 6 armários de 8U para todos os CP's + 1 armário de 8U para o IC e + 1  HC armário de 8U do piso 0
* 1 armário de 8U para o HC do piso 1.