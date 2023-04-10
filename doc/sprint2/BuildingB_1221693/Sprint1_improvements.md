RCOMP 2022-2023 Project
=======================

### Improvements from sprint 1 for Building B

#### 1221693 - Hugo Silva

---

Este documento engloba as melhorias que poderiam ser feitas no Sprint anterior deste projeto, tendo em conta o feedback
recebido pelo professor.


* Na determinação do número de outlets de cada divisão face à area da mesma, deveria ser considerada um arredondamento
* 
* para cima

Para o piso 0, temos:

| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets | Antes | Depois |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|:-----:|:------:|
|   B.0.1 |      3.33   |       5,74      |   19.11   |       4       |   4   |   4    |
|   B.0.2 |      3.33   |       5,74      |   19.11   |       4       |   4   |   4    |
|   B.0.3 |      3.33   |       5,74      |   19.11   |       4       |   4   |   4    |
|   B.0.4 |      3.33   |       5,74      |   19.11   |       4       |   4   |   4    |
|   B.0.5 |      4.81   |       8.52      |    41     |       8       |   8   |   9    |
|   B.0.6 |      9.63   |       10.93     |   105.26  |       5       |   5   |   5    |
|   B.0.7 |      9.63   |       10.93     |   105.26  |       5       |   5   |   5    |
|   B.0.8 |      3.33   |       8.52      |   28.37   |       5       |   5   |   6    |
|   B.0.9 |      3.33   |       8.52      |   28.37   |       5       |   5   |   6    |
|   B.0.10|      3.33   |       4.63      |   15.42   |       3       |   3   |   4    |

Para o piso 1, temos:

| Divisão | Largura (m) | Comprimento (m) | Área (m2) | Nº de outlets | Antes | Depois |
|--------:|:-----------:|:---------------:|:---------:|:-------------:|:-----:|:------:|
|   B.1.1 |    3.89     |       8.89      |   34.58   |       6       |   6   |   7    |
|   B.1.2 |    3.70     |       8.89      |   32.89   |       6       |   6   |   7    |
|   B.1.3 |    3.70     |       8.89      |   32.89   |       6       |   6   |   7    |
|   B.1.4 |    3.70     |       8.89      |   32.89   |       6       |   6   |   7    |
|   B.1.5 |    3.70     |       8.89      |   32.89   |       6       |   6   |   7    |
|   B.1.6 |    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.7 |    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.8 |    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.9 |    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.10|    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.11|    7.04     |       4.26      |   30.00   |       6       |   6   |   6    |
|   B.1.13|    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.14|    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |
|   B.1.15|    7.04     |       4.44      |   31.26   |       6       |   6   |   7    |

* O cálculo de espaço dedicado para o "housing" dos equipamentos de rede (U's) deveria ser melhor explicado e
* documentado.
* Não há necessidade de haver um outlet dedicado para o access point, apenas uma ligação direta.