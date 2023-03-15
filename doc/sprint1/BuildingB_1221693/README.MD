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

Nº de outlets no piso 0: 47 + x reservado para o Access Point

Nº de outlets no piso 1: 84 + x reservado para o Access Point

### 4. Materiais necessários e inventário ###
_4.1 Número de outlets (tomadas de rede)

Nº de outlets no piso 0: 47 + x reservado para o Access Point

Nº de outlets no piso 1: 84 + x reservado para o Access Point

Total: 131 +  x reservado para o Access Point

_4.2 Comprimemto dos cabos e outros materiais úteis

__Piso 0__

* Fio de cobre Cat6a

Para calcular o comprimento de fio de cobre necessário para os outlets, foi utilizada a seguinte fórmula:

    comprimento total = nº de outlets x comprimento médio + margem de segurança

Para calcular o comprimento de fio de cobre necessário para o access point, foi utilizada a seguinte fórmula:

    comprimento total = altura + comprimento + margem de segurança

    | Divisão | Nº de outlets | Comprimento total aproximado (m) |
    |--------:|:-------------:|:--------------------------------:|
    |   B.0.1 |       4       |                                  |
    |   B.0.2 |       4       |                                  |
    |   B.0.3 |       4       |                                  |
    |   B.0.4 |       4       |                                  |
    |   B.0.5 |       8       |                                  |
    |   B.0.6 |       5       |                                  |
    |   B.0.7 |       5       |                                  |
    |   B.0.8 |       5       |                                  |
    |   B.0.9 |       5       |                                  |
    |   B.0.10|       3       |                                  |

    Total:

* Fibra ótica de modo único

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
    |   B.1.6 |       6       |                                  |
    |   B.1.7 |       6       |                                  |
    |   B.1.8 |       6       |                                  |
    |   B.1.9 |       6       |                                  |
    |   B.1.10|       6       |                                  |
    |   B.1.11|       6       |                                  |
    |   B.1.13|       6       |                                  |
    |   B.1.14|       6       |                                  |
    |   B.1.15|       6       |                                  |

    Total:

* Fibra ótica de modo único