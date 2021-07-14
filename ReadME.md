## **Table of Contents**
- [Extra - Super Krunfo](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1esj4slvm0)
  - [Objetivo](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1f362b6b10)
  - [Preparativos](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1f362b6b11)
  - [Super Krunfo](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1eg6l938o6l)
  - [Implementação](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1f38lscpo0)
- [Entregáveis](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1f362b6b12)
  - [Repositório](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1egvrpv6k1l4)
- [Critérios de aceitação](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/1b_ee_02_super-krunfo.html&ref=master#mcetoc_1eh146n6m3)
# **Extra - Super Krunfo**
Para essa entrega você criará um pequeno jogo de super trunfo, se você não conhece esse jogo, [clique aqui](https://pt.wikipedia.org/wiki/Super_Trunfo) para conhecer.
## **Objetivo**
Essa atividade foi elaborada para trabalhar seus conhecimentos de leitura de arquivos CSV e manipulação de dados utilizando a biblioteca [random](https://www.w3schools.com/python/module_random.asp) em Python.
## **Preparativos**
Você devera criar um arquivo chamado krunfo.py e implementar as funções conforme as descrições.

Crie um arquivo CSV chamado super\_heroes.csv e popule-o com os dados desse [snippet](https://gitlab.com/-/snippets/2105055).
## **Super Krunfo**
Vamos considerar cada carta do seu super trunfo como uma linha lida do seu arquivo CSV (tirando o header), cada uma das cartas terão os seguintes atributos a serem considerados:

- name: será o nome do super-herói
- intelligence: será a inteligência do super-herói
- power: seu poder sobrenatural perante os outros super-heróis
- strenght: força física do super-herói
- agility: agilidade do super-herói
- vitality: resistência e energia do super-herói
## **Implementação**
Crie as seguintes funções seguindo as orientações:

- **list\_all\_super\_heroes(filename)**
  - **Parâmetros:** a função recebe o nome do arquivo a ser lido filename
    - filename: uma **string** com o nome do arquivo a ser lido
  - **Procedimento:** 
    - Faça uma leitura no arquivo super\_heroes.csv.
  - **Retorno:**
    - Uma **lista** de dicionários contendo todos os heróis do csv, no seguinte [formato](https://gitlab.com/-/snippets/2105425) aproximado.

- **get\_players\_decks(card\_list)**
  - **Parâmetros:**
    - card\_list: **lista de dicionários**, em que cada dicionário **representa uma carta**.
  - **Procedimento:** 
    - Verificar se a **quantidade de cartas é par**, caso não seja, retornar None.
    - De forma **pseudo-aleatória** (shuffle) **e igualitária dividir as cartas** (dicionários) da lista card\_list entre dois jogadores (embaralhar cartas para 2 jogadores).
  - **Retorno:**
    - Uma **tupla de duas posições**, a primeira para o jogador A e a segunda para o jogador B. **Cada posição** da tupla **deve conter uma lista de dicionários**, em que cada dicionário é uma carta.

- **compare\_cards(player\_a\_card, player\_b\_card, score)**
  - **Parâmetros**:
    - player\_a\_card: um **dicionário** representando uma carta do jogador A.
    - player\_b\_card: um **dicionário** representando uma carta do jogador B.
    - score: uma **lista com duas posições**. Na primeira, um **valor numérico** indicando a **pontuação do jogador A** e na segunda um **valor numérico** indicando a **pontuação do jogador B**.
  - **Procedimento**:
    - Deve comparar **aleatoriamente** um atributo da carta A **com o mesmo atributo** da carta B para determinar quem ganhou a rodada (quem tiver o maior número no atributo ganha).
    - Dependendo do resultado, o score do **jogador vencedor** deve ser **incrementado em 1**.
    - Em caso de **empate**, **não incrementar** o score de **nenhum** dos dois jogadores.
  - **Retorno**:
    - Uma **lista** de **duas posições** representando os scores **atualizados**.

- **play(card\_list, score)**
  - **Parâmetros:**
    - card\_list: **lista de dicionários**, em que cada dicionário **representa uma carta**.
    - score: **uma lista com duas posições**. Na primeira posição, um **valor numérico indicando a pontuação** do jogador A e a segunda posição um valor numérico indicando a pontuação do jogador B. Inicialmente essa lista deve ser inicializada como **[0, 0]**
  - **Procedimento:** 
    - Chamar a função get\_players\_decks para obter o deck de cada jogador**.**
    - Utilizar a função compare\_cards para comparar as cartas dos jogadores.
      - A primeira carta do **jogador A** deve ser comparada com a primeira carta do **jogador B**, de forma consecutiva.
    - Montar uma lista com duas posições, sendo a primeira posição o total de cartas vencedoras do **jogador A** e a segunda posição, o total de cartas vencedoras do jogador B.
  - **Retorno:**
    - Uma **lista** com duas posições, em sua primeira posição, o total de cartas vitoriosas do **jogador A**, e na segunda posição, o total de cartas vitoriosas do **jogador B**.
    - Caso get\_players\_decks retorne None por ter um número impar de personagens no CSV, a função play também deve retornar None.
-----
# **Entregáveis**
## **Repositório**
- Link do **repositório** do **GitLab**
- **Código-fonte:**
  - Arquivo **krunfo.py**.
- **Privacidade**
  - Incluir **ka-br-out-2020-correcoes** como **reporter**.
-----
# **Critérios de aceitação**

|**pts**|**Dado**|**Quando**|**É esperado**|
| :- | :- | :- | :- |
|1.0|list\_all\_super\_heroes|Executada a função|Retorne uma lista de dicionários com os dados do CSV|
|1.0|get\_players\_decks|Executada a função|Retorne uma tupla com o deck do jogador A e do jogador B, ou None|
|1.0|compare\_cards|Executada a função|Processado o vencedor, retorne o score atualizado|
|1.0|play|Executada a função|Inicialize o jogo, pareie todos os combates entre cartas e retorne o score final|

` `**Boa diversão, devs! 🧛‍♀️** 

