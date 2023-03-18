## RCOMP 2022/2023 - SPRINT 1 EDIFÍCIO A - 1211148 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta o planeamento e estruturação do Edifício A, que
está dividido em dois pisos.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Regras de cabeamento e visão geral da estruturação do Edifício A**
2. **Medidas e dimensões das divisões**
3. **Cabeamento e instalação dos dispositivos**
4. **Materiais necessários**
5. **Hardware total necessário (inventário)**

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Regras de cabeamento e estruturação geral do Edifício A ###

_1.1 Informação geral_

Seguem-se algumas especificações deste edifício presentes no enunciado deste projeto:

* As dimensões horizontais são de, aproximadamente, 20 x 20 metros.

* Uma vala técnica subterrânea com canaletas de cabos (representado em azul) existe e inclui passagens de cabos para cada edifício, e está pronto para
  cabeamento de telecomunicações e outros.

* Este edifício alberga o **DataCenter (sala A.1.4)**, albergará também o **cross-connect principal** para o sistema de cabeamento estruturado. Ambos os
  andares devem ter cobertura **LAN sem fio (Wi-Fi)**.

* O piso 0 possui uma canaleta de cabos sob o piso conectada à vala técnica externa. Acesso à canaleta de cabos sob o piso está disponível nos pontos
  marcados na planta na imagem abaixo. Além disso, cabo passagens para o andar acima estão disponíveis.

* A altura do teto no piso 0 é de 4 metros. Áreas comuns, como o hall de entrada, WC's e escadas, não requerem tomadas de rede.

* A altura do teto do piso 1 é de 3 metros, no entanto, existe um teto amovível, colocado a 2,5 metros do chão, cobrindo todo o andar. O espaço sobre o
  teto é perfeito para instalar canaletas de cabos e pontos de acesso sem fio. Este andar não possui canaletas de cabos subterrâneos.


                                                              Planta do piso 0 (presente no enunciado):


![BuildingA_Floor0](BuildingA_Floor0.PNG)

                                                              Planta do piso 1 (presente no enunciado):

![BuildingA_Floor1](BuildingA_Floor1.PNG)

_1.2 Número de outlets (tomadas de rede)_

Generalizando, um espaço de escritório padrão pode exigir aproximadamente uma tomada de rede a cada 10 a 15 metros quadrados, enquanto um espaço residencial
pode exigir uma tomada de rede a cada 20 a 30 metros quadrados. No entanto, dadas as condições exigidas pelo enunciado, vamos considerar que serão necessárias
**2 tomadas de rede por cada 10 metros quadrados**.

_1.3 Cabeamento_

Ambos os padrões de cabeamento **568A** e **568B** para redes Ethernet podem ser usados com vários tipos de cabos de cobre, incluindo cabos de Categoria 5e
(Cat5e), Categoria 6 (Cat6) e Categoria 6a (Cat6a). O cabo *Cat6a* fornece um **desempenho bastante alto** e pode suportar **taxas de transferência de dados
de até 10 GB/s** em distâncias de **até 100 metros**. É recomendado para aplicações de alto desempenho que exigem **conectividade confiável** e de **alta
velocidade** em distâncias maiores.

**Cat7** é um tipo de cabo de cobre projetado para suportar a **rede Ethernet de alta velocidade a taxas de transferência de dados** ainda mais altas e em
distâncias maiores do que o Cat6a. É um cabo **totalmente blindado** (STP), proporcionando **melhor resistência ao ruído e interferência** do que cabos
não blindados como o Cat5e e o Cat6.

No entanto, é importante realçar que o Cat7 **não é um padrão oficialmente reconhecido pela Telecommunications Industry Association (TIA) ou pela International
Organization for Standardization (ISO)**. Embora esteja amplamente disponível, a sua **compatibilidade com outros equipamentos de rede e sua prova futura não são
garantidos**. Como resultado, o Cat6a é frequentemente a escolha preferida para instalações Ethernet de alto desempenho, e vai ser também utilizado no cabeamento
deste edifício.

