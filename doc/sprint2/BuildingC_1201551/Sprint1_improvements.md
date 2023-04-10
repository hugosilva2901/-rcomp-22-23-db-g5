RCOMP 2022-2023 Project
=======================

### Improvements from sprint 1 for Building A

#### 1201551 - Antonio Martingo

---

Este documento engloba as melhorias que poderiam ser feitas no Sprint anterior deste projeto, tendo em conta o feedback
recebido pelo professor.

---

* Na determinação do número de outlets de cada divisão face à area da mesma, deveria ser considerada um arredondamento
* 
* para cima, ou seja:

  * Para o piso 1, nomeadamente nos espacos cuja area e de 16,34/17,28 m2, o numero de outlets a instalar seriam 4.
  * Para o piso 0, temos:

Para o piso 0, temos:

| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets | Antes | Depois |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|:-----:|:------:|
|   C.0.1 |    7,22     |      8,33       |   60,14   |       6       |   6   |   6    |
|   C.0.2 |    7,22     |      8,70       |   62,81   |       6       |   6   |   6    |
|   C.0.3 |    7,22     |      11,11      |   80,21   |      10       |   6   |   6    |
|   C.0.4 |    6,94     |      7,78       |   38,06   |     8 + 1     |   6   |   6    |
|   C.0.5 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|   C.0.6 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|   C.0.7 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|   C.0.8 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|   C.0.9 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|  C.0.10 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|  C.0.11 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|  C.0.12 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|  C.0.13 |    3,15     |      6,48       |   20,41   |       4       |   6   |   6    |
|  C.0.14 |    2,41     |      3,15       |   7,59    |      ---      |  ---  |  ---   |
|  C.0.15 |    4,07     |      3,15       |   12,82   |       2       |   2   |   4    |


Para o piso 1, temos:

| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets | Antes | Depois |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|:-----:|:------:|
|   C.1.1 |    7,59     |      5,19       |   39,39   |       8       |   8   |   8    |
|   C.1.2 |    3,15     |      5,19       |   16,34   |       3       |   3   |   4    |
|   C.1.3 |    3,15     |      5,19       |   16,34   |       3       |   3   |   4    |
|   C.1.4 |    3,15     |      5,19       |   16,34   |       3       |   3   |   4    |
|   C.1.5 |    3,15     |      5,19       |   16,34   |       3       |   3   |   4    |
|   C.1.6 |    3,15     |      5,19       |   16,34   |       3       |   3   |   4    |
|   C.1.7 |    3,15     |      5,19       |   16,34   |       3       |   3   |   4    |
|   C.1.8 |    6,67     |      1,85       |   12,34   |      ---      |   3   |   4    |
|   C.1.9 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.10 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.11 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.12 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.13 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.14 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.15 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.16 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.17 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.18 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |
|  C.1.19 |    3,33     |      5,19       |   17,28   |     3 + 1     |   3   | 4 + 1  |
|  C.1.20 |    3,33     |      5,19       |   17,28   |       3       |   3   |   4    |

 * Foi considerado que qualquer valor acrescido a um multiplo de 10 so deve ser considerado para arredondamento de area se este valor for superior a 1m.
* Para alguns espacos em específico, tais como C.0.1, C.0.2, C.0.3, o numero de outlets nao foi aumentado, por motivos especificos.
* Assumindo que a rede wifi nao e capaz de ser transmitida entre pisos, os AP's (Acess Points) deveriam ser colocados numa area mais central.
* O cálculo de espaço dedicado para o "housing" dos equipamentos de rede (U's) deveria ser melhor explicado e
* documentado.
