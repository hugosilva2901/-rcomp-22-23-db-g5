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

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Regras de cabeamento e estruturação geral do Edifício A: ###

_1.1 Informação geral_

Seguem-se algumas especificações deste edifício presentes no enunciado deste projeto:

* As dimensões horizontais são de, aproximadamente, 20 x 20 metros.

* Uma vala técnica subterrânea com canaletas de cabos (representado em azul) existe e inclui passagens de cabos para cada edifício, e está pronto para 
  cabeamento de telecomunicações e outros.

* Este edifício alberga o **DataCenter (sala A.1.4)**, albergará também o **cross-connect principal** para o sistema de cabeamento estruturado. Ambos os 
  andares devem ter cobertura **LAN sem fio (Wi-Fi)**.

* O piso 0 possui uma canaleta de cabos sob o piso conectada à vala técnica externa. Acesso à canaleta de cabos sob o piso está disponível nos pontos 
  marcados na planta na imagem abaixo. Além disso, cabo passagens para o andar acima estão disponíveis.

* A altura do teto no piso 0 é de 4 metros. Áreas comuns, como o hall de entrada, banheiros e escadas, não requerem tomadas de rede.

* A altura do teto do piso 1 é de 3 metros, no entanto existe um teto rebaixado amovível, colocado a 2,5 metros do chão, cobrindo todo o andar. O espaço 
  sobre o teto rebaixado é perfeito para instalar canaletas de cabos e pontos de acesso sem fio. Este andar não possui canaletas de cabos subterrâneos.


                                                              Planta do piso 0 (presente no enunciado):


![BuildingA_Floor0](BuildingA_Floor0.PNG)

                                                              Planta do piso 1 (presente no enunciado):

![BuildingA_Floor1](BuildingA_Floor1.PNG)

_1.2 Número de outlets (tomadas)_

Generalizando, um espaço de escritório padrão pode exigir aproximadamente uma tomada de rede a cada 10 a 15 metros quadrados, enquanto um espaço residencial 
pode exigir uma tomada a cada 20 a 30 metros quadrados. No entanto, dadas as condições exigidas pelo enunciado, vamos considerar que serão necessárias **2 
tomadas por cada 10 metros quadrados**.

_1.3 Cabeamento_

Ambos os padrões de cabeamento **568A** e **568B** para redes Ethernet podem ser usados com vários tipos de cabos de cobre, incluindo cabos de Categoria 5e 
(Cat5e), Categoria 6 (Cat6) e Categoria 6a (Cat6a). O cabo *Cat6a* fornece um **desempenho bastante alto** e pode suportar **taxas de transferência de dados 
de até 10 GB/s** em distâncias de **até 100 metros**. É recomendado para aplicações de alta performance que exigem **conectividade confiável** e de **alta 
velocidade** em distâncias maiores.

**Cat7** é um tipo de cabo de cobre projetado para suportar a **rede Ethernet de alta velocidade a taxas de transferência de dados** ainda mais altas e em 
distâncias maiores do que o Cat6a. É um cabo **totalmente blindado** (STP), o que proporciona **melhor resistência ao ruído e interferência** do que cabos 
não blindados como o Cat5e e o Cat6.

No entanto, é importante realçar que o Cat7 **não é um padrão oficialmente reconhecido pela Telecommunications Industry Association (TIA) ou pela International 
Organization for Standardization (ISO)**. Embora esteja amplamente disponível, sua **compatibilidade com outros equipamentos de rede e sua prova futura não são 
garantidos**. Como resultado, o Cat6a é frequentemente a escolha preferida para instalações Ethernet de alto desempenho, e vai ser também utilizado no cabeamento 
deste edifício. 

Como fios de fibra vão ser utilizados **cabos de fibra ótica de modo único**, também conhecidos como monomodo. São projetados para **transmitir sinais de luz num 
único caminho**. Eles são feitos com um **núcleo menor e mais denso** do que os cabos de modo múltiplo, permitindo que os **sinais de luz sejam transmitidos em 
distâncias maiores com menos atenuação de sinal**. As únicas desvantagens destes cabos são **o custo**, que é mais elevado do que os cabos de modo múltiplo, e a
**menor resistência a danos físicos**. 

_1.4 Cross-conection_

