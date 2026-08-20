# 📊 Pré-Modelagem e Análise de Risco de Crédito

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=flat-square&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen?style=flat-square)

## 📌 Visão Geral do Projeto

Este projeto aborda o ciclo completo de **tratamento, análise exploratória (EDA) e pré-processamento de dados** para um cenário de **concessão e modelagem de risco de crédito**. 

O objetivo principal é transformar uma base bruta de dados socioeconômicos em um conjunto limpo, balanceado e otimizado para o treinamento de algoritmos de Machine Learning, garantindo alta coerência estatística e de negócios.

---

## 🎯 Etapas do Pipeline de Dados

1. **Análise Exploratória e Tratamento de Outliers:**
   * Mapeamento de distribuições demográficas e avaliação de *outliers* funcionais (ex: clientes com 3 dependentes).
   * Imputação de dados faltantes via mediana para preservação do perfil estatístico.

2. **Engenharia de Atributos e Formatação de Dados:**
   * Tratamento de tipos de dados (booleans para inteiros `0` e `1`).
   * **Mapeamento Ordinal** para variáveis com hierarquia implícita (`Education` e `Credit Score`).
   * **One-Hot Encoding** para variáveis categóricas nominais (`Gender`, `Marital Status`, `Home Ownership`).

3. **Diagnóstico de Multicolinearidade & Matriz de Correlação:**
   * Análise bivariada das variáveis determinantes de renda e estabilidade.
   * Identificação de alta redundância ($r = -0{,}85$) entre moradia de aluguel e pontuação de crédito.
   * Remoção de colunas redundantes para proteção contra o viés de multicolinearidade em modelos lineares.

4. **Divisão da Base & Tratamento do Desbalanceamento de Classes:**
   * Separação estocástica e estratificada em conjuntos de **Treino (75%)** e **Teste (25%)**.
   * Aplicação do método **SMOTE** (*Synthetic Minority Over-sampling Technique*) restrito exclusivamente aos dados de treino para evitar *data leakage*.

---

## 💡 Principais Insights de Negócio

* 📈 **Efeito Escolaridade vs. Renda:** Existe uma tendência direta de crescimento salarial conforme o avanço da escolaridade, com pico no nível de Mestrado/Doutorado.
* 🏠 **Ponto de Virada Patrimonial:** A faixa salarial entre **$70.000 e $75.000** atua como divisor entre clientes locatários e proprietários de imóveis.
* 💳 **Drivers do Score de Crédito:** Renda ($r = +0{,}74$) e Posse de Imóvel Próprio ($r = +0{,}85$) demonstraram ser os maiores preditores da estabilidade financeira do cliente.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

* **Linguagem:** Python 3.10+
* **Manipulação de Dados:** `pandas`, `numpy`
* **Visualização de Dados:** `seaborn`, `matplotlib`
* **Machine Learning & Pré-processamento:** `scikit-learn` (`train_test_split`)
* **Balanceamento de Dados:** `imbalanced-learn` (`SMOTE`)

---

## 📁 Estrutura do Repositório

```text
├── M17 Projeto Pré-Modelagem.ipynb   # Notebook principal com o pipeline completo
├── README.md                         # Documentação do projeto
