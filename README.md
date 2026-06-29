# 🚔 Previsão de Ocorrências Criminais no Brasil com Machine Learning

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-purple)
![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00)
![Status](https://img.shields.io/badge/Status-Concluído-success)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Sobre o Projeto

Este projeto foi desenvolvido como Trabalho de Conclusão da disciplina **Machine Learning & Analytics**, da Pós-Graduação em Ciência de Dados e Analytics da **PUC-Rio**.

O objetivo é desenvolver modelos capazes de prever o número mensal de vítimas dos principais tipos criminais registrados no Brasil, utilizando técnicas de Machine Learning aplicadas a séries temporais.

Os dados utilizados são públicos e foram obtidos através do **Sistema Nacional de Informações de Segurança Pública (SINESP)**.

---

## 🎯 Objetivos

O projeto busca responder à seguinte questão:

> **É possível utilizar algoritmos de Machine Learning para prever a evolução dos índices criminais brasileiros utilizando apenas informações históricas?**

Para responder essa pergunta foram construídos modelos capazes de realizar previsões em dois níveis:

- 🇧🇷 Brasil
- 📍 Unidade Federativa (UF)

---

# 📂 Base de Dados

Fonte:

**Sistema Nacional de Informações de Segurança Pública (SINESP)**

https://dados.gov.br/

Período analisado:

- Janeiro de 2020
- Dezembro de 2025

---

## 📊 Variáveis utilizadas

Entre os principais atributos utilizados encontram-se:

- UF
- Tipo Criminal
- Data
- Total de vítimas
- Sexo das vítimas
- Faixa etária
- Tipo de arma (quando aplicável)

Após o tratamento dos dados foram criadas variáveis temporais como:

- Ano
- Mês
- Tempo
- Índice temporal

---

# 🛠 Tecnologias Utilizadas

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn

---

# 📁 Estrutura do Projeto

```
MVP_Machine_Learning_Previsao_Ocorrencias_Criminais/

│
├── arquivos/
│   ├── BancoVDE_2020.csv
│   ├── BancoVDE_2021.csv
│   ├── BancoVDE_2022.csv
│   ├── BancoVDE_2023.csv
│   ├── BancoVDE_2024.csv
│   └── BancoVDE_2025.csv
│
├── notebooks/
│   └── MVP_Machine_Learning_Previsao_Ocorrencias_Criminais.ipynb
│
├── README.md
│
└── LICENSE
```

---

# 🔄 Fluxo do Projeto

O desenvolvimento seguiu o pipeline clássico de um projeto de Ciência de Dados.

## ✔ Definição do Problema

Definição do objetivo de negócio.

---

## ✔ Coleta dos Dados

Importação dos arquivos anuais.

---

## ✔ Preparação dos Dados

Foram realizados:

- tratamento de valores ausentes;
- conversão de datas;
- engenharia de atributos;
- agregações;
- filtros;
- normalização dos dados.

---

## ✔ Análise Exploratória (EDA)

Foram realizadas análises para compreender:

- evolução temporal;
- distribuição das ocorrências;
- comportamento por estado;
- comparação entre tipos criminais.

---

## ✔ Engenharia de Atributos

Criação das variáveis:

- ano
- mês
- tempo
- codificações categóricas

---

## ✔ Separação Treino/Teste

Por se tratar de previsão temporal, não foi utilizada divisão aleatória.

Foi adotado:

```python
TimeSeriesSplit
```

preservando a ordem cronológica dos registros.

---

# 🤖 Modelos Desenvolvidos

Foram comparados quatro modelos.

## 📌 Baseline

Modelo de referência utilizando o valor observado no mesmo período do ano anterior.

---

## 📈 Regressão Linear

Modelo linear utilizado como comparação.

---

## 🌳 Random Forest

Modelo baseado em árvores de decisão.

Foi realizado ajuste automático dos hiperparâmetros utilizando:

- GridSearchCV
- TimeSeriesSplit

---

## 🚀 Gradient Boosting

Modelo baseado em árvores sequenciais.

---

# 📏 Métricas de Avaliação

Foram utilizadas as métricas:

- MAE
- RMSE
- R²

Além disso, foi registrado o tempo de treinamento de cada modelo.

---

# 🏆 Resultados

Os modelos foram comparados em duas perspectivas:

- Brasil
- Unidade Federativa

## Exemplo dos resultados obtidos

|Modelo|MAE|RMSE|R²|
|-------|------|------|------|
|Baseline|123,73|202,05|0,9905|
|Random Forest|127,11|204,79|0,9902|
|Gradient Boosting|207,45|274,50|0,9824|
|Regressão Linear|357,67|443,98|0,9540|

> **Observação:** os resultados acima correspondem ao cenário agregado em nível nacional. No notebook também são apresentados os resultados para cada Unidade Federativa.

---

# 📈 Principais Conclusões

✔ Os algoritmos apresentaram elevada capacidade de aprendizado dos padrões históricos.

✔ A utilização de validação temporal evitou vazamento de informação entre treinamento e teste.

✔ O modelo Baseline mostrou desempenho bastante competitivo, evidenciando forte dependência temporal da série.

✔ A Random Forest apresentou desempenho semelhante ao Baseline, demonstrando boa capacidade de modelar relações não lineares presentes nos dados.

✔ A Regressão Linear apresentou desempenho inferior aos modelos baseados em árvores.

---

# 📷 Exemplos de Visualizações

> *(Substitua pelas imagens exportadas do notebook.)*

## Evolução Temporal

```
images/evolucao_temporal.png
```

---

## Comparação dos Modelos

```
images/comparacao_modelos.png
```

---

## Previsões para 2026

```
images/previsoes2026.png
```

---

# 🚀 Como Executar

Clone o repositório

```bash
git clone https://github.com/seu_usuario/MVP_Machine_Learning_Previsao_Ocorrencias_Criminais.git
```

Entre na pasta

```bash
cd MVP_Machine_Learning_Previsao_Ocorrencias_Criminais
```

Abra o notebook no Google Colab ou Jupyter Notebook.

Execute todas as células.

---

# 📚 Referências

BRASIL.

Sistema Nacional de Informações de Segurança Pública (SINESP).

Disponível em:

https://dados.gov.br/

Scikit-Learn Documentation

https://scikit-learn.org/

Pandas Documentation

https://pandas.pydata.org/

---

# 👨‍💻 Autor

**Marcelo Alexandre Machado Silvestre**

Supervisor do Controle Técnico de Manutenção (CTM) – Marinha do Brasil

Pós-Graduando em Ciência de Dados e Analytics – PUC-Rio

Pós-Graduando em Desenvolvimento Full Stack – PUC Minas

Tecnólogo em Análise e Desenvolvimento de Sistemas

Tecnólogo em Gestão Financeira

---

## 📄 Licença

Este projeto foi desenvolvido exclusivamente para fins acadêmicos.

Os dados utilizados são públicos e pertencem ao Governo Federal do Brasil.