Os cross-connects são normalmente instalados em **DataCenters**, centrais telefónicas e outras instalações de telecomunicações. Eles fornecem uma maneira eficiente 
de gerenciar e organizar as conexões entre vários componentes de rede, como switches, routers e servidores. Nesta planta existem um **MC (Main Cross-Connect)**, um
**IC (Intermediate Cross-Connect)** e dois **HC's (Horizontal Cross-Connect)**. Podemos estimar que **a área total abrangida pelo HC não deve exceder os 1000 m2** e 
que **a distância máxima entre uma tomada e um HC** deve ser de, aproximadamente, **80 metros**. Relativamente às **distâncias entre os cross-connects**, cada uma 
não deve exceder os **500 metros**.

_1.5 Access Points_

**Access points (APs)** são dispositivos de rede sem fio que **permitem que os dispositivos clientes se conectem a uma rede sem fio**. Os access points são usados 
em redes sem fio para **estender a cobertura da rede e fornecer conectividade sem fio em áreas onde o sinal do router ou do switch não alcança**. Eles normalmente 
são conectados a um switch ou router de rede com fio para fornecer uma conexão de rede sem fio. Um access point tem uma cobertura de cerca de **30 a 50 metros de 
raio**. 

_1.6 Patch Panels, Path Cords, Consolidation Points e Switches_

Dado que estaremos a utilizar cabos Cat6a, todas as restantes ligações e dispositivos utilizarão também Cat6a. 

Um **patch cord** é um cabo curto com conectores em ambas as extremidades que é usado para conectar um dispositivo de rede a um patch panel, ou para interconectar 
diferentes componentes de rede, como switches, routers ou firewalls. 

Um **patch panel** é um painel que possui vários conectores que são usados para conectar diferentes dispositivos de rede a um sistema de cabeamento estruturado. 

Em geral, os patch panels e patch cords são usados em conjunto para **criar uma infraestrutura de rede organizada e confiável**, permitindo que os cabos sejam 
facilmente gerenciados e conectados, **reduzindo os custos de manutenção e aumentando a eficiência do sistema de cabeamento estruturado**.

Em geral, os **Consolidation Points (CPs)** são instalados em áreas centralizadas e acessíveis, e o seu objetivo é permitir que **novas conexões sejam adicionadas 
ou reorganizadas com facilidade, sem ter que alterar o cabo principal** (é conectado ao cabo de rede principal, que por sua vez é conectado a um switch ou router).
Em suma, ao instalar estes dispositivos em cada piso do edifício, deve ter-se em conta a posição dos mesmos já que uma posição estratégica irá diminuir os custos
totais da obra.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2. Medidas e dimensões das divisões ###

Seguem-se duas imagens, relativas aos dois pisos, com as medidas e áreas de cada divisão (valores aproximados, resultantes da conversão da escala).

                                                              Planta do piso 0 com as medidas:


![BuildingA_Floor0_Medidas](BuildingA_Floor0_Medidas.PNG)

                                                              Planta do piso 1 com as medidas:

![BuildingA_Floor1_Medidas](BuildingA_Floor1_Medidas.PNG)

Tendo as medidas das paredes, podemos calcular a área de cada uma das divisões.

| Divisao | Largura (m) | Comprimento (m) | Área(m2) |
|--------:|:-----------:|:---------------:|:--------:|
|   A.0.1 |      5      |       5,5       |   27,5   |
|   A.0.2 |      5      |      3,75       |  18,75   |
|   A.0.3 |      5      |      4,88       |   24,4   |
|   A.0.4 |    7,25     |      5,25       |  38,06   |
|   A.0.5 |    4,63     |        6        |  27,78   |
|   A.0.6 |     7,5     |        6        |    45    |
|   A.1.1 |    7,25     |       3,4       |  24,65   |
|   A.1.2 |    7,25     |       3,4       |  24,65   |
|   A.1.3 |    7,25     |       3,4       |  24,65   |
|   A.1.4 |    7,25     |       7,5       |  54,38   |
|   A.1.5 |    4,25     |       5.5       |  23,38   |
|   A.1.6 |      7      |      5,75       |  40,25   |
|   A.1.7 |    4,75     |      5,75       |  27,31   |

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 3. Cabeamento e instalação dos dispositivos ###

Seguem-se duas imagens, relativas aos dois pisos, com o cabeamento e dispositivos completos, seguindo as regras descritas a cima.

                                                              Planta do piso 0:

![BuildingA_Floor0_Design](BuildingA_Floor0_Design.PNG)

                                                              Planta do piso 1:

![BuildingA_Floor1_Design](BuildingA_Floor1_Design.PNG)