Como fios de fibra vão ser utilizados **cabos de fibra ótica de modo único**, também conhecidos como monomodo. São projetados para **transmitir sinais de luz num
único caminho**. Eles são feitos com um **núcleo menor e mais denso** do que os cabos de modo múltiplo, permitindo que os **sinais de luz sejam transmitidos em
distâncias maiores com menos atenuação de sinal**. As únicas desvantagens destes cabos são **o custo**, sendo mais elevado do que os cabos de modo múltiplo, e a
**menor resistência a danos físicos**. Isto foi escolhido de modo a não ser preciso o uso de Link Aggregation pois os **cabos de fibra ótica de modo único** são
mais eficientes.

_1.4 Cross-conection_

Os cross-connects são normalmente instalados em **DataCenters**, centrais telefónicas e outras instalações de telecomunicações. Eles fornecem uma maneira eficiente
de gerenciar e organizar as conexões entre vários componentes de rede, como switches, routers e servidores. Nesta planta existem um **MC (Main Cross-Connect)**, um
**IC (Intermediate Cross-Connect)** e dois **HC's (Horizontal Cross-Connect)** (para minimizar o comprimento dos cabos). Podemos estimar que **a área total abrangida
pelo HC não deve exceder os 1000 m2** e que **a distância máxima entre uma tomada de rede e um HC** deve ser de, aproximadamente, **80 metros**. Relativamente às 
**distâncias entre os cross-connects**, cada uma não deve exceder os **500 metros**. No piso 1 os três cross-connects estão localizados no mesmo bastidor.

_1.5 Access Points_

**Access points (APs)** são dispositivos de rede sem fio que **permitem que os dispositivos clientes se conectem a uma rede sem fio**. Os access points são usados
em redes sem fio para **estender a cobertura da rede e fornecer conectividade sem fio em áreas onde o sinal do router ou do switch não alcança**. Eles são normalmente
conectados a um switch ou router de rede com fio para fornecer uma conexão de rede sem fio. Um access point tem uma cobertura de cerca de **50 metros de diâmetro**.
O número de APs necessários dependerá do número de acessos, pois cada AP apenas consegue suportar cerca de 30 acessos.

A frequência de access points varia conforme o padrão de rede sem fio que está a ser utilizado. A escolha da frequência depende de vários fatores, como o tamanho da
área a ser coberta, a densidade de utilizadores e interferências de outras redes sem fio ou dispositivos eletrónicos na área. Em geral, a frequência de 5 GHz é menos
congestionada e oferece melhor desempenho em velocidade e confiabilidade, mas tem um **alcance menor** do que a **frequência de 2,4 GHz**.

_1.6 Patch Panels, Path Cords e Consolidation Points_

Dado que estaremos a utilizar cabos Cat6a, as restantes ligações e dispositivos utilizarão também Cat6a.

Um **patch panel** é um painel que possui vários conectores usados para conectar diferentes dispositivos de rede a um sistema de cabeamento estruturado.
Os patch panels mais comuns em ambientes de rede empresarial possuem **entre 24 e 48 portas**. No entanto, é possível encontrar patch panels com um número menor
ou maior de portas, dependendo das necessidades de cada ambiente de rede.

Um **patch cord** é um cabo curto com conectores em ambas as extremidades usado para conectar um dispositivo de rede a um patch panel, ou para interconectar
diferentes componentes de rede, como switches, routers ou firewalls. O número exato de patch cords necessários dependerá da distância entre as tomadas de rede e o
patch panel. **Cada tomada de rede precisa de um patch cord** para se conectar ao patch panel, portanto, **o número total de patch cords necessários será igual ao número
de tomadas de rede** que precisam ser conectadas. No entanto, se as tomadas de rede estiverem espalhadas por vários ambientes e com distâncias consideráveis entre si,
será necessário **patch cords mais longos para alcançar o patch panel**. Nesse caso, calcular-se-ia o comprimento necessário para cada patch cord e adicionava-se uma
**margem de segurança** para acomodar qualquer mudança futura no layout da rede.

