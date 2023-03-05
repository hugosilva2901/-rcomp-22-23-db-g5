## RCOMP 2022/2023 - SPRINT 1 EDIFÍCIO A - 1211148 ##

===========================================================================

### Introdução: ###
Este ficheiro documenta o planeamento e estruturamento do Edifício A, que 
está dividido em dois pisos.

------------------------------------------------------------------------------------------------------------------------------------------------------------

### Índice: ###

1. **Regras de cabeamento e visão geral da estruturação do Edifício A**

------------------------------------------------------------------------------------------------------------------------------------------------------------

### 1. Regras de cabeamento e visão geral da estruturação do Edifício A: ###

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

_1.2 Número de outlets_

Generalizando, um espaço de escritório padrão pode exigir aproximadamente uma tomada de rede a cada 10 a 15 metros quadrados, enquanto um espaço residencial 
pode exigir uma tomada a cada 20 a 30 metros quadrados. No entanto, dadas as condições exigidas pelo enunciado, vamos considerar que serão necessárias **2 
tomadas por cada 10 metros quadrados**.

_1.3 Cabeamento_

Ambos os padrões de cabeamento **568A** e **568B** para redes Ethernet podem ser usados com vários tipos de cabos de cobre, incluindo cabos de Categoria 5e 
(Cat5e), Categoria 6 (Cat6) e Categoria 6a (Cat6a). O cabo *Cat6a* fornece um **desempenho bastante alto** e pode suportar **taxas de transferência de dados 
de até 10 GB/s** em distâncias de **até 100 metros**. É recomendado para aplicações de alta performance que exigem **conectividade confiável** e de **alta 
velocidade** em distâncias maiores.

**Cat7** é um tipo de cabo de cobre projetado para suportar a **rede Ethernet de alta velocidade a taxas de transferência de dados** ainda mais altas e em 
distâncias maiores do que o Cat6a. É um cabo de par trançado **totalmente blindado** (STP), o que proporciona **melhor resistência ao ruído e interferência** 
do que cabos não blindados como o Cat5e e o Cat6.

No entanto, é importante realçar que o Cat7 **não é um padrão oficialmente reconhecido pela Telecommunications Industry Association (TIA) ou pela International 
Organization for Standardization (ISO)**. Embora esteja amplamente disponível, sua **compatibilidade com outros equipamentos de rede e sua prova futura não são 
garantidos**. Como resultado, o Cat6a é frequentemente a escolha preferida para instalações Ethernet de alto desempenho, e vai ser também utilizado no cabeamento 
deste edifício. 

Como fios de fibra, vão ser utilizados **cabos de fibra ótica de modo único**, também conhecidos como monomodo. São projetados para **transmitir sinais de luz num 
único caminho**. Eles são feitos com um **núcleo menor e mais denso** do que os cabos de modo múltiplo, permitindo que os **sinais de luz sejam transmitidos em 
distâncias maiores com menos atenuação de sinal**. As únicas desvantagens destes cabos são **o custo**, que é mais elevado do que os cabos de modo múltiplo, e a
**menor resistência a danos físicos**. 
