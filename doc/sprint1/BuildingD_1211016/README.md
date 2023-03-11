# RCOMP 2022/2023 - SPRINT 1 EDIFÍCIO D - 1211016 #

===========================================================================

## Introdução: ##
Este ficheiro tem o propósito de documentar o desenvolvimento de um projeto de cabeamento estruturado do Edifício D, que está dividido em dois pisos.

------------------------------------------------------------------------------------------------------------------------------------------------------------

## Índice: ##
1. **Considerações gerais e normativas de cabeamento**
2. **Abordagem no design da estrura de cabelagem do edifício**
3. **Regras de cabeamento e visão geral da estruturação do edifício D**
4. **Medidas e dimensões das divisões**

------------------------------------------------------------------------------------------------------------------------------------------------------------
## 1. Considerações gerais e normativas de cabeamento ##


* O número de outlets por divisão standard é de **2 por cada 10m2** de área, num contexto empresarial, no entanto este número pode variar dependendo do uso que é dado à respetiva divisão.


* A localização de **cross connects** e **patch pannels** é definida de acordo com as normas da ISO/IEC 11801 e com o objetivo de minimizar o comprimento de cabos.


* Os **cabos de cobre** CAT6 (1Gbps) e CAT7 (10Gbps), limitados a um comprimento de 90m são utilizados para equipamento "end user" como PC's e impressoras uma vez que é o standard para estes equipamentos.


* Os **cabos de fibra ótica** podem ser utilizados nos cross connects, se estes o permitirem, uma vez que o comprimento e "data rate" permitido é bastante superior.



------------------------------------------------------------------------------------------------------------------------------------------------------------
## 2. Abordagem no design da estrutura de cabeamento do edifício ##

 Para estruturar o cabeamento deste edifício, será utilizada uma abordagem, bottom-up ,
 que consiste em começar por levantar informação mais detalhada sobre as necessidades de cada divisão
 e posteriormente, tomar decisões de design.
 
Assim, a abordagem segue os seguintes passos:

### 2.1 Medição da área das salas ###

* O primeiro passo consiste em medir a área de cada divisão, para que seja possível determinar o número de outlets necessários.

* Posteriormente, será possível determinar o número de cross connects e patch pannels necessários.

* Serão também considerados casos em que o número de outlets seja diferente do standard, devido a necessidades específicas de cada divisão.

### 2.2 Localizar a posição dos outlets em cada divisão ###

* Será necessário tomar em consideração a posição dos outlets, de forma a que seja razoável para a utilização nas workstations e access points.

### 2.3 Determinar a localização de cross connects ###

* A localização dos cross connects será determinada com vista a que esteja o mais central possível aos outlets servidos por estes e em salas pouco acessíveis pelo público.

* Primeiro serão colocados os CP (consolidation points), se necessário, posteriormente os HC (horizontal cross connects) e finalmente os IC (intermediate cross connects).

### 2.4 Definir cabelagem e roteamento de cabos ###

* Após saber o local dos outlets e cross connects, será possível definir a estrutura de cabeamento e o roteamento de cabos.

* Ligações redundantes são desejadas, pois garantem failover, e aumento de bandwidth com load balancing.

### 2.5 Definir tipos de cabos ###

* Em contexto horizontal, serão utilizados cabos de cobre CAT6 ou superior, entre os cross connects, serão preferidos cabos de fibra ótica, por causa dos seus benefícios em bandwidth e compatibilidade.

### 2.6 Manter um inventário ###

* Por fim, será apresentado um inventário com todo o material necessário para a implementação física da solução apresentada.

------------------------------------------------------------------------------------------------------------------------------------------------------------
## 3. Regras de cabeamento e estruturação geral do Edifício D ##

### 3.1 Estrutura do edifício ###

                                                              Planta do piso 0 (presente no enunciado):


![BuildingD_floor0](BuildingD_floor0.png)

#### Considerações: ####

* A entrada de cabos no edifício é feita através de uma vala subterrânea com entrada na sala D.0.15, sala esta que tem condições para alojar um Cross Connect.
* Neste piso há passagem de cabos subterrânea.
* A altura das paredes é de 4m.
* A sala D.0.15 não necessita de Outlets devido à sua função de alojamento de Cross Connects e de ser uma sala de armazenamento.
* O mesmo se aplica à sala D.0.0.16, halls de entrada, corredores e WC's.
* As salas D.0.1, D.0.2 e D.0.3 têm propósitos específicos e só precisam de 2 outlets perto de cada passagem de cabos.
* Nas restantes aplica-se o número de outlets por divisão standard.
* É necessária cobertura **WLAN (Wi-Fi)** em todo o piso.


                                                              Planta do piso 1 (presente no enunciado):

![BuildingD_floor1](BuildingD_floor1.png)

#### Considerações: ####

* A entrada de cabos no edifício é feita por uma coluna com entrada na sala D.1.8, sala esta que tem condições para alojar Cross Connects.
* Neste piso **não** há passagem de cabos subterrânea.
* A altura das paredes é de 3m, no entanto, existe um teto falso com altura de 2,5m. O espaço entre os dois pode ser usado para roteamento de cabos e colocação de access points.
* A sala D.1.8 não necessita de Outlets devido à sua função de alojamento de Cross Connects e de ser uma sala de armazenamento.
* O mesmo se aplica à sala a halls de entrada, corredores e WC's.
* Nas restantes aplica-se o número de outlets por divisão standard.
* É necessária cobertura **WLAN (Wi-Fi)** em todo o piso.