Em geral, os patch panels e patch cords são usados em conjunto para **criar uma infraestrutura de rede organizada e confiável**, permitindo que os cabos sejam
facilmente gerenciados e conectados, **reduzindo os custos de manutenção e aumentando a eficiência do sistema de cabeamento estruturado**.

Em geral, os **Consolidation Points (CPs)** são instalados em áreas centralizadas e acessíveis, e o seu objetivo é permitir que **novas conexões sejam adicionadas
ou reorganizadas com facilidade, sem ter que alterar o cabo principal** (é conectado ao cabo de rede principal, que por sua vez é conectado a um switch ou router).
Em suma, ao instalar estes dispositivos em cada piso do edifício, deve ter-se em conta a posição dos mesmos já que uma posição estratégica irá diminuir os custos
totais da obra. Geralmente são necessários switches nos CPs para permitir a conexão de múltiplos cabos de rede. No entanto, como este edifício tem dimensões reduzidas,
e os outlets não se encontra a grandes distâncias do Horizontal Cross-Connect, **não será necessário instalar CPs**.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Medidas e dimensões das divisões ###

Seguem-se duas imagens, relativas aos dois pisos, com as medidas e áreas de cada divisão (valores aproximados, resultantes da conversão da escala).

                                                              Planta do piso 0 com as medidas:


![BuildingA_Floor0_Medidas](BuildingA_Floor0_Medidas.PNG)

                                                              Planta do piso 1 com as medidas:

![BuildingA_Floor1_Medidas](BuildingA_Floor1_Medidas.PNG)

Tendo as medidas das paredes, podemos calcular a área de cada uma das divisões.

| Divisão | Largura (m) | Comprimento (m) | Área (m2) |
|--------:|:-----------:|:---------------:|:---------:|
|   A.0.1 |      5      |       5,5       |   27,5    |
|   A.0.2 |      5      |      3,75       |   18,75   |
|   A.0.3 |      5      |      4,88       |   24,4    |
|   A.0.4 |    7,25     |      5,25       |   38,06   |
|   A.0.5 |    4,63     |        6        |   27,78   |
|   A.0.6 |     7,5     |        6        |    45     |
|   A.1.1 |    7,25     |       3,4       |   24,65   |
|   A.1.2 |    7,25     |       3,4       |   24,65   |
|   A.1.3 |    7,25     |       3,4       |   24,65   |
|   A.1.4 |    7,25     |       7,5       |   54,38   |
|   A.1.5 |    4,25     |       5.5       |   23,38   |
|   A.1.6 |      7      |      5,75       |   40,25   |
|   A.1.7 |    4,75     |      5,75       |   27,31   |

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 3. Cabeamento e instalação dos dispositivos ###

Seguem-se duas imagens, relativas aos dois pisos, com o cabeamento e dispositivos instalados, seguindo as regras descritas a cima.

                                                              Planta do piso 0:

![BuildingA_Floor0_Design](BuildingA_Floor0_Design.PNG)

                                                              Planta do piso 1:

![BuildingA_Floor1_Design](BuildingA_Floor1_Design.PNG)

### 4. Materiais necessários e inventário ###

_4.1 Número de outlets (tomadas de rede)_

| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|
|   A.0.1 |      5      |       5,5       |   27,5    |       5       |
|   A.0.2 |      5      |      3,75       |   18,75   |       3       |
|   A.0.3 |      5      |      4,88       |   24,4    |       4       |
|   A.0.4 |    7,25     |      5,25       |   38,06   |     7 + 1     |
|   A.0.5 |    4,63     |        6        |   27,78   |       5       |
|   A.0.6 |     7,5     |        6        |    45     |       9       |
|   A.1.1 |    7,25     |       3,4       |   24,65   |       4       |
|   A.1.2 |    7,25     |       3,4       |   24,65   |       4       |
|   A.1.3 |    7,25     |       3,4       |   24,65   |       4       |
|   A.1.4 |    7,25     |       7,5       |   54,38   |       0       |
|   A.1.5 |    4,25     |       5,5       |   23,38   |       4       |
|   A.1.6 |      7      |      5,75       |   40,25   |       8       |
|   A.1.7 |    4,75     |      5,75       |   27,31   |     5 + 1     |


Nº de outlets no piso 0: 33 + 1 reservado para o Access Point (canal 1)

Nº de outlets no piso 1: 29 + 1 reservado para o Access Point (canal 6)

Total: 64

_4.2 Comprimemto dos cabos e outros materiais úteis_

                                                              Piso 0:

* Fio de cobre Cat6a

Para calcular o comprimento de fio de cobre necessário para os outlets, foi utilizada a seguinte fórmula:

    comprimento total = nº de outlets x (comprimento médio + altura do HCC)

Para calcular o comprimento de fio de cobre necessário para o access point, foi utilizada a seguinte fórmula:

    comprimento total = comprimento até ao AP

| Divisão | Nº de outlets | Comprimento total aproximado (m) |
|--------:|:-------------:|:--------------------------------:|
|   A.0.1 |       5       |     5 * (22,24 + 1) = 116,20     |
|   A.0.2 |       3       |     3 * (16,67 + 1) = 53,01      |
|   A.0.3 |       4       |     4 * (11,65 + 1) = 50,60      |
|   A.0.4 |     7 + 1     |      7 * (7,83 + 1) = 61,81      |
|   A.0.5 |       5       |      5 * (7,10 + 1) = 40,50      |
|   A.0.6 |       9       |     9 * (16,54 + 1) = 157,86     |

1 Access Point:
-> 2,4 m

Total: 482,38 + 24,12 (margem de segurança de 5%) = 506,50 m

* Fibra ótica de modo único

| Divisão | Comprimento total aproximado (m) |
|--------:|:--------------------------------:|
|   A.0.4 |               2,40               |

Total: 2,40 m

* Patch panels

Dado que no piso 0 existem 34 outlets, serão necessários pelo menos 2 patch panels de 24 portas de fio Cat6a, mais um patch panel de fibra
adicional para o HCC.
No entanto, pode ser necessário considerar a escalabilidade futura do sistema de rede e planear para mais portas do que o necessário atualmente.

* Switches

O Horizontal Cross-Connect necessita de dois switches.

* Outros materiais úteis

Podem ser necessários outros materiais úteis como, por exemplo, **estruturas de suporte** utilizadas para proteger os equipamentos de telecomunicações, manter
a organização dos cabos e a segurança dos mesmos. São usadas para suportar e organizar equipamentos de tecnologia, como servidores, switches, routers e outros
dispositivos similares. Eles são usados em DataCenters, salas de servidores e outros locais onde vários equipamentos de TI precisam ser armazenados e
gerenciados num único espaço. Neste edifício seria recomendado o uso destas estruturas para manter os **Cross-Connects seguros**, os **patch panels** e, 
eventualmente, outro hardware que possa ser adquirido (como switches). As estruturas de suporte podem ser de vários tipos e tamanhos, atentendo sempre às
necessidades do edifício.

**Horizontal Cross-Connect:** (1U + 2U) * 3 (Patch Panels ) = 9U
                              2U (Switches)

Total: (9U + 2U) * 2 = 22U

                                                              Piso 1:

* Fio de cobre Cat6a

Para calcular o comprimento de fio de cobre necessário para os outlets, foi utilizada a seguinte fórmula:

    comprimento total = nº de outlets x (comprimento médio + altura do teto amovível + altura do HCC)

