# Big Data — Apache Spark com PySpark

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-PySpark-E25A1C?logo=apachespark&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00?logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

## Sobre o repositório

Este repositório reúne exercícios e atividades práticas desenvolvidos na **segunda metade da disciplina de Big Data**, do curso de **Bacharelado em Ciência da Computação da Pontifícia Universidade Católica do Paraná (PUCPR)**.

As implementações utilizam **Apache Spark com a API PySpark**, explorando os fundamentos do processamento distribuído de dados por meio de **Resilient Distributed Datasets (RDDs)** e **Pair RDDs**. Os notebooks apresentam desde operações básicas de transformação e ação até consultas, filtragens e agregações aplicadas a conjuntos de dados reais.

A primeira parte da disciplina, dedicada ao paradigma **Hadoop MapReduce**, está documentada no repositório [big-data-mapreduce-pjbl1](https://github.com/sergiocalazans/big-data-mapreduce-pjbl1).

## Objetivos de aprendizagem

- Compreender a criação e o processamento de RDDs com o Apache Spark.
- Aplicar transformações como `map`, `flatMap`, `filter`, `distinct`, `union`, `intersection` e `subtract`.
- Utilizar ações como `collect`, `take`, `count`, `countByValue` e `reduce`.
- Trabalhar com estruturas chave-valor (*Pair RDDs*) e operações como `mapValues`, `sortByKey` e `reduceByKey`.
- Realizar análises, agregações e cálculos estatísticos a partir de arquivos CSV.
- Identificar e tratar valores ausentes durante a preparação de dados.

## Conteúdo dos notebooks

### 1. RDD — Transformações, ações e análise de dados

**Arquivo:** [`RDD.ipynb`](RDD.ipynb)

Introdução aos RDDs e às principais operações da API do PySpark, seguida de exercícios aplicados a dois conjuntos de dados.

**Eurocopa 2024 (`euro2024_players.csv`):**
- Conversão dos nomes dos jogadores para letras maiúsculas.
- Seleção de jogadores da Alemanha.
- Contagem e listagem de jogadores ingleses com menos de 25 anos.
- Cálculo da média de gols dos jogadores da Itália.
- Contagem de clubes distintos representados por jogadores da Alemanha.

**Dados meteorológicos australianos (`weather_aus.csv`):**
- Contagem de registros e cidades distintas.
- Cálculo da precipitação média na cidade de Albury.
- Identificação da maior velocidade de rajada de vento registrada.
- Contagem de registros por cidade.
- Consultas aos indicadores `RainToday` e `RainTomorrow`.
- Cálculo da temperatura média às 15h em dias com chuva.
- Identificação das temperaturas máxima e mínima às 9h para dias em que chove no dia seguinte.

[Abrir RDD.ipynb no Google Colab](https://colab.research.google.com/github/sergiocalazans/big-data-pyspark/blob/main/RDD.ipynb)

### 2. Pair RDD — Processamento por chave e valor

**Arquivo:** [`PairRDD.ipynb`](PairRDD.ipynb)

Estudo dos RDDs compostos por pares chave-valor e de operações para organizar, filtrar e agregar dados.

**Atividades com a base da Eurocopa 2024:**
- Construção de pares `(nome, país)` e `(nome, (idade, gols, país))`.
- Filtragem de jogadores alemães com menos de 25 anos.
- Padronização de valores de texto sem alterar a estrutura dos pares.
- Ordenação por nome e por idade.
- Cálculo da idade média dos jogadores por país.
- Cálculo da média de gols por país utilizando `reduceByKey` e `mapValues`.

[Abrir PairRDD.ipynb no Google Colab](https://colab.research.google.com/github/sergiocalazans/big-data-pyspark/blob/main/PairRDD.ipynb)

## Estrutura do repositório

```text
big-data-pyspark/
├── RDD.ipynb                # Operações com RDDs e análises de dados
├── PairRDD.ipynb            # Operações com pares chave-valor
├── euro2024_players.csv     # Dados da Eurocopa 2024
├── weather_aus.csv          # Dados meteorológicos da Austrália
├── LICENSE                  # Licença MIT
└── README.md                # Documentação do repositório
```

## Tecnologias utilizadas

- **Python:** linguagem utilizada nas implementações.
- **Apache Spark / PySpark:** processamento distribuído e operações sobre RDDs.
- **Jupyter Notebook:** organização interativa de códigos, exercícios e resultados.
- **Google Colab:** ambiente de execução dos notebooks.
- **CSV:** formato dos conjuntos de dados analisados.

## Como executar

### Opção 1 — Google Colab (recomendada)

1. Abra um dos notebooks pelos links acima.
2. Execute as células em ordem, inicializando a sessão ou o contexto do Spark.
3. Os arquivos CSV utilizados nas atividades são acessados por URLs nos notebooks.
4. Verifique os resultados das transformações, ações e consultas.

> **Observação:** os notebooks criam contextos do Spark de maneiras diferentes. Execute cada notebook separadamente, em uma sessão limpa, para evitar conflitos de contexto.

### Opção 2 — Ambiente local

É possível executar os arquivos em um ambiente com Python, Java compatível com a versão do Spark, Jupyter e PySpark configurados.

```bash
git clone https://github.com/sergiocalazans/big-data-pyspark.git
cd big-data-pyspark
python -m pip install pyspark notebook
jupyter notebook
```

Abra `RDD.ipynb` ou `PairRDD.ipynb` e execute as células na sequência. A compatibilidade de versões do Python, Java e Spark depende do ambiente utilizado.

## Conceitos explorados

| Conceito | Aplicação |
|---|---|
| RDD | Coleção distribuída de dados processada pelo Spark |
| Transformações | Construção de novos RDDs a partir de dados existentes |
| Ações | Execução dos cálculos e recuperação de resultados |
| Pair RDD | Estrutura de pares chave-valor para processamento agrupado |
| `reduceByKey` | Agregação de valores associados à mesma chave |
| `mapValues` | Transformação dos valores mantendo as chaves |
| Dados faltantes | Filtragem de registros inválidos antes de cálculos numéricos |

## Contexto acadêmico

**Instituição:** Pontifícia Universidade Católica do Paraná (PUCPR)  
**Curso:** Bacharelado em Ciência da Computação  
**Disciplina:** Big Data  
**Etapa:** Segunda metade da disciplina — Apache Spark e PySpark  
**Finalidade:** Registro e documentação de atividades práticas acadêmicas

## Autor

**Sérgio Calazans**  
GitHub: [@sergiocalazans](https://github.com/sergiocalazans)

## Licença

Este repositório está disponibilizado sob a [Licença MIT](LICENSE).
