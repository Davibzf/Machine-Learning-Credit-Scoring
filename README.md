# 🧠 ML-CS — Machine Learning Credit Scoring

## 📌 Visão Geral

O **ML-CS (Machine Learning Credit Scoring)** é um projeto de **Machine Learning supervisionado** desenvolvido para **prever o score de crédito de clientes** a partir de dados financeiros, demográficos e comportamentais estruturados.

O objetivo é simular um **sistema de análise de risco de crédito**, seguindo boas práticas utilizadas por **bancos e fintechs**, com foco em **precisão, avaliação correta e interpretabilidade dos modelos**.

---

## 🎯 Objetivos do Projeto

* Prever o **score_credito** de clientes
* Analisar fatores que influenciam o risco de crédito
* Comparar diferentes modelos de Machine Learning
* Aplicar métricas adequadas para avaliação
* Utilizar técnicas de **Explainable AI (XAI)** para interpretação dos resultados

---

## 📊 Variáveis Utilizadas

### 🔹 Identificação e tempo

* `id_cliente`
* `mes`

### 🔹 Perfil do cliente

* `idade`
* `profissao`
* `salario_anual`

### 🔹 Relacionamento financeiro

* `num_contas`
* `num_cartoes`
* `idade_historico_credito`

### 🔹 Empréstimos e crédito

* `num_emprestimos`
* `juros_emprestimo`
* `emprestimo_carro`
* `emprestimo_casa`
* `emprestimo_pessoal`
* `emprestimo_credito`
* `emprestimo_estudantil`

### 🔹 Comportamento financeiro

* `dias_atraso`
* `comportamento_pagamento`
* `investimento_mensal`
* `saldo_final_mes`

🎯 **Variável alvo (target):**

* `score_credito`

> ⚠️ A variável `id_cliente` é utilizada apenas como identificador e não deve ser usada diretamente no treinamento do modelo.

---

## 🧠 Metodologia

1. Análise exploratória dos dados (EDA)
2. Tratamento de valores ausentes
3. Encoding de variáveis categóricas
4. Normalização / padronização
5. Treinamento de modelos supervisionados
6. Avaliação de desempenho com métricas apropriadas
7. Análise de importância das variáveis
8. Explicabilidade com técnicas de XAI

---

## 🤖 Modelos de Machine Learning

* Regressão Linear (baseline)
* Random Forest Regressor
* Gradient Boosting
* XGBoost

Os modelos são comparados para identificar o melhor desempenho na previsão do score de crédito.

---

## 📈 Métricas de Avaliação

### 🔹 Regressão

* MAE (Mean Absolute Error)
* RMSE (Root Mean Squared Error)
* R² (Coeficiente de Determinação)

### 🔹 Classificação (opcional)

* Accuracy
* Precision
* Recall
* F1-score
* AUC-ROC

---

## 🔍 Explainable AI (XAI)

O projeto utiliza técnicas de **Explainable AI** para tornar as decisões do modelo interpretáveis, como:

* Importância das features
* SHAP values

Essas técnicas permitem entender **quais fatores mais impactam o score de crédito**, algo essencial em sistemas financeiros.

---

## 🛠 Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* SHAP
* Matplotlib / Seaborn
* Jupyter Notebook

---

## 📂 Estrutura do Projeto

```
ml-credit-scoring/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── eda.ipynb
│   └── modeling.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── training.py
│   └── evaluation.py
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🚀 Possíveis Aplicações

* Análise de risco de crédito
* Sistemas de decisão financeira
* Simulações para fintechs
* Projetos acadêmicos
* Portfólio em Data Science / Machine Learning

---

## ⚠️ Aviso Legal

Este projeto possui **fins educacionais e demonstrativos**. Não deve ser utilizado diretamente para decisões financeiras reais sem validações regulatórias, auditoria de modelos e conformidade legal.

---

## 👨‍💻 Autor

**Davi Bezerra Fraga**
Projeto desenvolvido para estudos em **Machine Learning aplicado a crédito e finanças**.

---

⭐ Se este projeto te ajudou, considere deixar uma estrela!