Para calcular o comprimento de fio de cobre necessário para o access point, foi utilizada a seguinte fórmula:

    comprimento total = altura do teto amovível + comprimento até ao AP

| Divisão | Nº de outlets | Comprimento total aproximado (m)  |
|--------:|:-------------:|:---------------------------------:|
|   A.1.1 |       4       |  4 * (23,94 + 2,5 + 1) = 109,76   |
|   A.1.2 |       4       |   4 * (18.06 + 2,5 + 1) = 86,24   |
|   A.1.3 |       4       |   4 * (13.88 + 2,5 + 1) = 69,52   |
|   A.1.4 |       0       |                 0                 |
|   A.1.5 |       4       |   4 * (8,56 + 2,5 + 1) = 48,24    |
|   A.1.6 |       8       |  8 * (17,72 + 2,5 + 1) = 169,76   |
|   A.1.7 |     5 + 1     |  5 * (36,25 + 2,5 + 1) = 198,75   |

1 Access Point:
-> 35,00 m

Total: 717,27 + 35,86 (margem de segurança de 5%) = 753,13 m

* Fibra ótica de modo único

Main Cross-Connect até ao Intermediate Cross-Connect/Horizontal Cross-Connect: 1,25 m
Intermediary Cross-Connect até ao Horizontal Cross-Connect: patch cord (cerca de 1 m)
Main Cross-Connect até ao exterior: 5,00 m
Conexão com o piso 0: 2,5 + 2,5 (altura do teto) = 5,00 m

Total: 12,25 m

* Patch panels

Neste piso vão existir 2 patch panels de fibra, um para o Main Cross-Connect e outro para o Intermediate Cross-Connect. No Horizontal Cross-Connect vão existir
2 patch panels de cobre e um patch panel de fibra.
No entanto, pode ser necessário considerar a escalabilidade futura do sistema de rede e planear para mais portas do que o necessário atualmente.

* Switches

O Hrizontal Cross-Connect necessita de dois switches.
O Intermediate Cross-Connect necessita de um switch.
O Main Cross-Connect não necessita de switches.

* Outros materiais úteis

Podem ser necessários outros materiais úteis como, por exemplo, **estruturas de suporte** utilizadas para proteger os equipamentos de telecomunicações, manter
a organização dos cabos e a segurança dos mesmos. São usadas para suportar e organizar equipamentos de tecnologia, como servidores, switches, routers e outros
dispositivos similares. Eles são usados em DataCenters, salas de servidores e outros locais onde vários equipamentos de TI precisam ser armazenados e
gerenciados num único espaço. Neste edifício seria recomendado o uso destas estruturas para manter os **Cross-Connects seguros** como também os **Consolidation
Points**, os **patch panels** e, eventualmente, outro hardware que possa ser adquirido (como switches). As estruturas de suporte podem ser de vários tipos e
tamanhos, atentendo sempre às necessidades do edifício. Neste caso devem abranger o dobro do espaço necessário para os equipamentos.

**Main Cross-Connect:** 1U + 2U = 3U (patch panels)
**Intermediate Cross-Connect:** 1U + 2U (patch panels) + 1U (switch) = 4U
**Horizontal Cross-Connect:** (1U + 2U) * 3 (patch panels ) + 2U (switches) = 11U

Total: (3U + 4U + 11U) * 2 = 36U

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 5. Hardware total necessário (inventário) ###

|            | Fio de cobre Cat6a (m) | Fio de fibra ótica modo único (m) | Outlets | Access Points | Patch Panels | Patch Cords | Switches |
|------------|:----------------------:|:---------------------------------:|:-------:|:-------------:|:------------:|:-----------:|:--------:|
| **Piso 0** |         506,50         |               2,40                |   34    |       1       |      3       |     34      |    2     |
| **Piso 1** |         753,13         |               12,25               |   30    |       1       |      5       |     30      |    3     |
| **Total**  |        1259,63         |               14,65               |   64    |       2       |      8       |     64      |    5     |