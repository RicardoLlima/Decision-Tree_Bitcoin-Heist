# Análise de Transações Bitcoin com Machine Learning

Este projeto usa machine learning para analisar dados de transações em Bitcoin e classificar endereços como pertencentes a ransomware ou legítimos. O modelo principal é uma Árvore de Decisão treinada para distinguir entre diferentes tipos de transações.

## Índice

- [Introdução](#introdução)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Instalação](#instalação)
- [Descrição dos Dados](#descrição-dos-dados)
- [Análise Exploratória de Dados](#análise-exploratória-de-dados)
- [Pré-Processamento dos Dados](#pré-processamento-dos-dados)
- [Treino e Avaliação do Modelo](#treino-e-avaliação-do-modelo)
- [Visualização](#visualização)
- [Conclusão](#conclusão)

## Introdução

Este projeto utiliza dados de transações em Bitcoin, procurando entender e prever a natureza das transações, identificando se são legítimas ou potencialmente vinculadas a ransomware. Com a aplicação de uma Árvore de Decisão, o modelo é capaz de classificar transações com base em características específicas.

## Estrutura do Projeto

- `BitcoinHeistData.csv`: Dataset com informações sobre transações de Bitcoin.
- `Projeto.ipynb`: Código principal com a implementação dos passos de análise, pré-processamento, treino e avaliação.
- `README.md`: Documento descritivo do projeto.

## Instalação

1. Clone o repositório:
  ```bash
   git clone https://github.com/RicardoLlima/Decision-Tree_Bitcoin-Heist
   cd Decision-Tree_Bitcoin-Heist
  ```

2. Instale as dependências necessárias:
  ```bash
    pip install -r requirements.txt
  ```

3. Descarregue o dataset [aqui](https://archive.ics.uci.edu/dataset/526/bitcoinheistransomwareaddressdataset) e coloque-o na pasta principal do projeto.
   
4. Abra e execute o ficheiro `Projeto.ipynb`.

## Descrição dos Dados

As variáveis do conjunto de dados representam diferentes características das transações:

| Nome       | Tipo    | Descrição                                                                                       |
|------------|---------|-------------------------------------------------------------------------------------------------|
| address    | string  | Endereço do destinatário exclusivo                                                              |
| year       | int     | Ano da transação                                                                                |
| day        | int     | Dia da transação                                                                                |
| length     | int     | Número de "mixing rounds" para dificultar rastreamento                                          |
| weight     | float   | Diferença entre número de entradas e saídas na transação                                        |
| count      | int     | Número de transações                                                                            |
| looped     | int     | Número de transações para um endereço com caminhos alternativos                                 |
| neighbors  | int     | Número de transações referentes a cada Bitcoin                                                  |
| income     | int     | Rendimento recebido no endereço                                                                 |
| label      | string  | Tipo da transação (Ex: ransomware específico ou "white" para transações legítimas)              |

## Análise Exploratória de Dados

O passo de análise dos dados inclui a visualização dos dados que ajuda a entender melhor a distribuição e comportamento das variáveis no dataset. As seguintes análises gráficas são realizadas:

1. Número de transações por ano.
2. Distribuição de transações ao longo dos dias do ano.
3. Distribuição do número de rounds de mixing.
4. Distribuição do número de transações (`count`).
5. Distribuição da variável `weight`.
6. Distribuição da variável `income`.
7. Análise da variável `neighbors`.

## Pré-Processamento dos Dados

No pré-processamento, são realizados os seguintes passos:

- Identificação e remoção de valores nulos e duplicados.
- Conversão de variáveis categóricas para valores numéricos usando `replace()` para facilitar o treino do modelo.

## Treino e Avaliação do Modelo

Para classificar as transações, é utilizada uma Árvore de Decisão. As etapas incluem:

1. Dividir o dataset em conjuntos de treino e teste.
2. Treinar o modelo de Árvore de Decisão com os dados de treino.
3. Avaliar o desempenho com o relatório de classificação e matriz de confusão.
4. Visualizar a árvore de decisão resultante para interpretação.

## Visualização

O projeto inclui uma visualização gráfica da Árvore de Decisão, que facilita a interpretação de como o modelo está a tomar decisões com base nas variáveis fornecidas.

## Conclusão

Este projeto apresenta uma abordagem inicial para a classificação de transações Bitcoin como ransomware ou legítimas. Com a visualização da Árvore de Decisão, ficamos a perceber melhor o sistema de decisões e serve de base para futuras melhorias no modelo, como a utilização de modelos mais complexos.
